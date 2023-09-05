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

## Version 2023-9-8

### Scripting

* New `meshapp` deployments will fail to create `diagnosticSettings` on the `appService`. (19508)

    ![A screenshot of the Mesh scripting error](media/mesh-scripting-error.png)

    1. Use the uploader to deploy a new `meshapp`. The diagnostic setting resource fails to create with the **Diagnostic settings does not support retention for new diagnostic settings** error.
    1. The Uploader will mark the deploy operation as failed because the expected success message won't be in the output. It'll also break the Mesh Uploader.
    1. The other resources will be created in Azure.

    *Additional details:*

    The first time when you attempt an upload, you'll see the `meshapp` deploy and publish to fail.

    ![A screenshot of the Build and Upload Results dialog](media/build-upload-results-dialog.png)

    This is the diagnostic logs retention issue described above. If you attempt to upload again, you will see what looks like a success:

    ![A screenshot of the Build and Upload Results dialog indicating a success](media/build-upload-results-dialog-success.png)

    If you're careful, you'll notice that the **MeshApp Deploy & Publish** step is no longer listed in the status dialog.  Attempting to connect to an event in this seemingly successful environment will result in mesh scripting failures.

    The reason this occurs is that the earlier failure modified a file in such a way that subsequent uploads are not attempted.  This is why you'll need to remove the `"mode": ""` line.

    *Here's the workaround:*

    1. Uncheck **Enable App Monitoring** until 23.11.
    1. Open the `meshapp.manifest.json` file in a text editor and delete the line that reads `"mode":""`. 

### WebSlate

* After upgrading, WebSlate game objects may encounter an internal shader error. If so, navigate to the **Inspector** view of your WebSlate and ensure that the selected shader is set to `UnlitWebSlate`.
* After upgrading, your visual scripting graph may still reference the legacy `WebView` type. If so, manually update this reference to the correct `WebSlate` type.

