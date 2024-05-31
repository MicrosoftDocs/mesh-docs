---
title: Add the Mesh toolkit package
description: Instructions for adding the Mesh toolkit package to your project.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 5/29/2024
ms.topic: overview
keywords: Microsoft Mesh, getting started, toolkit, Mesh toolkit, import, registry, scoped registry, packages
---

# Add the Mesh toolkit package

With the Mesh toolkit package installed in Unity, you can use your 3D world-building skills to create fully customized multi-user 3D experiences. Mesh itself does the heavy lifting to enable engagement in 3D environments by handling the avatar system, Spatial Audio, and multi-user synchronization, but you have control over environment development, iteration, performance optimization and publishing through the Mesh toolkit. If you're already an intermediate to advanced Unity user, you can build environments in a familiar way and leverage existing scenes and assets to create Mesh experiences. You can add interactive content, insert logic, integrate with business data, or infuse AI--all with physics and interaction tools that you can leverage out-of-the-box.

When you install the Mesh toolkit, it does the following:

- Adjusts your Unity project's settings to match Mesh. This modifies several files in the *ProjectSettings* folder (for example, *GraphicsSettings.asset*).
- Ensures that OpenXR is enabled and adjusts the XR settings. To see these settings, on the menu bar, select **Edit** > **Project Settings** > **XR Plug-in Management**.
- Ensures that *TextMeshPro* is configured and sets its default font to "Segoe UI Fluent Semibold SDF".

**To add the Mesh toolkit package(s) to your Unity project**:

1. Open your Unity project, and then on the menu bar, select **Edit** > **Project Settings** > **Package Manager**.

1. Add a scoped registry with the following details:

   - **Name:** Mesh Toolkit

   - **URL:** https://registry.npmjs.org

   - **Scopes(s):** com.microsoft

   ![A screenshot of the Project Settings window with the Package Manager Scope Registry Configuration displayed.](../../media/build-your-basic-environment/Microsft-Mesh-toolkit-download-package-install-proper-name.png)

1. Click the **Save** button.
1. Close the **Project Settings** window, and then, on the menu bar, go to **Window** > **Package Manager**.

1. In the toolbar, click the **Packages** dropdown and then select **My Registries**.

   ![A screenshot of the Package Manager with the Packages drop down highlighted.](../../media/build-your-basic-environment/001-packages-drop-down.png)

1. In the list, you'll see the current build of the **Microsoft Mesh Toolkit**. 

    Select **Microsoft Mesh Toolkit** (the full package name should be **com.microsoft.mesh.toolkit**, as highlighted in the image below) and then click the **Install** button.

    :::image type="content" source="../../media/build-your-basic-environment/002-mesh-toolkit-in-package-manager.png" alt-text="A screenshot of the Unity package manager showing details of the preview Mesh toolkit.":::

When the spinner animation next to the package list stops, the package has finished downloading.

> [!NOTE]
> For versions of the toolkit prior to 5.2406.X, we released both a stable build and a preview build. Starting with version 5.2406.X, there's no longer a preview build. This change also applies to the Microsoft Mesh application; the preview version is deprecated and will no longer be released.

**To download the latest Mesh toolkit via GitHub**:
See the [Mesh Toolkit for Unity | GitHub](https://github.com/microsoft/Mesh-Toolkit-Unity/releases).

## Next steps

> [!div class="nextstepaction"]
> [Building for single and multiple platforms](build-for-single-and-multiple-platforms.md)
