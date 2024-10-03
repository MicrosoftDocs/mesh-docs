---
title: Mesh toolkit Toybox package
description: Learn about the Mesh toolkit Toybox package.
author: vtieto
ms.author: vinnietieto
ms.date: 10/03/2024
ms.topic: overview
ms.service: mesh
keywords: Microsoft Mesh, getting started, samples, tutorials, features, physics, toybox, interactables
---

# Mesh toolkit Toybox package

The Mesh toolkit Toybox package contains the prefabs and assets that are found in the activities in the Mesh Pavilion sample and much more. The package is named *com.microsoft.mesh.toolkit.toybox* and can be found in File Explorer in the *Packages* folder.

![A screen shot of the Toybox package in File Explorer.](../../../media/samples/010-toybox-pkg-in-file-explorer.png)

Here's how it looks in the Unity project.

![A screen shot of the Toybox package in the Unity project.](../../../media/samples/009-toybox-package.png)

## Add the Toybox package to an existing project

There are a couple of ways to add the Toybox package to your project.

- Copy and paste the *com.microsoft.mesh.toolkit.toybox* folder located in the [Packages](https://github.com/microsoft/Mesh-Toolkit-Unity/tree/main/Packages) folder into your project's Packages folder.
- Reference the Toybox package from GitHub.

> [!IMPORTANT]
> To reference the Toybox package from GitHub you must have [Git](https://gitforwindows.org/) installed on your computer.

**To import Toybox into your Unity project using GitHub**:

1. In your project, on the menu bar, select **Window** > **Package Manager**.
1. In the *Package Manager*, click the '+' drop-down and then select "Add package from git URL..."

    ![A screen shot of Add package from Github menu option.](../../../media/samples/011-add-package-with-github.png)

1. Paste <https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.toybox> into the text field and then click **Add**.

    ![A screen shot of the toybox URL pasted into the Github text box.](../../../media/samples/012-add-github-url.png)

Toybox will now be installed in your Unity project as a package in the project's *Packages* folder with the name  *Microsoft Mesh Toolkit Toybox*.

> [!TIP]
> We recommend that you use a specific release of the Toybox package to ensure your project is locked to a release.

You can reference a specific release version, branch, or Git commit hash by altering the URL in step 3 as demonstrated below:

| Syntax           | URL example                                                                                                                                     |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Specific version | <https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.toybox#vX.Y.Z>                                   |
| Specific branch  | <https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.toybox#my_branch>                                |
| Git commit hash  | <https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.toybox#badc0ffee0ddf00ddead10cc8badf00d1badb002> |
