---
title: Known issues for Mesh toolkit
description: Mesh toolkit active known issues
ms.service: mesh
author: qianw211    
ms.author: vinnietieto
ms.date: 2/12/2024
ms.topic: Guide
keywords: Microsoft Mesh, Mesh toolkit, Mesh Developer
---

# Active known issues - Mesh toolkit

## Version 5.2315.0

* The embedded videos show as black on Quest 2. (24096)

    *Workaround:*  If you run into an issue where videos display and behave as expected on PC but not on Quest, add the video script to the video player.

### Events

* You may not able to access **host tools** in an event template or customization session. Here are the steps to reproduce this issue: (33738)

    * Open your project in the Unity editor;

    * Join a customization session or event template;

    * You'll find no **host tools** available;

    * Add a screenshare, and you won't be able to access **host tools* to start the screenshare for validation.

### WebSlate

* On Quest, the system webview is about two years behind and causes some websites to show an *Unsupported browser* message. We're working with Meta to update Chromium to a more recent version. (28696)

* If loading too many WebSlates at once, lower-end computers may not be able to load all WebSlates; only some WebSlates will be loaded. We recommend that you use the [Content Performance Analyzer tool](../develop/debug-and-optimize-performance/cpa.md) to measure rendering time and determine the proper allocations based on your environment's features.

- When working with WebSlate in the Unity editor, the editor needs to be restarted when updating the WebSlate or Mesh toolkit packages through the Unity package manager.

- The "Current URL" field of a WebSlate currently cannot be updated during Play mode.

- If your WebSlate game object displays an "internal shader error", navigate to the Inspector view of your WebSlate and ensure that the selected shader is set to "UnlitWebSlate".

- Visual scripting has WebSlate support. If your visual scripting graph shows references to the legacy “WebView” type, manually update this reference to “WebSlate”.

- When interacting with a WebSlate, Mesh may capture keyboard input causing unintended interactions with the Mesh app.

## Cloud Scripting known limitations

### Azure Login Expired
Some users are experiencing an error during deploy and publish that shows the a similar log output to the following: `The client 'YOUR_USER_EMAIL' with object id 'YOUR_AAD_ID' does not have authorization to perform action 'Microsoft.Resources/deployments/write' over scope ...` This occurs when the locally cached login as expired. The expiration can be checked by running `az account get-access-token --query "expiresOn" --output tsv` in command line. As a workaround, manually run `az login` from the command line.

### The performance of deployed apps with high frequency messages is sub optimal

Currently, animating the transforms of more than a couple of objects by setting them from the cloud-based Mesh Cloud Scripting can lead to slowdowns when deployed. (Note that these slowdowns are not evident when running the Mesh Cloud Scripting Service locally). We recommend that you make use of the Animator component, which animates properties on the client, as much as possible.

### Unity can freeze for a period when previewing a scene with a running Mesh Cloud Scripting Service

If you switch the focus from Unity to another app while Unity is playing, the Mesh Cloud Scripting Service continues to run, submitting messages to the message queue. When you switch the focus back to Unity, it pauses until it completely drains the queue. If the Mesh Cloud Scripting Service is making lots of frequent state changes and/or you have switched focus away from Unity for a long time, Unity can freeze for some time while this happens.

### If scene doesn't contain at least one collider on a gameObject set to the 'GroundCollision' layer, input in Mesh Browser might not work

Changing floor or any platform game object's layer to 'GroundCollision' is sufficient.

#### Adding multiple lights as children of the same transform  will cause an error

Unity doesn't support adding multiple lights to the same game object, so adding two light nodes to the same transform node will cause a runtime error.

### Renaming of Unity scenes is not supported

A Unity scene and a C# application are weakly linked by the scene name. When renaming a Unity scene, the user is required to manually rename the corresponding C# project folder to match the Unity scene.
