---
title: Release notes for Mesh toolkit
description: Release notes for the Microsoft Mesh Toolkit with a list of important updates and a list of the Microsoft Mesh Toolkit versions.
ms.service: mesh
author: jbrentj    
ms.author: jejacks
ms.date: 02/10/2025
ms.topic: release-notes
keywords: Microsoft Mesh, Mesh toolkit, Mesh Developer
---

# Mesh toolkit release notes

For purposes of this document, there are two categories of users:

* Creators: Technical artist and developers building with the Mesh toolkit
* IT admins: Managers working in Azure or M365

## Version list and dates

> [!IMPORTANT]
> Mesh Toolkit versions older than 5.2406 have being deprecated. We recommend upgrading to the newest version of the Mesh Toolkit.



## Mesh Toolkit 5.2414.X

### What's new

* This release contains minor fixes and improvements.

## Mesh Toolkit 5.2413.X

### What's new

### Mesh Toolkit uploader

* Older uploader versions will warn before changing assets made using a newer version. While the Mesh runtime is backwards compatible with older assets, we cannot guarantee compatibility with an asset that has subsequently been downgraded from a newer version. In the unlikely event that downgrading an asset was somehow unavoidable, please test your asset thoroughly before using in an event.

* Versions of Mesh toolkit older than 5.2406 (released May 2024) will be deprecated starting October 1st. (Note: No action is needed for environments that are already published on the affected toolkit versions earlier than 24.6, existing uploads will continue to function as they do today.)

### Visual scripting

* Users can control whether Visual Scripting errors block upload by using the new settings under Project Settings > Mesh Toolkit Settings > Extensions > Visual Scripting.

* If a visual script variable is accidentally set to a value that's incompatible with its declared type (for example, if you're using "Add (in Math/Scalar)" as the input for setting an Integer-type variable), content validation now flags this as a correctness issue. This shows up in the Mesh Visual Scripting Diagnostics panel, in CPA (Content Performance Analyzer), and before upload.

* Visual scripts can now access properties and methods of Text Mesh Pro - Text (UI). The new script nodes have names starting with Text Mesh Pro UGUI in the script node selector.

## Mesh Toolkit 5.2412.X

### What's new

### Mesh Toolkit uploader

* Fixed bug that caused uploads to fail with a FileNotFoundException on a retry.

* Extend retries around graph operations to hopefully get past temporary issues.

* Removed the option to select the Unity build pipeline in the Mesh Toolkit Settings.

* Fix an issue that caused validation to fail on retry even when the scene was fixed and appeared to be saved.

* Default font settings commands now output a messages to console.

### Interactables

The component for Interactables (“Mesh Interactable Setup”) has been updated with the following:

* UI redesign, with a cleaner look and better organization and usability.

* “Interactables” is now an umbrella term for the four Interactable types: **Basic**, **Manipulable**, **Equippable**, and **Throwable**.

* In the Equippable type, there are ten presets for hand positioning, and you can also create your own custom presets.

* The component now has context-sensitive help buttons.

## Mesh Toolkit 5.2411.X

### What's new

#### Mesh Toolkit uploader

* Updated Build Target selection with more information on the platforms that target supports. Also added a general warning when uploading an environment with a subset of targets selected.


## Mesh Toolkit 5.2410.X

### What's new

#### Mesh Toolkit uploader

* Where there is an issue between Uploader Tool and Mesh Services during the Upload process, we now display a message to the user that the operation is taking longer than expected but still running.

* Fixed bug where the Unity Package Manager failed to get information and the console was spammed by the same message on repeat.

#### WebSlate Controllables to display URls in Mesh events

With the release of the 24.10 Mesh Toolkit, developers now have the ability to add WebSlate Controllables to environments. These WebSlates enable event attendees to interact with a webpage through WebSlates while in a Mesh event and empower event organizers to dynamically change the content that's displayed on the WebSlates in real-time.

An event host could display Microsoft Whiteboard, for example:

:::image type="content" source="media/WebSlate-example-of-whiteboard.png" alt-text="Screenshot of a Mesh event with a WebSlate showing Microsoft Whiteboard with two avatars interacting with it.":::

* **Developer updates:** Same simple workflow for adding Webslates, with minor additional configurations to add Controllable capabilities.

* **Event organizer experience:** Toggle URLs, visibility (on/off), and optionally Prevent suspension (to keep WebSlates always on). Via the Control Panel, changing the URL at runtime updates WebSlates for all users in the event, instantly (global refresh).

* **End user experience:** Upon cursor/controller hover, a menu bar with a built-in refresh button and a tooltip briefly explaining single-user nature of webslates has been added (some webapps may offer shared experiences). This provides a way to return to the URL set by organizers (in the case the user navigates away) and can be used incase webapps have issues during experiences.

Some notable details to consider are:

* Developers have the option to select if a URL can be changed while an event is occurring or not by removing the WebSlate Controllable script in the parent WebSlateFramed GameObject.

* Developers choose the location of the WebSlate in the environment. Currently, WebSlate positioning is not adjustable after they are uploaded to an environment (this is not an Object in the Catalog)

* The content and interaction of the WebSlate will depend on which webapp is displayed on it. For example, some webapps will provide synchronized inputs for all users, creating a sense of a shared interaction - but navigation and scrolling will not be synced across users. Choosing which URLs are displayed in the WebSlate and testing them is important to achieve the desired experience.

* Currently SSO is not supported for any webapps in Mesh. However, on Mesh for Windows (not Quest), signing into certain apps does work via manual authentication. Within the WebSlate, the Microsoft account manager will allow sign in using the credentials that are present on the user's machine for easy and secure content access. Note: Although this unlocks the ability to use Fluid Framework apps like Microsoft Whiteboard and Loop, only inputs are synced across users, not navigation or scrolling.

**24.10 Toolkit upgrade note:**

For existing environments with the WebSlateFramed component in the Unity scene, upgrading Mesh Toolkit to 24.10 will automatically provide organizers with WebSlate Controllable functionality upon Upload. This means that organizers will be able to toggle the URL for their WebSlates at runtime via the Control Panel, and that end users will see a refresh button/info coin upon hovering the slate. We suggest double checking WebSlate positioning in environments to ensure the user-facing menu bar that appears at runtime upon hover (located below the slate in the center) is not colliding with any other parts of the environment.

For those who don't want URLs to be controlled by organizers, the WebSlate Controllable can be turned off by removing the "WebSlate Controllable" script from their WebSlate GameObject.

### Visual scripting

* Improved and extended the diagnostics shown in the Mesh Visual Scripting Diagnostics panel (at the bottom of the Inspector panel) and made them more actionable by including an extended description that can be viewed in a tooltip by hovering any entry in the Diagnostics panel.

* Some of the new diagnostics (for example, "Variable not declared" and "Cannot modify prefab definition") block the environment's upload until they are fixed. Already uploaded environments are not affected.

* Added **On Dictionary Item Added** and **On Dictionary Item Removed** events that allow visual scripts to efficiently respond to items being added to or removed from dictionary-type component properties and visual script variables.

    :::image type="content" source="media/Visual-scripting-dictionary-item-24.10.png" alt-text="Screenshot of the Mesh Toolkit showing hte On Dictionary Item Added or Removed.":::

* Client startup time in Emulator has been improved significantly for large scenes (with thousands of visual scripts and tens of thousands of scene objects). (60475)

#### Resolved issues

* For Mesh Physics, we removed problematic and unnecessary mechanism that disabled Renderer components below Rigidbody at start-up and re-enabled them when fully connected. (59804)

* For Visual Scripting, we fixed an issue that caused embedded subgraphs to be corrupted when saved in Unity Editor. (Subgraphs saved in separate asset files were not affected by this issue.) (60183)

* For Visual Scripting, loading a corrupted embedded subgraph into Unity Editor causes these warnings to be logged to the Editor console: `Failed to add element to graph during deserialization: [...]`. (60183)

* For Visual Scripting, When editing visual scripts in a prefab definition by selecting the prefab asset in the Project panel (instead of opening the prefab definition in scene context or in isolation from the Hierarchy panel), the Mesh Visual Scripting Diagnostics panel may show false-positive diagnostic errors:

  * `Cannot modify prefab definition`
  * `Invalid reference`

    However, these errors do point to actual content issues if they appear when editing visual scripts in a prefab definition edited in scene context or opened in isolation from the Hierarchy panel. (60475)

## Mesh Toolkit 5.2409.X

### What's new

#### Mesh Toolkit Uploader

* **Unity Upgrade**: The 24.9 Toolkit requires the use of the Unity Editor version 2022.3.34f1. This is a minor upgrade, so content that is already published will continue to work.

* The **Build and Upload Results** window which displays at the end of the environment upload process shows the state of pre-processors and validators. To see these results again, in Unity on the menu bar, select **Mesh Toolkit** > **Validate** > **Validate Active Scene**.

* In the Mesh Uploader, there's an updated display for platform support for each environment. The icons for currently selected platforms appear in white; unselected platforms appear in red and display a tooltip warning when you scroll over them.

* Replaced the popup that warned of previously uploaded platforms that aren't in the current selection with a warning in the UI text instead.

#### Visual scripting

* Visual scripts now have access to **Physics | Raycast nodes** that provide Hit Info output. The value returned through this port can be inspected using **Raycast Hit | ...** property accessor nodes.

#### Resolved issues

* Using **Rigidbody | Set Position** and **Rigidbody | Set Rotation** now works as expected and no longer causes the affected physics bodies to be repositioned back to where a visual script most recently placed them on late join.

* The **Rigidbody | Get/Set Position** and **Rigidbody | Get/Set Rotation** nodes as well as the **Transform | Get/Set Position** and **Transform | Get/Set Position** nodes for physics bodies are now correctly annotated with "Shared by all clients" or "Local to this client" in the absence or presence of *Local Physics Scope* components in the Transform hierarchy.

* **Transform | Set Local Scale** now correctly synchronizes across clients when applied to physics bodies.

* The problem that raycasts in visual scripts in Mesh Emulator split-screen mode always targeted the first client's physics colliders instead of their own client's has been fixed. This issue was only noticeable if collider geometry was different across clients, which usually isn't the case unless done explicitly.

## Mesh Toolkit 5.2408.X

### What's new

#### Content Performance Analyzer (CPA)

* The CPA tool now contains a new analyzer to check for occlusion culling data. If static objects exist in the scene without occlusion data, this will block upload until resolved.

* The CPA tool now contains AVP quality options for AVP simulation.

#### Mesh Toolkit Uploader

* Fixed bug which caused the upload to fail during thumbnail generation when the file was not on disk.

* Fix a bug where saving a scene with TMP text caused the mesh toolkit package to reimport.

* Fix a bug that allowed the user to still use a deprecated version of the toolkit.

* Settings title changed from "Mesh Uploader Settings" to "Mesh Toolkit Settings"

## Mesh Toolkit 5.2407.X

### What's new

- You can now enter [Play Mode with Mesh Emulation](../develop/debug-and-optimize-performance/mesh-emulator.md) with [Domain Reloading disabled](../develop/debug-and-optimize-performance/speed-up-mesh-emulation.md). This should significantly speed up the start and stop times of the Mesh Emulator, allowing you to iterate faster.

- Fixed a bug where saving a scene with TMP text caused the mesh toolkit package to reimport.

- Duplicate environment names are no longer allowed in the same collection.

- Add menu "Mesh Toolkit/Configure/Apply Mesh Font to Open Scenes" that will update fonts on open scenes TextMesh pro components to use default Mesh font.

## Mesh Toolkit 5.2406.X

### What's new

#### Visual scripting

* Fixed "Failed to deserialize scriptable object" errors in Emulator that were logged to the Unity console under certain circumstances.

* Fixed an issue where an update to a shared property (or variable) applied by a visual script could sometimes be lost due to an earlier update of the same property (or variable) returning from its roundtrip through the server at an inopportune time.

* Fixed an Emulator-only issue with Visual Scripting late-join in very large scenes if visual scripts were using script variables to pass `Transform` or `GameObject` references into script graphs. When this issue occurred, warnings-level messages with the following wording were logged to the console: "OnMessageReceived: Received message with correct class ID 1 but data size in packet expecting total ... with a packet of 1988, index ... does not look correct."

#### Mesh Toolkit Uploader

* Mesh Toolkit Uploader will check for IL2CPP module being installed to allow building for Windows Standalone (PC) platform.

* Fix a bug where some scenes using default mesh fonts will cause toolkit to build the fonts incorrectly.

* Improve mesh toolkit default font configuration by automatically importing TMP essentials, if needed, when configuring default font.

* Fix extra errors displayed when no valid collections are found.

* Add a message to fill the blank space when an environment had no prior platforms uploaded.

## Mesh Toolkit 5.2405.X

### What's new

#### Mesh Toolkit Uploader

* Cloud Scripting could report that the **scenemap** was out of date because the scene had not yet been saved. Since saving the scene is required for upload, it didn't make sense to report this as a problem. We've moved the option to save the scene to the very beginning of the steps that the uploader performs so the scene is either saved or the operation is cancelled.

* Fixed bug that happened when we tried to rename an asset copy but a previous copy was already present. It also reduces the number of leftover copies left in disk after a build failure.

* Fixed a bug where some scenes using default Mesh fonts caused the Toolkit to issue an unnecessary error in the console.

#### Cloud scripting

Cloud scripting now only generates classes for animators that are used in the Unity scene under the scope of the cloud scripting **gameobject**.  Animators that are unused, or only used in other parts of the scene, will no longer have classes generated.

If your cloud scripts include references to these classes, you will encounter compile errors like this:

```cshar
error CS0246: The type or namespace name 'MyUnusedAnimator' could not be found (are you missing a using directive or an assembly reference?)  
To resolve, ensure that the animator in question is used within the cloud scripting portion of the scene, or remove the reference from your cloud scripts.
```

Note that this change only impacts cloud scripts built with this version of Mesh Toolkit or later. Existing Mesh environment deployments are not affected.

#### Visual Scripting

* Visual scripts are no longer completely disabled if the environment contains a ScriptMachine with a broken ("Missing") or unassigned ("None") asset graph reference.

* The new Show Input Dialog visual script node can be used to pop up a dialog box that prompts the user for text input. The text entered by the user (and the button they pressed to close the dialog) are stored in visual script variables.

    :::image type="content" source="media/Visual-scripting-Show-input-dialogue.png" alt-text="Screenshot of Show Input Dialog visual scripting node in the Mesh Toolkit.":::

* Fixed the String | Create node, which previously only worked in the Emulator but failed to work in standalone builds.

* The script node selector (Fuzzy Finder) in the script graph UI no longer includes nodes that access inherited properties or methods through types that cannot be accessed directly.

* Fixed sharing tags shown in the Visual Scripting graph UI for the following Mesh Interactable Body script nodes to correctly say Shared by all clients (instead of incorrectly Local to this client):
    Mesh Interactable Body | Is Activated
    Mesh Interactable Body | Get Equipped At
    Mesh Interactable Body | Is Equipped
    Mesh Interactable Body | Get Equip Time

    The functionality of these visual script nodes is unchanged. If you need a local version of these properties, you can combine them with the Mesh Interactable Body | Is Mine property.

* Attempting to set an undeclared script variable in a `Variables` component that's "Shared by all clients" no longer causes a flood of console errors. Instead, the attempt to set the invalid variable is ignored.

* **On State Changed** outputs can now be read even when the **On State Changed** event itself wasn't triggered.

    This makes it simpler to execute the same script flow from both an **On State Changed** event as well as, for example, an **On Start event** that leads into the same script flow in order to consistently establish some scene state based on the initial state at startup.

    Previously, any attempt to read **On State Changed** outputs from outside its own script flow led to an error being logged ("The value of... cannot be fetched dynamically, it must be assigned") and the offending script flow being aborted.

* Script errors at runtime are now presented with more useful diagnostics in the Emulator console:

    The console error now includes the name of the `ScriptMachine` and identifies the event node that triggered the offending script flow.

    Clicking the error message in the Emulator console highlights the offending `ScriptMachine` in the transform hierarchy.

#### Playmode

* New scene validation when entering Playmode: Before 5.2405, a scene was only validated if there was an attempt to upload a scene to Mesh. Now, scene validation occurs when a user tries to enter Playmode. 

    If a user attempts to enter Playmode before a scene is validated, there is a new error message:

    :::image type="content" source="media/playmode-scene-validation.png" alt-text="Screenshot of scene validation error dialog when starting playmode.":::

    There is also a new menu item to **Validate Active Scene**:

    :::image type="content" source="media/Playmode-validate-scene-menu-item.png" alt-text="Screenshot of Validate Active Scene menu item in the Mesh Toolkit.":::

## Mesh toolkit 5.2404.X (Preview)

>[!Caution]
>This is a preview release of the Mesh toolkit noted by a **-preview** tag at the end of the version number.  Environments published with this preview version of the Mesh toolkit will only work with the preview version of Mesh, and **are not compatible with the stable public version of Mesh**. Do not upgrade to this version of the Mesh toolkit until a stable public version is released; stable public versions won't have a **-preview** tag at the end of the version number.  
>
> **Be careful that you don't overwrite environments currently in use by your company with the preview version.**

### What's new

* Add Screen Share support to Mesh Toolkit, allowing developers to place on their environments screen share components that later will allow users in a Mesh to screenshare.

    To add a Screen Share component you can:

    1. Open context menu on the **Scene Hierarchy** > **Mesh Toolkit** > **Screen Share**.
    1. Search for the Screen Share prefab on Mesh Toolkit Package and drag and drop it to your scene.

    The added prefab contains an editable root and a mock UI that will not be uploaded to help developers place and design their environments. Modifying the provided mock UI under [NoUpload] will not be reflected when uploading and joining an event on Mesh. The added prefab can be sized and placed as desired on the scene.

    If adding multiple Screen Share components on the scene all of them will show the same screen when a user starts Screen Sharing on Mesh.

#### Mesh Toolkit Uploader

* Scene validation will now happen when entering playmode instead of only before uploading the scene.

* Any scene with unsaved changes will need to be saved before proceeding with an Upload. This is to prevent the loss of these changes during the operation and some bugs which may occur from differences between the scene states.

* Fix to prevent FileNotException error when getting information on the asset being uploaded.

* Fug fix to prevent accidental renaming of the asset copy during build which may cause the operation to fail.

* Fix to reset thumbnail camera if it already exists when adding, instead of throwing an error.

* Disable Build & Publish when Playmode is active as it causes the build to fail.

* Fix potentially confusing error message when upload to graph fails.
Display a progress bar during post build operations.

* Uploader now skips thumbnail generation if the build has already failed.

## Mesh toolkit 5.2403.X

### What's new

#### Mesh Toolkit uploader

* The Mesh Toolkit now requires the use of Unity Version 2022.3.15f1. This is a minor upgrade from the previous version (2022.3.7f1), so projects should upgrade without problems.

* If there is a validation error during creation operation, user won't see a message dialog anymore. Failure will be shown in result dialog and more details will be presented in the logs.

* Fixed a bug where opening ocv after sign in caused unity to crash.

* Handle errors when failing to save the Mesh Toolkit configuration to disk.

* Improved reporting of the states of the Mesh Uploader Extensions in the results dialog.

## Mesh emulator

* Fixed bug on emulator when all scenes would get darker if the first player left.

## Mesh toolkit 5.2402.X

### What's new

#### Mesh Toolkit uploader

* The ContentVersion has been incremented to 1.25.0: Newly published content will only be visible in recent MeshBrowsers.

* Improved handling and reporting of failures during Environment creation.

* Add a prompt to open the Mesh Portal if we failed to find any collections for the user.

* Improved message when cancelling the dialog to select a new thumbnail folder.

#### Mesh 201 Tutorial

* Mesh 201 is released for the Mesh Toolkit version 5.2402.0 (Preview). In this tutorial, you build on that knowledge and learn how to use WebSlates to display web content in your experience. The tutorial includes an interactive globe; when a person in your experience clicks on the globe, the latitude and longitude of the clicked location are captured and these coordinates are incorporated into a Bing Maps URL as parameters. An HTTP request is executed using this URL; Bing Maps provides a map of the chosen area and sends it to a nearby WebSlate.

#### Visual scripting

* Mesh-injected nodes are no longer invisible in the Emulator at runtime, and no longer fill the console with repeated "null texture" warnings. (44056)

* Visual scripts are no longer completely disabled if the environment contains a ScriptMachine with a broken ("Missing") or unassigned ("None") asset graph reference. (36795)

* Fixed the String | Create node, which previously only worked in the Emulator but failed to work in standalone builds. (37040)

* The script node selector (Fuzzy Finder) in the script graph UI no longer includes nodes that access inherited properties or methods through types that cannot be accessed directly. (37824)

* Fixed sharing tags shown in the Visual Scripting graph UI for the following Mesh Interactable Body script nodes to correctly say Shared by all clients (instead of incorrectly Local to this client):
    - Mesh Interactable Body | Is Activated
    - Mesh Interactable Body | Get Equipped At
    - Mesh Interactable Body | Is Equipped
    - Mesh Interactable Body | Get Equip Time

    The functionality of these visual script nodes is unchanged. If you need a local version of these properties, you can combine them with the Mesh Interactable Body | Is Mine property. (38589)

* Fixed Script Stats panel in Mesh Emulator not displaying anything if the visual script graph UI hasn't ever been opened for that Unity project on the local machine yet. (40526)

* Fixed Mesh Visual Scripting Diagnostics panel not displaying anything if the visual script graph UI hasn't ever been opened for that Unity project on the local machine yet. (40527)

* Fixed the On Interval node occasionally triggering twice in short sequence after an interval has elapsed. (40894)

* Several useful Render Settings properties are now exposed to visual scripts:

    * For environments whose Environment Lighting Source is set to Skybox:
        * Render Settings | Get Skybox – see [Unity docs](https://docs.unity3d.com/ScriptReference/RenderSettings-skybox.html)
        * Render Settings | Get/Set Ambient Intensity – see [Unity docs](https://docs.unity3d.com/ScriptReference/RenderSettings-ambientIntensity.html)
    * Note that in order to see the effects of skybox material updates on dynamic lighting, include the Dynamic GI | Update Environment script node after modifying the skybox material.

    * For environments whose Environment Lighting Source is set to Color:
        * Render Settings | Get/Set Ambient Light – see [Unity docs](https://docs.unity3d.com/ScriptReference/RenderSettings-ambientLight.html)

    * For environments whose Environment Lighting Source is set to Gradient:
        * Render Settings | Get/Set Ambient Sky Color – see [Unity docs](https://docs.unity3d.com/ScriptReference/RenderSettings-ambientSkyColor.html)
        * Render Settings | Get/Set Ambient Equator Color – see [Unity docs](https://docs.unity3d.com/ScriptReference/RenderSettings-ambientEquatorColor.html)
        * Render Settings | Get/Set Ambient Ground Color – see [Unity docs](https://docs.unity3d.com/ScriptReference/RenderSettings-ambientGroundColor.html)

* Several Line Renderer component methods and properties are now exposed to visual scripts:
    * Methods:
        * Line Renderer | Get Position – see [Unity docs](https://docs.unity3d.com/ScriptReference/LineRenderer.GetPosition.html)
        * Line Renderer | Get Positions – see [Unity docs](https://docs.unity3d.com/ScriptReference/LineRenderer.GetPositions.html)
        * Line Renderer | Set Position – see [Unity docs](https://docs.unity3d.com/ScriptReference/LineRenderer.SetPosition.html)
        * Line Renderer | Set Positions – see [Unity docs](https://docs.unity3d.com/ScriptReference/LineRenderer.SetPositions.html)

    * Properties:
        * Line Renderer | Get/Set Position Count – see [Unity docs](https://docs.unity3d.com/ScriptReference/LineRenderer-positionCount.html)

* Many useful Video Player component methods and properties are now exposed to visual scripts.
    * Methods:
        * Video Player | Play – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer.Play.html)
        * Video Player | Pause – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer.Pause.html)
        * Video Player | Stop – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer.Stop.html)
        * Video Player | Step Forward – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer.StepForward.html)

    * Properties – which can all be observed using an *On State Changed* event node:
        * Video Player | Is Prepared – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-isPrepared.html)
        * Video Player | Is Playing – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-isPlaying.html)
        * Video Player | Is Paused – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-isPaused.html)
        * Video Player | Is/Set Looping – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-isLooping.html)
        * Video Player | Get/Set Time – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-time.html)
        * Video Player | Get/Set Playback Speed – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-playbackSpeed.html)
        * Video Player | Get Length – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-length.html)
        * Video Player | Can Set Time – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-canSetTime.html)
        * Video Player | Can Set Playback Speed – see [Unity docs](https://docs.unity3d.com/ScriptReference/Video.VideoPlayer-canSetPlaybackSpeed.html)

#### Mesh uploader

* The ContentVersion has been incremented to 1.25.0; Newly published content will only be visible in recent MeshBrowsers.

* Improved handling and reporting of failures during Environment creation.

* Add a prompt to open the Mesh Portal if we failed to find any collections for the user.

* Improved message when cancelling the dialog to select a new thumbnail folder.

## Mesh toolkit 5.2401.0 (Preview)

### What's new

#### Toolkit

* The `ContentVersion` has been incremented to 1.24.0: Newly published content will only be visible in the recent Mesh app.

* Some errors that came from the Mesh services did not have enough information in them. For example, some errors were just reported as "BadRequest" or "BadGateway". We've improved error messages from the service to include more useful details.

* Simplified discovery of options by moving the **Settings** in the **Options** tab into the **Project Settings/Mesh Uploader Settings** pane with the other **Uploader** settings.

* Improved error handling when thumbnail generation fails.

* Improved error handling on asset validation.

* If we fail to create a copy of the asset, the build and publish operation won't proceed.

* Fixed an issue where the **Require Ground Collision Layer** won't have the correct value when changed while a window was open.

##### Diagnostics and debug tools are now easier to discover and use in the Mesh Emulator:

* In the Unity editor, click the **Enter Split Screen** button to enable split-screen mode, which allows you to test and debug multi-user issues. 

* In the split-screen mode, click **Add** or **Leave** to add more split-screen clients to the session or to make them leave the session.

* Select **Script Stats** to show a panel of real-time visual script performance statistics, such as:

    * which visual script flows require the most per-frame time to execute

    * which shared properties and variables are updated (and replicated over network) most often

    Clicking on an entry brings you straight to the corresponding scene object in the **Hierarchy** panel.

* Select **Perf Stats** to show to **Visual Profiler** (only in single-screen mode) to display real-time CPU and GPU performance statistics for the scene you're running.

#### Scripting and physics

* It's now possible to use the **On State Changed** visual script event to observe the transform of a physics body. The event fires whenever the physics body is moved directly on the local client or by a remote client. (31869)

* During an environment upload, issues detected by the Visual Scripts validation step now log significantly improved diagnostics and extended guidance on how to avoid the reported issues. (34450)

## Version 5.2315.0

### Version list and dates

These are the offerings and packages currently available. There may be slight differences in the list you see here and the packages you have or see.

>[!Note]
>The version number for your environment project's Mesh toolkit package **must** be equal to or older than the Mesh app (PC or Quest) your environment is targeting, otherwise the environment will not load. You can generally ensure this is true by using the non-preview Mesh toolkit package, which releases only after the matching Mesh app is available in stores.

| Mesh offering/package   | Version | Date released
| ----------- | ----------- | ----------- |
| Mesh toolkit package      |   5.2315.0     | 2023-2-2  |
| Mesh (PC/Quest)   |  5.2315.0       |  2023-2-2  |

### What's new

#### Toolkit

* The `ContentVersion` has been incremented to 1.22.0. Newly published content will only be visible in recent versions of the Mesh app.

* Added new prebuild validation which will only allow GameObjects on certain layers.

* Renamed the **Create Asset** button to **Create Environment**.

* Fixed build status in the result report when there are invalid assets during the build phase.

* If the level of diagnostic data is not set by the tenant admin, then by default the Uploader will send optional diagnostics.

* Renamed the menu item from **Mesh Toolkit/Configure/Default Font** to **Mesh Toolkit/Configure/Apply Default Font Settings**.

* Renamed the menu item from **Mesh Toolkit/Configure/Project Settings** to **Mesh Toolkit/Configure/Apply Project Settings**.

* In the Mesh Uploader **Update Environment** tab, when you click the the **Thumbnail** drop-down and select **Take from folder**, a button appears with a label that used to say **Add Provisional Thumbnails** but now says **Add guidance thumbnails**.

* We now show an error dialog when the user picks a folder outside of the project.

* Fixed bugs in the Uploader extensions system:

    * Metadata stages were accidentally being run multiple times.

    * Metadata results were being ignored in certain cases.

* We now return to an empty default scene after building when there was no active scene.

* We now avoid displaying collections that could not be validated in Mesh.

* We now show the toolkit package version in the Uploader Window.

* Uploader build platforms are now stored as per project settings instead of per computer settings.

* Improved how the uploader handles an operation being cancelled.

* Prevent refreshing asset list when changing window focus.

* Added an updated title and warning when using the preview version of the toolkit.

* We cleared a confusing progress bar when Unity reloads assembly during an operation.

* We now prompt the user to re-authenticate if authentication has expired when retrying an operation.

* Sometimes the Uploader would hit a `UserInteractionNeeded` exception when authenticating the user. We now mitigate this problem when it occurs by delegating the user to a Web Browser based authentication.

* Breaking changes to layers: we renamed several layers, moving currently unused layers into reserved layers, and updated cross-layer interactions. See [Configuring for avatar movement and teleportation](/mesh/develop/build-your-basic-environment/configuring-for-avatar-movement-and-teleportation).

* Moved the setting from `RequireNavMeshLayer` to `RequireGroundCollisionLayer`.

* Fixed failure message in the result dialog for successful publishes.

#### Scripting

* The NavMesh layer is now called the GroundCollision layer. For more information on the uses of the GroundCollision layer, see [Configuring for avatar movement and teleportation](../develop/build-your-basic-environment/configuring-for-avatar-movement-and-teleportation.md).

* Shared properties and script variables set on dynamic targets--for example, target component instances read from script variables or otherwise deduced at script runtime--now reliably work on all viable targets throughout the scene. (32730)

    Previously, only a subset of viable target instances throughout the scene worked reliably when a target was deduced dynamically during script runtime. This doesn't include target instances that were placed in sibling branches of the transform tree.
    
    * anything on the implicit `This` scene object

    * anything below it
    
    * anything on any of its parents 
    
    The `This` scene object is the GameObject the `ScriptMachine` executing the visual script is attached to.
    
    For example, if you were trying to set a shared property of a `Foo`-type component and you were using a variable to dynamically reference a specific `Foo` instance to turn that property on, this would only have worked reliably for any for the following `Foo` instances:

    * was attached to `This` = the same GameObject as the `ScriptMachine` running the visual script

    * was attached to any parent/ancestor GameObject of `This` in the transform hierarchy

    * was attached to any child/descendant GameObject of This in the transform hierarchy

* Using Timer nodes in subgraphs no longer causes repeated error messages related to `OptimizedTimerUnitUpdateScheduler` to be logged. (31866)

* The visual script graph UI now includes usage notes and helpful hints on Mesh's and Unity's visual script nodes. (25922)

* It's no longer necessary to add `Microsoft.Mesh.VisualScripting.xml` to version control. If it has been previously deployed into your Unity project, it can be safely deleted and removed from version control. (25922)

* In the **Local Script Scope** component, the **Share visual script variables on this GameObject** setting now defaults to being off when a new instance of this component is added to the scene. Existing instances are unaffected. (26551)

* The special script nodes injected by Mesh at runtime have significantly improved visuals and handling now (30925):

    * The visual footprint of injected nodes has been reduced to remove visual clutter and to make script flows easier to follow while they're executing. They're now firmly attached to one of the neighboring user-defined nodes.

  * New visuals of injected nodes:
  
    | New visuals | Injected nodes |
    | -------- | ------- |
    | ![an image of the profiling visual](media/profiling.png)  | profiling (start of flow)    |
    | ![an image of the data filtering visual](media/data-filtering.png) | data filtering   |
    | ![an image of the state tracking visual](media/state-tracking.png)    | state tracking    |
    
  * When the data filtering node blocks data and passes on a `Null` value instead, its icon changes and its tooltip shows diagnostic information on what data is blocked most recently:
  
      ![an image of the data filter node blocking data showing diagnostic information on what data is blocked most recently](media/blocked-data-forbidden-text.png)
    
    * When you edit script graphs at runtime in the Emulator, injected nodes are now automatically injected and removed as required.

* Script graphs were saved with redundant type and versioning information in some object references. This will not visibly impact user experience. This redundant information is no longer included. (30688)

* The **Mesh Visual Scripting Diagnostics** panel now correctly displays diagnostics for all selected `ScriptMachine` components if more than one is selected in the transform hierarchy. Previously, only diagnostics for the first selected ScriptMachine were displayed. If several were selected at the same time, errors were logged to the console panel. (30873)

* Accessing **Travel Point** methods and properties now works in all cases. Previously, when the **Travel Point** was set up in isolation and not nested in an explicit **Travel Point Group**, and a reference to it was passed to the method or property node from another script node (for example, from a **Get Variable** node), the **Travel Point** reference was incorrectly filtered out at runtime and the method call or property access would fail to work. (31414)

#### WebSlate

* Added the option to prevent the WebSlate from suspending when users are at a distance, or when it is offscreen. Useful for slates that need to keep running in the background, but can cause performance issues if overused. Normally, to save resources, WebSlates suspend 30 seconds after going offscreen or becoming too small to be useful.

    This option can be seen in Unity's inspector when a WebSlate is selected, as a checkbox on the WebSlate script called **Prevent Suspension**.

#### Mesh 101 Tutorial

* The **Create Asset** button is now **Create Environment**.  See [Mesh 101 Tutorial Chapter 5: Make your environment available for testing](/mesh/develop/getting-started/mesh-101-tutorial/mesh-101-05-make-environment-available).

## Version 5.2314.0

### Version list and dates

These are the offerings and packages currently available. There may be slight differences in the list you see here and the packages you have or see.

>[!Note]
>The version number for your environment project's Mesh toolkit package **must** be equal to or older than the Mesh app (PC or Quest) your environment is targeting, otherwise the environment will not load. You can generally ensure this is true by using the non-preview Mesh toolkit package, which releases only after the matching Mesh app is available in stores.

| Mesh offering/package   | Version | Date released
| ----------- | ----------- | ----------- |
| Mesh toolkit package      |   5.2314.0     | 2023-12-4  |
| Mesh (PC/Quest)   |  5.2314.0       |  2023-12-4  |

### What's new

#### Scripting

* The **On State Changed** event node now works correctly after its `ScriptMachine` is disabled and later re-enabled. Previously, the node incorrectly stopped triggering completely and indefinitely after it had been disabled for the first time. (26333)

* In the script graph, the per-node annotations **Local to this client** and **Shared by all clients** now reliably update in real time when the scene is changed while the script graph window is visible. (26334)

* The **Mesh Interactable Body | Is Selected property** property is now correctly networked in Mesh Emulation Mode. Previously, it incorrectly behaved as if it was a local property even though it is networked in the Mesh client. (26792)

* Mesh's injected framework nodes (for example, **Track Object State** and **Sanitize Data**) no longer persist in second-level subgraphs after running a scene in Mesh Emulation Mode. (28966)

* When the **On State Changed** event node is used to observe a shared property or variable, it now triggers immediately after the property or variable is changed locally. Previously, for shared properties or variables, it triggered only after the local change had been sent to and received back from the server, incurring network delay even on the sending client. (28968)

* Available script nodes in the script graph editor now reliably represent what's supported in Mesh, and it's no longer necessary to add `UnitOptions.db` to version control as it's automatically re-generated if necessary when the Unity project is opened. (26109)

    Previously, the list of available script nodes can easily be auto-populated with incompatible (default) project settings or without having been filtered to include only nodes supported by Mesh. For example, this could happen if users chose not to apply Mesh project settings before starting to work on visual scripts, or if they manually edited Visual Scripting's **Type Options** or **Node Library** and selected **Regenerate Nodes**.

##### Physics

* The physics event nodes **On Trigger Enter**, **On Trigger Exit**, **On Collision Enter**, and **On Collision Exit** are now reliably networked. By default, these events reliably trigger on all clients in the room. However, if the physics collider observed by these event nodes is in scope of a **Local Physics Scope** component, the events reliably trigger on exactly one client, which makes it possible for the script flows they trigger to reliably read and write shared state (for example: update a shared score variable). (27635)

#### Interactables

* [Equippable objects](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects) now respond to a mouse button down as opposed to the mouse button release. (27858)

* On Quest devices: to pick up an [equippable object](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects), you can simply bring your hand close to the object and click the Grip button.  

    Previously, you need to point the controller ray at the object and click the **Grip** button. This feels very unnatural for interaction with objects that are near.  When you're very close to an object, it's hard to point your controller ray at it to interact. (24187)

* **Validate Unique ID** added to environment upload. To verify the interactables in your scene that have valid unique ids go to **Mesh Toolkit -> Validate Unique IDs**. (25151)

* Throwable objects have a new setting for **Throw Direction Offset**. This is added to the direction the object is being thrown. (26308)

* `MeshInteractableSetup` will no longer allow objects to be both manipulable and equippable. Objects that were previously defined as both will only be equippable and you may change it back to manipulable if that's not intended. (26632)

#### Uploader

* The ContentVersion has been incremented to 1.21.0: Newly published content will only be visible in the recent Mesh build.

* The environment thumbnail will be automatically generated based on travel point when no thumbnail camera is found in the scene.

* Renamed **Mesh World** to **Environment collection** on the uploader user interface and logs.

* Updated the Mesh logo.

* Fixed the **Feedback** window which was previously blank.

* Added tooltips to the **Uploader** dialog which can contain useful information in case of failures.

* Making the **Results** section for **Extension tools** an expandable area.

* Fixed a bug where the Uploader could appear to open in a valid state but also show a dialog claiming the user's license is not valid.

* Fixed a bug where missing TMP settings will not setup default font.

* Fixed `ArgumentNullException` when using **Toggle [NoUpload] suffix** without selecting a GameObject.

* Added handler for the graph error when the Uploader fails to find the OneDrive folder.

* Failed to upload Thumbnails will now report correctly as an error and fail before trying to publish an asset.

* Fixed an issue which displayed a warning before uploading disabled entries.

#### WebSlate

* Fixed this issue: On Quest, if the user resumes from sleep, entering an event will crash if the event has WebSlate. (27705)

#### Error messages

* A new `TravelExceptionReason` and localized error message for  `RelayServerUnreachableException`:

    Oops! We failed to connect. Please check your internet connection and try again. If you continue to experience this problem, check with your IT department and mention: the client didn't receive a response from the Relay server within the connection timeout. (29004)

* A new `TravelExceptionReason` and localized error message for `RelayNetworkException`:

    Oops! We failed to connect. Please check your internet connection and try again. (29004)

## Version 5.2313.0

### Version list and dates

These are the offerings and packages currently available. There may be slight differences in the list you see here and the packages you have or see. We are working to create better transparency and standardization of versions of offerings and packages to make upgrading easier.

>[!Note]
>The version number for Mesh (PC or Quest) **must** match the Mesh toolkit authoring package version you're using otherwise you may get errors or unexplained behavior. Please hold off on upgrading the Mesh toolkit authoring package until the Mesh client version for your target platform (PC or Quest) is available.

| Mesh offering/package   | Version | Date released
| ----------- | ----------- | ----------- |
| Mesh toolkit Package      |   5.2313.0     | 2023-11-13  |
| Mesh (PC/Quest)   |  5.2313.0       |  2023-11-13  |

### What's new

#### Scripting

**Restrictions on UnityEvents and animation events in Unity**

UnityEvents and animation events must call into visual scripts. They are not allowed to directly manipulate properties or invoke methods. This restriction applies to the following:

* in a Timeline `SignalReceiver`
* in Animation Events

Here's what to do for UnityEvent in a `SignalReceiver` as the starting point:

1. For Animation Events, it's the same except you can use the **Animation Event** visual script trigger and the corresponding `TriggerAnimationEvent` function on the `ScriptMachine` object, where the *Function* in the Animation Event and the `Float`, `Int`, `String` parameters can be used or filled arbitrarily.

1. Create a `ScriptMachine` for a visual script that uses an UnityEvent trigger and that performs the action you'd like to do.
 
1. Choose a descriptive name for the UnityEvent trigger, for example `DoThing`:

    ![Dialog box for UnityEvent and ](media/unity-event-dialog.png)
   
1. In the `SignalReceiver`, set up the UnityEvent by the following steps:

1. Target the `ScriptMachine` you've created for the visual script.

1. For the function to call, select `ScriptMachine > TriggerUnityEvent (string)`.
    1. In the parameter field, enter the name of the UnityEvent trigger (for example, `DoThing`).

    ![Dialog box for ](media/signal-receiver-box.png)
   
#### Physics

* Added the component `LocalPhysicsScope`to create a part of the scene hierarchy where rigidbodies are not synced among clients.

* Added the component `ThrowTrajectory` to calculate future positions of the rigidbody trajectory.

#### WebSlate

* We fixed an issue where it would allow scripting ([Visual scripting](/mesh/develop/script-your-scene-logic/visual-scripting/visual-scripting-overview) and [Cloud scripting](/mesh/develop/script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts)) to correctly control WebSlate at start-up.

    Before this fix, if the scripting navigate or push HTML content to WebSlates at start-up, it would not show up correctly due to a race-condition.
  
* Added the option to prevent the WebSlate from suspending when users are at a distance, or when it is offscreen. Useful for slates that need to keep running in the background, but can cause performance issues if overused. Normally, WebSlates suspend 30 seconds after going offscreen or becoming too small to be useful, to save resources.
  
    This option can be seen in Unity's inspector when a WebSlate is selected, as a checkbox on the WebSlate script called "Prevent Suspension".

#### Uploader

* The `ContentVersion` has been incremented to 1.20.0: Newly published content will only be visible in recent Mesh app.

* Fixed a rendering issue at World List and Environment dropdowns.

* Fixed a bug where create tab UI will draw incorrectly when the text overflowed out of the window boundaries.

* Fixed a bug where the Uploader was throwing regex exceptions after a failed build.

* Added a check for potential null reference exception when publishing assets.

#### Content Performance Analyzer (CPA)

* Batch counts reported by the Content Performance Analyzer and the Mesh Performance Profiler are now more accurately counted based on Unity's SRP batcher markers. 

    >[!Note]
    >Batch counts will no longer be reported outside of the Unity editor because they can't be accurately counted in release builds.

### Resolved product issues

* This issue: "a privacy statement for the `com.microsoft.mesh.toolkit` package gets truncated when viewed in the **Unity Package Manager** in the package description section" -- has been fixed.
