---
title: Known issues for Mesh Toolkit
description: Mesh Toolkit active known issues
author: qianw211    
ms.author: qianwen
ms.date: 9/8/2023
ms.topic: Guide
keywords: Microsoft Mesh, Mesh Toolkit, Mesh Developer
---

# Acitive known issues - Mesh Toolkit

## Version 23.12

## Version 23.11

### Interactables

* If you run into a Trigger Zone component, please ignore it. This will be removed in the next release.

### Scripting

* New `meshapp` deployments will fail to create `diagnosticSettings` on the `appService`. (19058)

    ![A screenshot of the Mesh scripting error](media/mesh-scripting-error.png)

    >[!Note]
    >The issue with creating diagnostic settings retention has been resolved for 23.11. However, this error dialog may still show up if you have experienced a deployment failure in the past.

    *Additional details:*

    The first time when you attempt an upload, you'll see the `meshapp` deploy and publish to fail.

    ![A screenshot of the Build and Upload Results dialog](media/build-upload-results-dialog.png)

    This is the diagnostic logs retention issue described above, which has been resolved for 23.11. If you attempt to upload again, you will see what looks like a success:

    ![A screenshot of the Build and Upload Results dialog indicating a success](media/build-upload-results-dialog-success.png)

    If you're careful, you'll notice that the **MeshApp Deploy & Publish** step is no longer listed in the status dialog.  Attempting to connect to an event in this seemingly successful environment will result in mesh scripting failures.

    The reason this occurs is that the earlier failure modified a file in such a way that subsequent uploads are not attempted.  This is why you'll need to remove the `"mode": ""` line.

    *Here's the workaround:*

    1. Be sure to **Enable App Monitoring** for 23.11, and re-enable this setting if you have previously disabled it. This step is crucial to our diagnostic capabilities.
    1. Open the `meshapp.manifest.json` file in a text editor and delete the line that reads `"mode":""`. 

### WebSlate

* If loading too many WebSlates at once, lower-end computers may not be able to load all WebSlates, only some WebSlates will be loaded. We recommend using the CPA tool to measure rendering time and determine the proper allocations based on your environment's features.
* After upgrading, WebSlate game objects may encounter an internal shader error. You can navigate to the **Inspector** view of your WebSlate and ensure that the selected shader is set to `UnlitWebSlate`.
* After upgrading, your visual scripting graph may still reference the legacy `WebView` type. You can manually update this reference to the correct `WebSlate` type.

### Mesh Toolkit Updating/Upgrading

In rare instances, after you update the Toolkit package, your Unity project may become unexplainably and temporarily broken. This can result in mysterious compiler errors and missing script references despite the script file being present and clean.

1. Close and restart Unity.

1. If this doesn't work, on the Unity menu bar, select Assets > Reimport All. Note that this process can take some time.



