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

1. Select **Microsoft Mesh Toolkit** in the list and click the **Install** button in the right pane.

1. Wait for the spinner in that list item to disappear.

## Next steps

> [!div class="nextstepaction"]
> [Building for single and multiple platforms](build-for-single-and-multiple-platforms.md)
