---
title: Developer guidance for 23.11
description: Transition
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, Mesh Portal, Immersive spaces, Avatars, getting started, documentation, features
---

# Mesh Toolkit 23.11 upgrade guide

How to upgrade to Unity 2022.3.7f1 and associated breaking changes for Mesh developers.

## Context

During Private Preview, the Mesh Toolkit and Mesh application will ship with breaking changes that all developers must accommodate as they update their Unity projects to the latest version. As with previous versions of Mesh releases, moving to the latest version is required.

In particular, the Mesh 23.11 release has two major updates that are more impactful than most releases. Mesh has moved forward from `Unity 2021` to `Unity 2022.3.7f1`. In addition, many component names, namespaces, and assemblies have been renamed to match the expected public shape. Developers and their organizations must consider the following two sections of changes when moving to the latest version.

### Requirements

* **Install Unity 2022.3.7f1**
* **Download the latest `Mesh Toolkit 23.11.zip` and run your Mesh project(s) with Unity 2022.3.7f1** for access to the latest components and features.
* **Run the renaming script `Microsoft.Mesh.Updater.exe` to update renamed components.** Nearly all Mesh Toolkit components have been renamed as of 23.11, and the script is only available during Private Preview. We look forward to continuing to support you throughout the future, and this is a necessary step for customers in Private Preview who are with us during the transition to Public Preview in the near future.
* **Request all Mesh users in your organization to update or download the latest Mesh client application from the Microsoft Store (for PC) and/or Meta App Lab (for Mesh on Quest).**

## Upgrading content to 23.11

23.11 has both a Unity upgrade (2022.3.7f1) and a significant number of Toolkit renames. To update your content, the steps are:

1. Clean the Unity project from the command line with git clean –dxf.
2. Open the project in Unity 2022.3.7f1 and allow it to upgrade the project / materials etc.
3. Save and close the Unity project.
4. Run the MeshUpdater.exe tool to change toolkit renames / references. Note that this mostly changes references for Mesh physics and visual scripts that call Mesh components.
5. Change the toolkit package to the latest 23.11 version in manifest.json for the project.
6. If the user has a MeshApp, upgrade the code:

    Change `Microsoft.MeshApps.UnityRuntime` to `Microsoft.Mesh.CloudScripting` in `D:\x\x\x\Packages\com.x.mesh\Editor\MeshTemplateMenu.cs`

    Change `WebViewNode` to `WebSlateNode` in
    `D:\x\x\x\Assets\.MeshApps\x\Feature\DisplayView.cs`
7. Open the Unity project.
8. Run the Content Performance Analyzer and fix any errors it produces (**Mesh Toolkit** -> **Content Performance Analyzer**)
9. Reconfigure the cloud scripting deployment configuration.
    1. See Cloud Scripting section in Breaking changes below
1. Publish the environment.

    > [!NOTE]
    > Update the MeshApp subscription, resource group, etc. in the Mesh Uploader.

Having issues? See the [troubleshooting](#troubleshooting) section below.

## Breaking changes

This release introduces the following changes:

* **Unity component renames**

    Scene components should update automatically for the renames; however, if you have any visual scripts, you’ll need to use the Mesh Updater tool, `Microsoft.Mesh.Updater.exe` described above.

* **Deploying environments**

    To use the global deployment configuration previously set in the project setting in Unity Editor:

    1. Select the environment and scene in the Mesh Uploader "Update Environment" Tab.
    1. Select the "Modify Deployment Configs" option, and then select the "Use Legacy Configs From Assets" option. This should apply the legacy global deployment configuration to the environment and scene.

* **Player & Object interactions**

    Scenes must have a new TravelPoint component. 23.11 removes the legacy spawning system entirely, and now requires that all Mesh environments use TravelPoints. This is our new publicly supported player repositioning system (including spawning). Player spawning is now handled by TravelPoints, the legacy spawn system has been removed (this includes the SpawnConfig scripts and support for spawning into seats by default).

    All Mesh environments must have TravelPoints configured to maintain desired player spawning behavior. If no TravelPoints are found in the scene, the player will spawn above the origin (if the floor is nearby, the player will be grounded; otherwise the player will fall and respawn in a loop).

* **Environment design considerations**
    * Any environments using lightmaps will need to re-bake lighting after the 2022 upgrade.
    * All materials will be modified after the 2022 upgrade.
    * When upgrading, users may run into the error "WebView is a namespace but is used like a type". To fix this restart Unity. This should make the error go away.
    * Note that that some Unity layer names have changed in 23.11.

* **Cloud scripting**
    * Moved to a per-environment deployment configuration workflow. The deployment configuration is associated with environment and configured from the MeshUploader UI now. See the Scripting Getting Started guide for the latest workflow.

        To use the global deployment configuration previously set in the project setting in Unity Editor, select the environment and scene in the MeshUploader "Update Environment" tab, then select the "Modify Deployment Configs" option, and then select the "Use Legacy Configs From Assets" option. This should apply the legacy global deployment configuration to the environment and scene.

        However, at the moment that work is not entirely complete.  While these deployment settings will switch automatically when choosing an environment to upload, not everything will switch automatically.  Until the work is complete, please continue to use your existing process in addition to setting up this UX: so keep updating `meshapp.manifest.json` with the desired settings as normal before uploading an environment.

* **Mesh Physics**
    * Various deprecated components have been removed from the main Mesh Toolkit package. An additional package, 'com.microsoft.mesh.physics.legacy-6.0.77.tgz', is available for this release to facilitate manual migration. This package can be added to a legacy project in addition to the Mesh Toolkit package. Any reference to a deprecated component will then continue to work in PlayMode as well as the MeshApp but will write an error message to the Unity Console window that allows finding and manually replacing the component. These errors must be addressed within this release cycle; afterwards, deprecated components may silently cease to work.

    * The SharedEvents mechanism, introduced to replace the UnityEvent for connecting Mesh.Physics components, has been superseded by the far more powerful Mesh.VisualScripting integration. Wherever a low-level one-to-one replacement isn't possible, we've found it useful to take a step back to the higher-level use case to construct a solution that better fits the VisualScripting paradigm.

    |**SharedEvent name**                              |**Suggested migration path**                                                |
    |--------------------------------------------------|----------------------------------------------------------------------------|
    |CollisionEventsSensor.onCollisionEnter / Exit     | replace by VisualScripting OnCollisionEnter / Exit                         |
    |TriggerEventsSensor.onTriggerEnter / Exit         | replace by VisualScripting OnTriggerEnter / Exit                           |
    |StickyBody.onStick / onUnstick                    |  replace by VisualScripting with collision and/or interaction events       |
    |BouncingSurface.onBounce                          |  replace by VisualScripting with collision events                          |

    * Most deprecated components have no one-to-one replacement, but their main use cases can now be better realized by Mesh.VisualScripting. If important use cases in existing content can't be migrated, contact your Microsoft Mesh TAP partner to request features we might have missed.


    |**Component name**                                |**Suggested migration path**                                        |
    |--------------------------------------------------|--------------------------------------------------------------------|
    |BodyPairDistanceSensor (part of BuzzerButton)     |  replace by new VisualScripting-enabled BuzzerButton               |
    |ButtonJoint (part of BuzzerButton)                | replace by new VisualScripting-enabled BuzzerButton                |
    |SharedControlEvents (part of BuzzerButton)        |   replace by new VisualScripting-enabled BuzzerButton              |
    |MeshPhysicsBodyEvents (a.k.a. SharedBodyEvents)   |  replace by VisualScripting                                        |
    |MeshPhysicsEvents (a.k.a. SharedPhysicsEvents)    | replace by VisualScripting                                         |
    |StickyBodyEffects                                 |  replace by VisualScripting                                        |
    |StickyBodyTrigger                                 | replace by TriggerEventsSensor & VisualScripting                   |
    |TeleportBody                                      |  replace by VisualScripting SetPosition                            |
    |ForceToolConfig                                   |   replace by MeshInteractableProperties                            |
    |ThrowableBody                                     |    replace by MeshInteractableProperties Equippable Throwable      |
    |CollisionEventsSensor                             |  replace by VisualScripting OnCollisionEnter/OnCollisionExit       |
    |TriggerEventsSensor                               |  replace by VisualScripting OnTriggerEnter/OnTriggerExit           |

## ForceToolConfig replacement steps for Interactables

To replace the deprecated ForceToolConfig component, follow these steps:

* Replace ForceToolConfig with the MeshInteractableProperties component, which will act equally on each Rigidbody object in the Hierarchy below.

* Select the Manipulable check box to make the objects interactable by the ray interaction,  similar to ForceToolConfig.

* Activate Highlight Settings | While Hovered & While Selected

* If ForceToolConfig events were used to trigger actions, this needs to be reconstructed from scratch by attaching a MeshInteractableBody component next to each Rigidbody and using a VisualScripting to observe its IsSelected/IsHovered properties. See the section "Example 1: Calling “Reset Body Transforms” from a Visual Script when object is selected" for details.

* If a ThrowableBody component was used in combination with ForceToolConfig, a similar effect can be achieved by activating Equippable and configuring Throw Settings.

* Advanced behavior configuration of ForceToolConfig hasn’t been precisely re-implemented, but many use cases are covered by the various Manipulation Settings of MeshInteractableProperties. Contact support if critical use cases are missing.

## Visual script update examples

We suggest that you read our documentation on Mesh Visual Scripting and Mesh Object and Avatar Interactions first.

### Calling “Reset Body Transforms” from a Visual Script when an object is selected

To reset body transforms, we first need an interactable GameObject that will listen to user interactions. In this example, we’ll reset body transforms when the user selects an object.

To make a GameObject interactable, we add a *Mesh Interactable Properties* component to the GameObject. We can leave the parameters at their defaults – the GameObject doesn’t need to be equippable or manipulatable. For Mesh *Interactable Properties* to work, there must exist a collider either on this GameObject or anywhere under it in the Hierarchy.

:::image type="content" source="media/developer-guidance-23.11/Picture1.png" alt-text="Mesh interactable properties script":::

Next, we create a visual script. First, add a Script Machine component to the same GameObject.

:::image type="content" source="media/developer-guidance-23.11/Picture2.png" alt-text="Script machine component":::

This will automatically also add the *Variables* component.

:::image type="content" source="media/developer-guidance-23.11/Picture3.png" alt-text="Variables component":::

Add a new variable with the following properties:

* Name: ResetBodyTransformsComponent (this can be any unique name)
* Type: Reset Body Transforms (select from a list of available objects)
* Value is the actual reference to your Reset Body Transforms component which you want to call. The easiest way to assign this is to drag the GameObject with the Reset Body Transforms component from the scene Hierarchy window. This GameObject is probably at the root node of objects you’re resetting.

:::image type="content" source="media/developer-guidance-23.11/Picture4.png" alt-text="Variables":::

In the Script Machine, click New to create a new visual script and give it a name. After saving, Unity will automatically open a Visual Scripting Graph window where you can edit the visual script. We create the following nodes:

* Mesh Interactable Body: Is Selected: This is the property of Mesh Interactable Body (the component added by Mesh Interactable Properties automatically at runtime) that which tracks whether the object is selected or not.
* On State Changed: Used to track changes to the property.
* If: This is the visual script node that’s equivalent to the if-else code block. We’ll only reset body transforms when an object gets selected (and not when an object is deselected).
* Get Object Variable: From the drop-down menu, select the ResetBodyTransformsComponent which we added above.
* Reset Body Transforms: Reset Body Transforms Now: This is the actual function call that resets the bodies.

Connect the nodes as shown in the image below. If everything is correct, the bodies should reset when the GameObject is selected.

:::image type="content" source="media/developer-guidance-23.11/Picture5.png" alt-text="Connect nodes visual scripting":::

## Component renames in 23.11

| 23.10 Type                                                         | 23.11 Type                                                             |
|--------------------------------------------------------------------|------------------------------------------------------------------------|
| Microsoft.Mesh.Toolkit.AspectRatioResizeBehavior                   | Microsoft.Mesh.Controllables.AspectRatioResizeProcessor                |
| Microsoft.Mesh.Toolkit.EmbeddedAudioBehavior                       | Microsoft.Mesh.Controllables.EmbeddedAudioControllable                 |
| Microsoft.Mesh.Toolkit.EmbeddedVideoBehavior                       | Microsoft.Mesh.Controllables.EmbeddedVideoControllable                 |
| Microsoft.Mesh.Toolkit.ObjectBehavior                              | Microsoft.Mesh.Controllables.ObjectControllable                        |
| Microsoft.Mesh.Toolkit.StreamedVideoBehavior                       | Microsoft.Mesh.Controllables.StreamedVideoControllable                 |
| Microsoft.Mesh.Toolkit.UnityPlayableBehavior                       | Microsoft.Mesh.Controllables.UnityPlayableControllable                 |
| Microsoft.Mesh.ObjectConfigurationLayer.PlayerAnchorObject         | Microsoft.Mesh.Interactables.AvatarAnchor                              |
| Microsoft.Mesh.ObjectConfigurationLayer.PlayerTetherObject         | Microsoft.Mesh.Interactables.AvatarTether                              |
| Microsoft.Mesh.ObjectConfigurationLayer.PlayerTriggerObject        | Microsoft.Mesh.Interactables.AvatarTrigger                             |
| Microsoft.Mesh.ObjectConfigurationLayer.Billboard2D                | Microsoft.Mesh.Interactables.Billboard2D                               |
| Microsoft.Mesh.ObjectConfigurationLayer.MeshInteractableObject     | Microsoft.Mesh.Interactables.MeshInteractableBody                      |
| Microsoft.Mesh.ObjectConfigurationLayer.MeshInteractableConfig     | Microsoft.Mesh.Interactables.MeshInteractableProperties                |
| Microsoft.Mesh.ObjectConfigurationLayer.TravelPoint                | Microsoft.Mesh.Interactables.TravelPoint                               |
| Microsoft.Mesh.ObjectConfigurationLayer.TravelPointGroup           | Microsoft.Mesh.Interactables.TravelPointGroup                          |
| Microsoft.Mesh.ObjectConfigurationLayer.UniqueObjectId             | Removed                                                                |
| Microsoft.Mesh.Physics.BodyPairDistanceSensor                      | Legacy                                                                 |
| Microsoft.Mesh.Physics.ButtonJoint                                 | Legacy                                                                 |
| Microsoft.Mesh.Physics.CollisionEventsSensor                       | Legacy                                                                 |
| Microsoft.Mesh.Physics.ForceToolConfig                             | Legacy                                                                 |
| Microsoft.Mesh.Physics.ForceToolInteractableSetup                  | Legacy                                                                 |
| Microsoft.Mesh.Physics.ForceToolTargetingHighlight                 | Legacy                                                                 |
| Microsoft.Mesh.Physics.ForceToolTargetingMonitor                   | Legacy                                                                 |
| Microsoft.Mesh.Physics.ForceToolTether                             | Legacy                                                                 |
| Microsoft.Mesh.Physics.PhysicsArtifactSetup                        | Legacy                                                                 |
| Microsoft.Mesh.Physics.PhysicsSceneSetup                           | Legacy                                                                 |
| Microsoft.Mesh.Physics.SharedBodyEvents                            | Legacy Microsoft.Mesh.Physics.MeshPhysicsBodyEvents                    |
| Microsoft.Mesh.Physics.SharedControlEvents                         | Legacy                                                                 |
| Microsoft.Mesh.Physics.SharedPhysicsEvents                         | Legacy Microsoft.Mesh.Physics.MeshPhysicsEvents                        |
| Microsoft.Mesh.Physics.StickyBodyEffects                           | Legacy                                                                 |
| Microsoft.Mesh.Physics.StickyBodyTrigger                           | Legacy                                                                 |
| Microsoft.Mesh.Physics.TeleportBody                                | Legacy                                                                 |
| Microsoft.Mesh.Physics.ThrowableBody                               | Legacy                                                                 |
| Microsoft.Mesh.Physics.TriggerEventsSensor                         | Legacy                                                                 |
| Microsoft.Mesh.Toolkit.ArbitrarySpawnPointConfig                   | Removed, use Microsoft.Mesh.Interactables.TravelPoint/TravelPointGroup |
| Microsoft.Mesh.Toolkit.MeshRichTextFonts                           | Microsoft.Mesh.Text.DynamicRichTextFonts                               |
| Microsoft.Mesh.Toolkit.SpawnPointConfig                            | Removed, use Microsoft.Mesh.Interactables.TravelPoint/TravelPointGroup |
| Microsoft.Mesh.VisualScripting.LocalSceneScope                     | Microsoft.Mesh.VisualScripting.LocalScriptScope                        |
| Microsoft.Mesh.WebView.WebView                                     | Microsoft.Mesh.WebSlate.WebSlate                                       |
| Microsoft.MeshApps.UnityRuntime.Binding.AnimatorDomBinding         | Microsoft.Mesh.CloudScripting.Binding.AnimatorDomBinding               |
| Microsoft.MeshApps.UnityRuntime.Binding.BoxGeometryDomBinding      | Microsoft.Mesh.CloudScripting.Binding.BoxGeometryDomBinding            |
| Microsoft.MeshApps.UnityRuntime.Binding.CapsuleGeometryDomBinding  | Microsoft.Mesh.CloudScripting.Binding.CapsuleGeometryDomBinding        |
| Microsoft.MeshApps.UnityRuntime.Binding.DirectionalLightDomBinding | Microsoft.Mesh.CloudScripting.Binding.DirectionalLightDomBinding       |
| Microsoft.MeshApps.UnityRuntime.Binding.GeometryDomBinding         | Microsoft.Mesh.CloudScripting.Binding.GeometryDomBinding               |
| Microsoft.MeshApps.UnityRuntime.Binding.LightNodeDomBinding        | Microsoft.Mesh.CloudScripting.Binding.LightNodeDomBinding              |
| Microsoft.MeshApps.UnityRuntime.Binding.MeshBehavior               | Microsoft.Mesh.CloudScripting.Binding.MeshBehavior                     |
| Microsoft.MeshApps.UnityRuntime.Binding.MeshGeometryDomBinding     | Microsoft.Mesh.CloudScripting.Binding.MeshGeometryDomBinding           |
| Microsoft.MeshApps.UnityRuntime.Binding.PointLightDomBinding       | Microsoft.Mesh.CloudScripting.Binding.PointLightDomBinding             |
| Microsoft.MeshApps.UnityRuntime.Binding.RigidBodyDomBinding        | Microsoft.Mesh.CloudScripting.Binding.RigidBodyDomBinding              |
| Microsoft.MeshApps.UnityRuntime.Binding.SceneDomBinding            | Microsoft.Mesh.CloudScripting.Binding.SceneDomBinding                  |
| Microsoft.MeshApps.UnityRuntime.Binding.SidecarDomBinding          | Microsoft.Mesh.CloudScripting.Binding.SidecarDomBinding                |
| Microsoft.MeshApps.UnityRuntime.Binding.SphereGeometryDomBinding   | Microsoft.Mesh.CloudScripting.Binding.SphereGeometryDomBinding         |
| Microsoft.MeshApps.UnityRuntime.Binding.SpotLightDomBinding        | Microsoft.Mesh.CloudScripting.Binding.SpotLightDomBinding              |
| Microsoft.MeshApps.UnityRuntime.Binding.TextDomBinding             | Microsoft.Mesh.CloudScripting.Binding.TextDomBinding                   |
| Microsoft.MeshApps.UnityRuntime.Binding.TouchSensor                | Microsoft.Mesh.CloudScripting.Binding.TouchSensor                      |
| Microsoft.MeshApps.UnityRuntime.Binding.TransformDomBinding        | Microsoft.Mesh.CloudScripting.Binding.TransformDomBinding              |
| Microsoft.MeshApps.UnityRuntime.Binding.WebViewDomBinding          | Microsoft.Mesh.CloudScripting.Binding.WebSlateDomBinding               |
| Microsoft.MeshApps.UnityRuntime.MeshApp                            | Microsoft.Mesh.CloudScripting.MeshApp                                  |


## Known issues

See the [Mesh Toolkit release notes](Resources/mesh-toolkit-release-notes.md) for 23.11.

## Troubleshooting

If you have trouble with the update script, try to resolve it by right clicking the toolkit package folder in the Project View and select **Reimport**. This should help resolve dangling references in the PlaymodeSetup prefab.

## Next steps

   > [!div class="nextstepaction"]
   > [Use Mesh](Setup/Content/m365-migration-guide.md)
