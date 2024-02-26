---
title: Mesh toolkit Dart Room sample
description: Learn about the Mesh toolkit Dart Room sample.
author: vtieto
ms.author: vinnietieto
ms.date: 2/2/2024
ms.topic: overview
ms.service: mesh
keywords: Microsoft Mesh, getting started, samples, tutorials, features, physics, dartroom
---

# Microsoft Mesh toolkit Sample: Dart Room

![Gallery View](../../../media/samples/003-dartroom.png)

The *Dart Room* project (scene: *DartRoom*) contains a carefully designed scene that demonstrates the power of combining appealing visuals with the creative use of Mesh Physics features found in the Mesh toolkit. Feel free to inspect and modify the scene and play with it!.

In this project, you'll find:

* **Cups**: Simple objects to pick up.
* **Tables**: When grabbed, they try to align themselves with gravity.
* **Cupboards**: These should feel heavy. They use physics constraints.
* **Reset buttons** (red): Resets the transforms of a sub-scene.
* **Clock pendulums**: Powered by a physics hinge and velocity field.
* **Darts**: You can throw these in the camera direction. They're "sticky," so they'll stay attached to anything they hit.
* **Globe**: The globe rotates, demonstrating a motored hinge. The globe also has a gravity field which influences small objects entering a spherical trigger volume. Drag some cups close to the globe and watch them rotate around it like satellites.

![A screenshot of the gravity globe in the Dartroom sample.](../../../media/samples/004-dartroom-gravity-globe.png)

The [Samples Overview](samples-overview.md) page contains instructions on how to download the Mesh toolkit which contains this sample.

## Warning about sample load time

The sample could take 15 minutes or slightly longer to load into Unity due to large asset sizes. If you need to, change your Sleep mode setting so that the computer doesn't go to sleep while the project is loading. If this happens, it could cause the project to not load properly.

## Contributions

We are not currently accepting code contributions to our samples.  If you have any feedback or if you run into any issues with the samples or the Mesh toolkit, do the following: in a Unity project that has the Mesh toolkit package installed, select **Mesh Toolkit** -> **Give feedback to Microsoft** and then use the feedback link in the Mesh toolkit to let us know.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## License

The Mesh sample in this project is governed by the MIT license as shown in the [LICENSE.MD](https://github.com/microsoft/Mesh-Toolkit-Unity/blob/main/LICENSE) file in the *Mesh-Toolkit-Unity* repository. However, the samples functionality is dependent on the Mesh toolkit, which is governed by a separate license, and contains 3rd party software. 
