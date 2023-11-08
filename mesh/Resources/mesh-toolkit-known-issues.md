---
title: Known issues for Mesh Toolkit
description: Mesh Toolkit active known issues
ms.service: mesh
author: qianw211    
ms.author: qianwen
ms.date: 11/2/2023
ms.topic: Guide
keywords: Microsoft Mesh, Mesh Toolkit, Mesh Developer
---

# Active known issues - Mesh Toolkit

## Version 23.13

* The embedded videos show as black on Quest 2. (24096)

    *Workaround:*  If you run into an issue where videos display and behave as expected on PC but not on Quest, add the video script to the video player.

### WebSlate

* If loading too many WebSlates at once, lower-end computers may not be able to load all WebSlates, only some WebSlates will be loaded. We recommend using the CPA tool to measure rendering time and determine the proper allocations based on your environment's features.

### Cloud Scripting

#### Azure Login Expired
Some users are experiencing an error during deploy and publish that shows the a similar log output to the following: `The client 'YOUR_USER_EMAIL' with object id 'YOUR_AAD_ID' does not have authorization to perform action 'Microsoft.Resources/deployments/write' over scope ...` This occurs when the locally cached login as expired. The expiration can be checked by running `az account get-access-token --query "expiresOn" --output tsv` in command line. As a workaround, manually run `az login` from the command line.

#### The performance of deployed apps with high frequency messages is sub optimal

Currently, animating the transforms of more than a couple of objects by setting them from the cloud-based Mesh Cloud Scripting can lead to slowdowns when deployed. (Note that these slowdowns are not evident when running the Mesh Cloud Scripting Service locally). We recommend that you make use of the Animator component, which animates properties on the client, as much as possible.

#### Unity can freeze for a period when previewing a scene with a running Mesh Cloud Scripting Service

If you switch the focus from Unity to another app while Unity is playing, the Mesh Cloud Scripting Service continues to run, submitting messages to the message queue. When you switch the focus back to Unity, it pauses until it completely drains the queue. If the Mesh Cloud Scripting Service is making lots of frequent state changes and/or you have switched focus away from Unity for a long time, Unity can freeze for some time while this happens.

#### If scene doesn't contain at least one collider on a gameObject with 'NavMesh' layer, input in Mesh Browser might not work

Changing floor or any platform game object's layer to 'NavMesh' is sufficient.

#### Multiple "Cloud Scripting Metadata" Uploader stages are shown when publishing environment to PC and Android

The "Cloud Scripting Metadata" stage in the Uploader results window shows twice when publishing an environment to both PC and Androind. This is expected and a change to make it more clear is coming soon.

#### Adding multiple lights as children of the same transform  will cause an error

Unity doesn't support adding multiple lights to the same game object, so adding two light nodes to the same transform node will cause a runtime error.

#### Renaming of Unity scenes is not supported

A Unity scene and a C# application are weakly linked by the scene name. When renaming a Unity scene, the user is required to manually rename the corresponding C# project folder to match the Unity scene.
