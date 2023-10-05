---
title: Cloud scripting known issues
description: Review the known issues with Cloud Scripting for Mesh.
author: typride
ms.author: vinnietieto
ms.date: 8/28/2023
ms.topic: Guide
keywords: Microsoft Mesh, scripting, cloud scripting, visual scripting, coding
---

# Cloud Scripting known issues

Here is our current set of known issues.  We're working on addressing all these for upcoming releases.

## High priority

### Azure Login Expired
Some users are experiencing an error during deploy and publish that shows the a similar log output to the following: `The client 'YOUR_USER_EMAIL' with object id 'YOUR_AAD_ID' does not have authorization to perform action 'Microsoft.Resources/deployments/write' over scope ...` This occurs when the locally cached login as expired. The expiration can be checked by running `az account get-access-token --query "expiresOn" --output tsv` in command line. As a workaround, manually run `az login` from the command line.

### Environment Upload Hangs

If environment upload process never completes or hangs, refer to [Mesh APP CLI Tool]() TBD on how to deploy manually.

### Server app not updated with new changes

If you notice that recent changes aren't reflected on the server app, restart the app by running the `meshapp restart` command.

### Renaming of Unity scenes is not supported

A Unity scene and a C# application are weakly linked by the scene name. When renaming a Unity scene, the user is required to manually rename the corresponding C# project folder to match the Unity scene.

Internal ID: [39431]

### Space characters aren't allowed in a Unity project and folders

1. Space characters aren't allowed in the path to a Unity project
1. Space characters aren't allowed in Unity folder and scene names.

### The scene must be manually saved before uploading the template
Refer to [this workaround](./Troubleshooting.md#when-joining-event-in-meshbrowser-scene-is-completely-different). TBD

### The performance of deployed apps with high frequency messages is sub optimal

Currently, animating the transforms of more than a couple of objects by setting them from the cloud-based Mesh App can lead to slowdowns when deployed. (Note that these slowdowns are not evident when running the Mesh App locally). We recommend that you make use of the Animator component, which animates properties on the client, as much as possible.

### Unity can freeze for a period when previewing a scene with a running Mesh App

If you switch the focus from Unity to another app while Unity is playing, the Mesh App continues to run, submitting messages to the message queue. When you switch the focus back to Unity, it pauses until it completely drains the queue. If the Mesh app is making lots of frequent state changes and/or you have switched focus away from Unity for a long time, Unity can freeze for some time while this happens.

### If scene doesn't contain at least one collider on a gameObject with 'NavMesh' layer, input in Mesh Browser might not work

Changing floor or any platform game object's layer to 'NavMesh' is sufficient.

## Medium Priority

### Multiple "MeshApp Metadata" Uploader stages are shown when publishing environment to PC and Android

The "MeshApp Metadata" stage in the Uploader results window shows twice when publishing an environment to both PC and Androind. This is expected and a change to make it more clear is coming soon.

### Adding multiple lights as children of the same transform  will cause an error

Unity doesn't support adding multiple lights to the same game object, so adding two light nodes to the same transform node will cause a runtime error.

### Client disconnect callback doesn't reach the server unless the Mesh application is closed

When the user leaves a space or event, the event client disconnect callback doesn't fire. When the user closes the Mesh application entirely, the client disconnect callback will be triggered.

Internal ID:  [39437]

## Next steps

> [!div class="nextstepaction"]
> [Cloud scripting release notes](cloud-scripting-release-notes.md)
