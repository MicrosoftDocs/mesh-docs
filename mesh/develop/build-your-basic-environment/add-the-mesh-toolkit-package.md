---
title: Add the Mesh Toolkit package
description: Instructions for adding the Mesh Toolkit package to your project.
ms.service: mesh
author: typride
ms.author: jejacks
ms.date: 10/4/2023
ms.topic: overview
keywords: Microsoft Mesh, getting started, toolkit, Mesh toolkit, import, registry, scoped registry, packages
---

# Add the Mesh Toolkit package

The Mesh Toolkit enables creators and developers to build custom 3D environments and experiences with Unity.

To add the Mesh Toolkit package to your Unity project:

1. With your Unity project opened, go to **Edit** > **Project Settings** > **Package Manager**.

1. Add a scoped registry with the following details:

   - **Name:** mesh.toolkit

   - **URL:** https://registry.npmjs.org

   - **Scopes(s):** com.microsoft

   ![Scope Registry Configuration](../../media/build-your-basic-environment/configure-scoped-registry.png)

1. Go to **Window** > **Package Manager**.

1. Click the **Packages** dropdown in the toolbar and select **My Registries**.

1. Select **Microsoft Mesh Toolkit** in the list and click the **Install**  button in the right pane. You can select the version, install a preview version, and update/remove versions.

    :::image type="content" source="../../media/build-your-basic-environment/Microsft-Mesh-toolkit-download-pacakge-install-unity.png" alt-text="Screenshot of Unity package manager, install options for preview or public mesh toolkit.":::

1. Wait for the spinner in that list item to disappear.

## Preview developer tools

As a developer, you may desire to develop using the preview version of Microsoft Mesh. This gives developers access the upcoming version to test and prepare before the preview version is released to the public.

The release schedule generally follows this plan:

In the second week of the month, the Preview version is released to allow developers three full weeks to test.

After three weeks, the preview version is promoted to public and the cycle repeats.

To download the latest Mesh Toolkit or preview version, see the
[Mesh Toolkit for Unity | GitHub](https://github.com/microsoft/Mesh-Toolkit-Unity/releases).

>[!Caution]
>This is a preview release of the Mesh Toolkit noted by a **-preview** tag at the end of the version number.  Environments published with this preview version of the Mesh Toolkit will only work with the preview version of Mesh, and **are not compatible with the stable version of Mesh**. If you don't have access to Mesh preview, do not upgrade to this version of the Mesh Toolkit until a stable version is released.  Stable versions will not have a **-preview** tag at the end of the version number.  
> 
> **Be careful that you don't overwrite environments currently in use by your company with the preview version.**

## Next steps

> [!div class="nextstepaction"]
> [Building for single and multiple platforms](build-for-single-and-multiple-platforms.md)
