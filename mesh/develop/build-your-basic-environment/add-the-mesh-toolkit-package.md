---
title: Add the Mesh Toolkit package
description: Instructions for adding the Mesh Toolkit package to your project.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 11/03/2023
ms.topic: overview
keywords: Microsoft Mesh, getting started, toolkit, Mesh toolkit, import, registry, scoped registry, packages
---

# Add the Mesh Toolkit package

The Mesh Toolkit enables creators and developers to build custom 3D environments and experiences with Unity.

Mesh has a public build where all users can experience custom worlds and a corresponding toolkit for developers who wish to create custom environments or artifacts to be used in immersive experiences.

**To add the Mesh Toolkit package to your Unity project**:

1. Open your Unity project, and then on the menu bar, select **Edit** > **Project Settings** > **Package Manager**.

1. Add a scoped registry with the following details:

   - **Name:** mesh.toolkit.preview

   - **URL:** https://registry.npmjs.org

   - **Scopes(s):** com.microsoft

   ![A screenshot of the Project Settings window with the Package Manager Scope Registry Configuration displayed.](../../media/build-your-basic-environment/configure-scoped-registry.png)

1. Close the **Project Settings** window, and then, on the menu bar, go to **Window** > **Package Manager**.

1. In the toolbar, click the **Packages** dropdown and then select **My Registries**.

   ![A screenshot of the Package Manager with the Packages drop down highlighted.](../../media/build-your-basic-environment/001-packages-drop-down.png)

1. In the list, select **Microsoft Mesh Toolkit** and then click the **Install**  button. You can select the version, install a preview version, and update/remove versions.

    :::image type="content" source="../../media/build-your-basic-environment/Microsft-Mesh-toolkit-download-package-install-unity.png" alt-text="A screenshot of the Unity package manager showing details of the preview Mesh Toolkit.":::

When the spinner animation next to the package list stops, the package has finished downloading. 

## Microsoft Mesh preview

In addition to the stable release builds, we offer a preview build and preview toolkit. These are ideal for developers who want to test out upcoming features and prepare in advance for the next public build.

We promote the preview build to the stable public build at regular intervals. Currently (November 2023), this happens every three weeks.

> [!Caution]
> This is a preview release of the Mesh Toolkit noted by a **-preview** tag at the end of the version number.  Environments published with this preview version of the Mesh Toolkit will only work with the preview version of Mesh, and **are not compatible with the stable version of Mesh**. If you don't have access to Mesh preview, don't upgrade to this version of the Mesh Toolkit until a stable version is released. Stable versions won't have a **-preview** tag at the end of the version number.  
>
> **Be careful not to overwrite Environments currently in use by your company with the preview version.**

**To download the latest Mesh Toolkit or preview version**:
See the [Mesh Toolkit for Unity | GitHub](https://github.com/microsoft/Mesh-Toolkit-Unity/releases).

## Next steps

> [!div class="nextstepaction"]
> [Building for single and multiple platforms](build-for-single-and-multiple-platforms.md)
