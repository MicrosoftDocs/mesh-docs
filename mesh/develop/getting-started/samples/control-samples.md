---
title: Control samples
description: Read an overview of the control samples available in the Mesh toolkit.
author: vtieto
ms.author: vinnietieto
ms.date: 05/10/2024
ms.topic: overview
ms.service: mesh
keywords: Microsoft Mesh, getting started, samples, tutorials, features, toolkit, Mesh toolkit, control samples
---

# Mesh Control Samples

## Overview

The Control Samples package provides user interface controls built using the Mesh Toolkit. Controls are authored using Mesh scripting and Graphics Tools. We want to you have access to these features, but since they're still in development we call them "samples" to indicate that they're evolving and are subject to change over time.

## Getting started

The Control Samples package is included when you [download the Mesh samples from GitHub](./download-mesh-samples.md).

![Screen shot of the Control Samples package in File Explorer.](../../../media/samples/control-samples/001-control-samples-package.png)

**To add the Control Samples package to your project**:

1. In your Unity project on the menu bar, select **Window** > **Package Manager**.
1. Click the '+' drop-down and then select **Add package from git URL...**.

![Screen shot of the Package Manager menu with Add package from disk menu item highlighted.](../../../media/samples/control-samples/002-add-package-from-disk.png)

1. In the **Select package on disk** window, navigate to the folder named *com.microsoft.mesh.toolkit.control.samples* and then double-click the *package.json* file.

![Screen shot of the package.json file in File Explorer.](../../../media/samples/control-samples/003-package-json-file.png)

1. The Control Samples package appears in the Package Manager tagged as "Local" ...

![Screen shot of the Control Samples package in the Package Manager.](../../../media/samples/control-samples/004-control-samples-package-in-package-manager.png)

... and can be found in the **Project** > **Packages** folder.

![Screen shot of the Control Samples package in the Packages folder.](../../../media/samples/control-samples/005-control-samples-in-packages-folder.png)

=====

1. Copy and paste the *com.microsoft.mesh.toolkit.control.samples* folder located in this repository's `Packages` folder into your project's `Packages` folder, or b) reference the Control Samples package from GitHub. To use this second method, follow these steps:

1. In Unity select `Window > Package Manager` from the file menu bar

1. Click the `'+'` icon within the Package Manager and select `"Add package from git URL..."`

    ![Package Manager Add](README~/PackageManagerAdd.png)

1. Paste *https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.control.samples* into the text field and click `"Add"`

    ![Package Manager Paste](README~/PackageManagerPaste.png)

The Control Samples will now be installed within your Unity project as package within the project's `Packages` folder named `Microsoft Mesh Toolkit Control Samples`. You can now start using prefabs and visual scripts within the Control Samples' runtime folder.

## List of controls

In the Runtime folder you will find the following prefab controls:

- **BackplateBase.prefab** - Use this prefab to plate all of your controls on a backplate with rounded corners and an iridescent surface.
- **ButtonBase.prefab** - This prefab is the base prefab used for all button variants. The button animates, produces audio feedback when pressed and contains a label. Use `Visual Scripting` to hook application logic to button presses.
- **InformationButton.prefab** - This is the prefab for a floating world space coin button. The button features proximity detection via the `Avatar Trigger` behavior: When player enters button range, coin stops spinning and is billboarded instead and player is able to click coin. If player is out of range, they are no longer able to click on the button and button returns to spinning. The button interactable behavior is driven by OCL's `Mesh Interactable Properties` and `Visual Scripting`.
- **Earth.prefab** - This prefab for an Earth globe that can be spun and selected. When selected the globe generates a latitude and longitude position and adds a marker. This functionality can be extended and modified with `Visual Scripting`. All actions are shared by all clients by default.