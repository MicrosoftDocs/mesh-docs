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

## Version 23.11

### Version list and dates

These are the offerings and packages currently available. There may be slight differences in the list you see here and the packages you have or see. We are working to create better transparency and standardization of versions of offerings and packages to make upgrading easier.

>[!Note]
>The version number for Mesh (PC or Quest) **must** match the Mesh Toolkit Authoring package version you're using otherwise you may get errors or unexplained behavior. Please hold off on upgrading the Mesh Toolkit Authoring package until the Mesh client version for your target platform (PC or Quest) is available.

| Mesh offering/package   | Version | Date released
| ----------- | ----------- | ----------- |
| Mesh Toolkit Package      |        | 2023-9-  |
| Mesh Azure Portal |  20230817.92   |  2023-9-5 |
| Mesh (PC/Quest)   |  5.2311.0       |  2023-9-  |

### What's new

* Unity upgraded to 2022.3.7. We recommend all Unity projects for Mesh environments to be upgraded to Unity 2022 LTS, using the latest 23.11 Mesh Toolkit and Mesh app build.
* Player spawning is now handled by `TravelPoints`, the legacy spawn system has been removed: this includes the `SpawnPointConfig` and `ArbitrarySpawnPointConfig` scripts and support for spawning into seats by default.  All Mesh environments must have `TravelPoints` configured to maintain desired player spawning behavior.  If no `TravelPoints` are found in the scene, the player will spawn above the origin, and if the floor is nearby, the player will be grounded, otherwise the player will fall and respawn in a loop.

#### Scripting

* Mesh 101 sample has been updated to include the Object Configuration Layer (OCL) and Visual scripting workflow.
* Upgrade instructions: To use the global deployment configuration previously set in the project setting in Unity Editor, select your environment and scene in the Mesh Uploader **Update Environment** tab -> **Modify Deployment Configs** tick box -> select **Use Legacy Configs From Assets** option. This should apply the legacy global deployment configuration to your environment and scene.
* For the latest information in Visual Scripting, see *Mesh Visual Scripting Guide.pdf*.
* For the latest information on Cloud Scripting, see *Mesh Scripting Developer Guide.pdf*.

#### Physics

* Assemblies have been renamed from `com.microsoft.mesh.physics.*` to `Microsoft.Mesh.Physics.*` requiring the use of the Mesh Updater executable to migrate existing content and a reupload of all content. See OneMeshToolkit migration steps for details.
* Various deprecated components have been removed from the main Mesh Toolkit package.
* An additional package `com.microsoft.mesh.physics.legacy-6.0.77.tgz`` package is available for this release to facilitate manual migration. This package can be added to a legacy project in addition to the Mesh Toolkit package. Any references to a deprecated package will then continue to work in PlayMode as well as in the Mesh app, but write an error message to the Unity Console window that allows finding and manually replacing the component. These errors must be addressed within this release cycle, afterwards deprecated components may silently cease to work.
* The `SharedEvents` mechanism, introduced to replace the `UnityEvent` for connecting `Mesh.Physics` components has been superseded by the far more powerful `Mesh.VisualScripting` integration. Wherever a low-level one-to-one replacement is not possible, we have generally found it useful to take a step back to the higher-level use case to construct a solution that better fits the Visual Scripting paradigm.

    | SharedEvent name     | Suggested migration path |
    | ----------- | ----------- |
    | `CollisionEventsSensor.onCollisionEnter / Exit` | replace by VisualScripting `onCollisionEnter / Exit` |
    | `TriggerEventsSensor.onTriggerEnter / Exit`     | replace by VisualScripting `OnTriggerEnter / Exit`   |
    | `StickyBody.onStick / onUnstick`                | replace by VisualScripting with collision and/or interaction events |
    | `BouncingSurface.onBounce`    | replace by VisualScripting with collision events |

* Most deprecated components have no one-to-one replacement, but their main use cases can now be better realized by `Mesh.VisualScripting`. If important use cases in the existing content cannot be migrated, contact support to request features we might have missed.

    | Component name     | Suggested migration path |
    | ----------- | ----------- |
    | `BodyPairDistanceSensor` |  replace by new Visual Scripting-enabled `BuzzerButton` |
    | `ButtonJoint` |  replace by new Visual Scripting-enabled `BuzzerButton` |
    | `SharedControlEvents` | replace by new VisualScripting-enabled `BuzzerButton` |
    | `MeshPhysicsBodyEvents` (a.k.a. `SharedBodyEvents`) | replace by `VisualScripting` |
    | `MeshPhysicsEvents` (a.k.a. `SharedPhysicsEvents`) |	replace by `VisualScripting` |
    | `StickyBodyEffects` | replace by `VisualScripting` |
    | `StickyBodyTrigger` | replace by `TriggerEventsSensor & VisualScripting` |
    | `TeleportBody` |	replace by `VisualScripting SetPosition` |
    | `ForceToolConfig` | replace by `MeshInteractableProperties` |
    | `ThrowableBody` |	replace by `MeshInteractableProperties \| Equippable \| Throwable` |
    | `CollisionEventsSensor`    | replace by VisualScripting `OnCollisionEnter / OnCollisionExit` |
    | `TriggerEventsSensor`    | replace by VisualScripting `OnTriggerEnter / OnTriggerExit` |

#### WebSlate

* *Renaming*: We've renamed WebView to Webslate.
* *Framed WebSlate prefab*: New WebSlate prefab with a Mesh-style design frame is now available in the Mesh Toolkit.
* *Security enhancements*: Navigation within WebSlate is exclusively limited to HTTPS.
* *Visual Scripting*: After incorporating the WebSlate visual scripting node into your project, you can utilize it just like any other node in your visual script graph. Here's an example of a script graph that loads a new URL in WebSlate when the state of a graph variable changes.
* *Manual authentication*: To ensure security against unintended URL-based attack vectors such as phishing, WebSlates by default restricts navigation to the URLs that are included under the domain of the first page loaded into the WebSlate.
* *Image Quality replacement*: For the 23.11 release, we are temporarily removing Image Quality. Image quality will default to medium quality. Pixels per Unit will enable WebSlates to match the resolution of your screen, enabling users to have a better experience at various viewing distances.
* *WebSlate performance improvements*:
    * *Culling*: stops rendering when webviews are outside the user's viewport.
    * *Suspend/resume*: suspends any webslate not being actively rendered after a preset time.
* CPA tool now supports WebSlate: Collects and analyzes performance (e.g. render time) across all WebSlates in your scene. This feature provides warnings if elements in your scene are affecting your WebSlates.

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

