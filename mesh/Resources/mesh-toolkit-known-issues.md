---
title: Known issues for Mesh Toolkit
description: Mesh Toolkit active known issues
ms.service: mesh
author: qianw211    
ms.author: qianwen
ms.date: 12/4/2023
ms.topic: Guide
keywords: Microsoft Mesh, Mesh Toolkit, Mesh Developer
---

# Active known issues - Mesh Toolkit

## Version 23.14

* The embedded videos show as black on Quest 2. (24096)

    *Workaround:*  If you run into an issue where videos display and behave as expected on PC but not on Quest, add the video script to the video player.

### Scripting

* Script graphs were saved with redundant type and versioning information in some object references. This will not visibly impact user experience.

* The **Mesh Visual Scripting Diagnostics** panel only displays the diagnostics for the first selected `ScriptMachine` and errors were logged to the console panel if several were selected at the same time.

* When the **Travel Point** is set up in isolation, not nested in an explicit **Travel Point Group**, and a reference to it is passed to the method or property node from another script node, for example, from a **Get Variable** node, the **Travel Point** reference is incorrectly filtered out at runtime and the method call or property access will fail to work.

### WebSlate

* On Quest, the system webview is about two years behind and causes some websites to show an *Unsupported browser* message. We're working with Meta to update Chromium to a more recent version. (28696)

* If loading too many WebSlates at once, lower-end computers may not be able to load all WebSlates; only some WebSlates will be loaded. We recommend that you use the [Content Performance Analyzer tool](../develop/debug-and-optimize-performance/cpa.md) to measure rendering time and determine the proper allocations based on your environment's features.

## Version 23.13

* The embedded videos show as black on Quest 2. (24096)

    *Workaround:*  If you run into an issue where videos display and behave as expected on PC but not on Quest, add the video script to the video player.

### Scripting

* The **On State Changed** event node stops triggering completely and indefinitely after it had been disabled for the first time. (26333)

* In the script graph, the per-node annotations **Local to this client** and **Shared by all clients** currently doesn't reliably update in real time when the scene is changed while the script graph window is visible. (26334)

* The Mesh **Interactable Body | Is Selected** incorrectly behaves as if it's a local property even though it's networked in the Mesh client. (26792)

* Mesh's injected framework nodes (for example, **Track Object State** and **Sanitize Data**) persist in second-level subgraphs after running a scene in Mesh Emulation Mode. (28966)

* When the **On State Changed** event node is used to observe a shared property or variable, it should be triggered immediately after the property or variable is changed locally. Currently, for shared properties or variables, it's triggered only after the local change had been sent to and received back from the server, incurring network delay even on the sending client. (28968)

* Currently, the list of available script nodes can easily be auto-populated with incompatible (default) project settings or without having been filtered to include only nodes supported by Mesh. For example, this could happen if users chose not to apply Mesh project settings before starting to work on visual scripts, or if they manually edited Visual Scripting's **Type Options** or **Node Library** and selected **Regenerate Nodes**. (26109)

#### Physics

* The physics event nodes: **On Trigger Enter**, **On Trigger Exit**, **On Collision Enter**, and **On Collision Exit** may not reliably trigger on all clients in the room. Depending on network conditions, it's possible that they'll only trigger on a subset of clients. (27635)

* It's currently hard to reliably read-then-write shared state (for example: update a shared score variable) in a script node triggered by one of the physics event nodes: **On Trigger Enter**, **On Trigger Exit**, **On Collision Enter**, and **On Collision Exit**, as these events are generally triggered on more than one client in the room for the same interaction. (27635)

### Interactables

* [Equippable objects](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects) should respond to a mouse down as opposed to the current mouse release. (27858)

* On Quest devices: to pick up an [equippable object](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects), you need to point the controller ray at the object and click the Grip button. If you simply bring your hand close to the object and click the Grip button, nothing will happen.  This feels very unnatural for interaction with objects that are near.  When you're very close to an object, it's hard to point your controller ray at it to interact. (24187)

* Missing `MeshUniqueIdManager`` causes serialization failures. (25151)

### WebSlate

- On Quest, the system webview is about two years behind and causes some websites to show an *Unsupported browser* message. We're working with Meta to update Chromium to a more recent version. (28696)

- If loading too many WebSlates at once, lower-end computers may not be able to load all WebSlates, only some WebSlates will be loaded. We recommend using the CPA tool to measure rendering time and determine the proper allocations based on your environment's features.

- When working with WebSlate in the Unity editor, the editor needs to be restarted when updating the WebSlate or Mesh Toolkit packages through the Unity package manager.

- The "Current URL" field of a WebSlate currently cannot be updated during Play mode.

- If your WebSlate game object displays an "internal shader error", navigate to the Inspector view of your WebSlate and ensure that the selected shader is set to "UnlitWebSlate".

- Visual scripting has WebSlate support. If your visual scripting graph shows references to the legacy “WebView” type, manually update this reference to “WebSlate”.

- When interacting with a WebSlate, Mesh may capture keyboard input causing unintended interactions with the Mesh app

## Cloud Scripting known limitations

### Azure Login Expired
Some users are experiencing an error during deploy and publish that shows the a similar log output to the following: `The client 'YOUR_USER_EMAIL' with object id 'YOUR_AAD_ID' does not have authorization to perform action 'Microsoft.Resources/deployments/write' over scope ...` This occurs when the locally cached login as expired. The expiration can be checked by running `az account get-access-token --query "expiresOn" --output tsv` in command line. As a workaround, manually run `az login` from the command line.

### The performance of deployed apps with high frequency messages is sub optimal

Currently, animating the transforms of more than a couple of objects by setting them from the cloud-based Mesh Cloud Scripting can lead to slowdowns when deployed. (Note that these slowdowns are not evident when running the Mesh Cloud Scripting Service locally). We recommend that you make use of the Animator component, which animates properties on the client, as much as possible.

### Unity can freeze for a period when previewing a scene with a running Mesh Cloud Scripting Service

If you switch the focus from Unity to another app while Unity is playing, the Mesh Cloud Scripting Service continues to run, submitting messages to the message queue. When you switch the focus back to Unity, it pauses until it completely drains the queue. If the Mesh Cloud Scripting Service is making lots of frequent state changes and/or you have switched focus away from Unity for a long time, Unity can freeze for some time while this happens.

### If scene doesn't contain at least one collider on a gameObject with 'NavMesh' layer, input in Mesh Browser might not work

Changing floor or any platform game object's layer to 'NavMesh' is sufficient.

### Multiple "Cloud Scripting Metadata" Uploader stages are shown when publishing environment to PC and Android

The "Cloud Scripting Metadata" stage in the Uploader results window shows twice when publishing an environment to both PC and Androind. This is expected and a change to make it more clear is coming soon.

### Adding multiple lights as children of the same transform  will cause an error

Unity doesn't support adding multiple lights to the same game object, so adding two light nodes to the same transform node will cause a runtime error.

### Renaming of Unity scenes is not supported

A Unity scene and a C# application are weakly linked by the scene name. When renaming a Unity scene, the user is required to manually rename the corresponding C# project folder to match the Unity scene.
