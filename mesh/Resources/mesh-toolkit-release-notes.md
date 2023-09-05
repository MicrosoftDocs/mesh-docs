---
title: Release notes for Mesh Toolkit
description: Mesh release notes
author: qianw211    
ms.author: qianwen
ms.date: 9/8/2023
ms.topic: Guide
keywords: Microsoft Mesh, Mesh Toolkit, Mesh Developer
---

# Mesh Toolkit release notes

**Release notes and known issues for Microsoft Mesh Toolkit and Azure**

For purposes of this document, there are two categories of users:

* Creators: Technical artist and developers building with the Mesh Toolkit
* IT admins: Managers working in Azure

## Release 2023-9-8

### Version list

These are the offerings and packages currently available. There may be slight differences in the list you see here and the packages you have or see. We are working to create better transparency and standardization of versions of offerings and packages to make upgrading easier.

>[!Note]
>The version number for Mesh (PC or Quest) **must** match the Mesh Toolkit Authoring package version you're using otherwise you may get errors or unexplained behavior. Please hold off on upgrading the Mesh Toolkit Authoring package until the Mesh client version for your target platform (PC or Quest) is available.

| Mesh offering/package   | Version | Date released
| ----------- | ----------- | ----------- |
| Mesh Toolkit Package      |        | 2023-9-  |
| Mesh Azure Portal |  20230905.68       |  2023-9-5 |
| Mesh (PC/Quest)   |  5.2311.0       |  2023-9-  |

### What's new

* Unity upgraded to 2022.3.7. We recommend all Unity projects for Mesh environments to be upgraded to Unity 2022 LTS, using the latest 23.11 Mesh Toolkit and Mesh app build.

#### Scripting

* Mesh 101 sample has been updated to include the Object Configuration Layer (OCL) and Visual scripting workflow.
* Player spawning is now handled by `TravelPoints`, the legacy spawn system has been removed: this includes the `SpawnConfig` scripts and support for spawning into seats by default.  All Mesh environments must have `TravelPoints` configured to maintain desired player spawning behavior.  If no `TravelPoints` are found in the scene, the player will spawn above the origin, and if the floor is nearby, the player will be grounded, otherwise the player will fall and respawn in a loop.
* Upgrade instructions: To use the global deployment configuration previously set in the project setting in Unity Editor, select your environment and scene in the Mesh Uploader **Update Environment** tab -> **Modify Deployment Configs** tick box -> select **Use Legacy Configs From Assets** option. This should apply the legacy global deployment configuration to your environment and scene.
* For the latest information in Visual Scripting, see *Mesh Visual Scripting Guide.pdf*.
* For the latest information on Cloud Scripting, see *Mesh Scripting Developer Guide.pdf*.

#### Physics

* Assemblies have been renamed from `com.microsoft.mesh.physics.*` to `Microsoft.Mesh.Physics.*` requiring the use of the Mesh Updater executable to migrate existing content and a reupload of all content. See OneMeshToolkit migration steps for details.
* Various deprecated components have been removed from the main Mesh Toolkit package.
* An additional package `com.microsoft.mesh.physics.legacy-6.0.77.tgz`` package is available for this release to facilitate manual migration. This package can be added to a legacy project in addition to the Mesh Toolkit package. Any references to a deprecated package will then continue to work in PlayMode as well as in the Mesh app, but write an error message to the Unity Console window that allows finding and manually replacing the component. These errors must be addressed within this release cycle, afterwards deprecated components may silently cease to work.
* The `SharedEvents` mechanism, introduced to replace the `UnityEvent` for connecting `Mesh.Physics` components has been superseded by the far more powerful `Mesh.VisualScripting` integration. Wherever a low-level one-to-one replacement is not possible, we have generally found it useful to take a step back to the higher-level use case to construct a solution that better fits the Visual Scripting paradigm.
* Most deprecated components have no one-to-one replacement, but their main use cases can now be better realized by `Mesh.VisualScripting`. If important use cases in the existing content cannot be migrated, contact support to request features we might have missed.

    | Component name     | Suggested migration path |
    | ----------- | ----------- |
    | **`BuzzerButton`**      | **`BuzzerButton`**       |
    | &nbsp;&nbsp;`BodyPairDistanceSensor` |  &nbsp;&nbsp;replace by new Visual Scripting-enabled `BuzzerButton` |
    | &nbsp;&nbsp;`ButtonJoint` |  &nbsp;&nbsp;replace by new Visual Scripting-enabled `BuzzerButton` |
    | &nbsp;&nbsp;`SharedControlEvents` | &nbsp;&nbsp;replace by new VisualScripting-enabled `BuzzerButton` |
    | `MeshPhysicsBodyEvents` <br> (a.k.a. `SharedBodyEvents`) | replace by `VisualScripting` |
    | `MeshPhysicsEvents` <br> (a.k.a. `SharedPhysicsEvents`) |	replace by `VisualScripting` |
    | `StickyBodyEffects` | replace by `VisualScripting` |
    | `StickyBodyTrigger` | replace by `TriggerEventsSensor & VisualScripting` |
    | `TeleportBody` |	replace by `VisualScripting SetPosition` |
    | `ForceToolConfig` | replace by `MeshInteractableProperties` |
    | `ThrowableBody` |	replace by `MeshInteractableProperties \| Equippable \| Throwable` |

#### Uploader

* Updated Uploader to Unity version 2022.3.7f1
* The `ContentVersion` has been incremented to 1.18.0: Newly published content will only be visible in recent Mesh standalone app builds.
* Added validation to ensure `MeshThumbnailCamera`` is present in the scene if the thumbnail is in auto generation mode.
* Added a setting that allows Auto-filter components. Enabling this setting will destroy the not-supported components before uploading the asset. Otherwise, build and upload operations will fail, clearly alerting the user.
* Extensions can now display a warning state that doesn’t fail the upload but does call the user to action.
* Mesh Uploader configured project settings updates: Added reserved layers.
* Fixed the tooltip on the **Results** dialog.

#### Content Performance Analyzer Version 0.5.0

* Analyzers can now warn rather than fail on certain issues. This ensures some issues are treated as blockers while others are more advisory. 
* There is a new WebSlate (previously known as WebView) analyzer to look at how long WebSlates takes to render.
* There is a new Animation analyzer to look at animators that update even when culled.
* We added Mesh Uploader integration! Now some analyzers will run before every upload. Note: analyzers which require PlayMode are not run.

