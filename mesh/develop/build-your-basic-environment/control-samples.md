---
title: Use prebuilt user interface controls
description: Read an overview of the user interface control prefabs available in the Mesh toolkit.
author: vtieto
ms.author: vinnietieto
ms.date: 10/03/2024
ms.topic: overview
ms.service: mesh
keywords: Microsoft Mesh, getting started, samples, tutorials, features, toolkit, Mesh toolkit, sample objects, UI, user interface, environments
---

# Use prebuilt user interface controls

## Overview

The Control Samples package provides prebuilt user interface controls built using the Mesh Toolkit that you can import into your projects. We use them extensively in our [Mesh 101](../getting-started/mesh-101-tutorial/mesh-101-01-overview-and-setup.md) and [Mesh 201](../getting-started/mesh-201-tutorial/mesh-201-01-overview-set-up-and-get-started.md) tutorials.

![Screen shot of several control samples in the Mesh 101 tutorial.](../../media/build-your-basic-environment/control-samples/016-controls-in-use.png)

The control samples are still in development so we call them "samples" to indicate that they're evolving and are subject to change over time. Details about the control samples are given in the [Control Samples in detail section](#control-samples-in-detail) further down this page, but here's a quick look at how we use them in our tutorials.

**BackplateBase**

Since a backplate is such a useful supporting object for any informational text display, we use the BackplateBase prefab in quite a few places.

![Screen shot of the numerous instances of the BackplateBase prefab in the Mesh 101 tutorial.](../../media/build-your-basic-environment/control-samples/011-backplatebase-instances.png)

One example: In the Mesh 101 tutorial, BackplateBase can be found as a child object to **ChapterLabel** which is the information text display for the first station, **3.1: Video Playback**.

![Screen shot of a BackplateBase instance in the Mesh 101 tutorial.](../../media/build-your-basic-environment/control-samples/012-backplatebase-one-example.png)

**ButtonBase**

In the Mesh 101 tutorial, the ButtonBase prefab is used to create the *Play* button for the video screen in the *3.1: Video Playback* station. Note that the prefab has been renamed here to "PlayVideoButton".

![Screen shot of a ButtonBase instance in the Mesh 101 tutorial.](../../media/build-your-basic-environment/control-samples//013-buttonbase-prefab.png)

**Earth**

In the Mesh 201 tutorial, the Earth prefab is used for *Station 4: Load a URL from a 3D asset*.

![Screen shot of an Earth prefab instance in the Mesh 101 tutorial.](../../media/build-your-basic-environment/control-samples/015-earth.png)

**InformationButton**

In the Mesh 101 tutorial, the InformationButton prefab is used for the *3.2: Info Dialog Trigger* station. Note that the prefab has been renamed slightly here to "Information_Button".

![Screen shot of an InformationButton instance in the Mesh 101 tutorial.](../../media/build-your-basic-environment/control-samples/014-information-button.png)

## Getting started

The Control Samples package is included when you [download the Mesh samples from GitHub](../getting-started/samples/download-mesh-samples.md).

![Screen shot of the Control Samples package in File Explorer.](../../media/build-your-basic-environment/control-samples/001-control-samples-package.png)

**To add the Control Samples package to your project**:

1. In your Unity project on the menu bar, select **Window** > **Package Manager**.
1. Click the '+' drop-down and then select **Add package from disk ...**.

![Screen shot of the Package Manager menu with Add package from disk menu item highlighted.](../../media/build-your-basic-environment/control-samples/002-add-package-from-disk.png)

1. In the **Select package on disk** window, navigate to the folder named *com.microsoft.mesh.toolkit.control.samples* and then double-click the *package.json* file.

![Screen shot of the package.json file in File Explorer.](../../media/build-your-basic-environment/control-samples/003-package-json-file.png)

1. The Control Samples package appears in the Package Manager tagged as "Local" ...

![Screen shot of the Control Samples package in the Package Manager.](../../media/build-your-basic-environment/control-samples/004-control-samples-package-in-package-manager.png)

... and can be found in the **Project** > **Packages** folder.

![Screen shot of the Control Samples package in the Packages folder.](../../media/build-your-basic-environment/control-samples/005-control-samples-in-packages-folder.png)

## Control Samples in detail

The Control Sample prefabs are in subfolders of the *Runtime* folder.

**Runtime** > **ButtonBase**

- **BackplateBase**: Use this prefab to place all of your controls on a backplate with rounded corners and an iridescent surface. 

![A Screen shot of the BackplateBase prefab in the scene.](../../media/build-your-basic-environment/control-samples/007-backplate-base.png)

- **ButtonBase**: The base prefab for all button variants. The button animates, produces audio feedback when pressed, and contains a label. Use *Visual Scripting* to set up events that trigger when an avatar clicks the button.

![A Screen shot of the ButtonBase prefab in the scene.](../../media/build-your-basic-environment/control-samples/008-buttonbase.png)

**Runtime** > **Globe**

- **Earth**: An Earth globe that spins and can be selected. When selected, the globe generates a latitude and longitude position and adds a marker. This functionality can be extended and modified with Visual Scripting. All actions are shared by all clients by default.

![A Screen shot of the Earth prefab in the scene.](../../media/build-your-basic-environment/control-samples/009-globe.png)

**Runtime** > **InformationButton**

- **InformationButton**: A floating world space coin button. The button features proximity detection through the `Avatar Trigger` behavior. When an avatar is a certain distance from the button, the coin stops spinning and is billboarded instead. The avatar is able to click the coin. If the avatar is out of range, it's no longer able to click on the button and the button returns to spinning. The button's interactable behavior is driven by its *Mesh Interactable Setup* component and the *InformationButton* script.  

![Screen shot of the InformationButton prefab in the scene.](../../media/build-your-basic-environment/control-samples/010-information-button.png)

## Next steps

> [!div class="nextstepaction"]
> [Samples overview](../getting-started/samples/samples-overview.md)
