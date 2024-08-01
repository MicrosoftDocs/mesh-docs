---
title: Mesh 101 Prepare the project
description: Learn about adding a few basic features that are necessary for the Mesh 101 tutorial project.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 8/1/2024
ms.topic: Tutorial
keywords: Microsoft Mesh, getting started, Mesh 101, tutorial
---

# Mesh 101 Tutorial Chapter 2: Prepare the project

<br>

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=c6b989b4-6634-4c4d-a1f7-2aa38ab3cd70]

<br>

## Scenes in the project

1. Open the **Mesh101** project in Unity. If you have more than one version of Unity installed, be sure to open the project with `Unity 2022.3.34` which is required for this tutorial.


2. In the **Assets** folder, there are two scenes available: **Starting Point** and **Finished Project**.

    ![A screenshot of a computer Description ](../../../media/sample-mesh-101/image010.png)

1. Open the **StartingPoint** scene. 

### About the Scenes

**StartingPoint**: This is the scene you'll do the tutorial in. It
contains a pre-built setting that includes the wind turbines and
stations you'll be visiting and adding Mesh features to.

**FinishedProject**: As the title implies, this scene contains an
accurate completed version of the tutorial. You can refer to this at any
time to confirm that you've completed tutorial steps in the
*StartingPoint* scene correctly. Always save your work in the
*StartingPoint* scene before switching scenes.

### Turn object icons off for a clearer view

Many objects appear in a scene with 3D icons displayed by default. This can help you identify the objects, but it can also clutter the view and make objects harder to see. 

![A screen shot of the Scene view with gizmos and icons cluttering the view.](../../../media/sample-mesh-101/499-scene-with-icons-displayed.png)

Let's turn off 3D icons to make the view more clear.

1. In the toolbar above the upper right corner of the **Scene** window, select the Gizmos drop-down.

    ![A screen shot of the gizmos drop down button.](../../../media/sample-mesh-101/503-gizmos-drop-down.png)

1. Slide the **3D icons** slider all the way to the left.

    ![A screen shot of the 3D icons slider.](../../../media/sample-mesh-101/518-3d-icons-slider.png)

    This will make it easier to read info dialogs, labels on buttons, and more.

    ![Screenshot of the Scene view with icons turned off and a clearer view of objects.](../../../media/sample-mesh-101/504-view-with-icons-turned-off.png)

### Exploring the *StartingPoint* scene

Feel free to move around in the **Scene** window to get familiar with
the scene's contents. If we zoom out a little, we can see that there are
a number of wind turbines in our wind farm. Those two white rounded
items are called *Sphere Terraces*.

![A screenshot of a computer Description ](../../../media/sample-mesh-101/image013.jpg)

When viewing the sphere terraces from the front, you can see that each one contains a space inside that
you'll soon be walking around in.

![A screenshot of a computer Description ](../../../media/sample-mesh-101/013-sphere-terraces-v2.png)

You'll be visiting the Sphere Terraces starting in the next chapter---they each contain a series of stations where you'll learn how to implement Mesh features. The first Sphere Terrace (covered in Chapter 3) is where you'll learn about Mesh Visual Scripting ...

![A screenshot of a video game Description ](../../../media/sample-mesh-101/014-chapter3-sphere-terrace-v2.png)

... and the other Sphere Terrace, covered in Chapter 4, is where you'll
learn about Mesh Interactables and Mesh Physics.

![A screenshot of a computer Description ](../../../media/sample-mesh-101/014-chapter-4-sphere-terrace-v2.png)

### Using Play Mode with Mesh Emulation

When you press the Unity Editor Play button, your project automatically uses *Mesh Emulation*. This is made possible by the presence of the **MeshEmulatorSetup [NoUpload]** prefab which you can view in the **Hierarchy**.

![A screenshot of the Mesh Emulator prefab in the Hierarchy.](../../../media/sample-mesh-101/520-mesh-emulator-in-hierarchy.png)

In earlier versions of the tutorial, you needed to add this prefab intentionally when you first entered Play mode. As of mid-May 2024, the prefab comes pre-loaded into the scene.

In Play Mode with Mesh Emulation, you get an approximate preview of what the content will look and feel like when it runs in the Mesh app. The Emulator prefab provides you with a highly stylized avatar controller that has a camera attached, so now when we "play" the project we can have a look around. By default, the Mesh Emulator is set up to give you a single view in the **Game** window. 

![A picture containing screenshot, pc game, video game software,3d modeling Description automatically generated](../../../media/sample-mesh-101/016-playmode-v2.png)

A key feature of Play Mode with Mesh Emulation is the ability to run multiple clients within the same process; this allows you to easily get a first impression of a multi-user scenario. In the future, you may want to have two or more views in Mesh Emulator mode. To do this, you can navigate to the Emulator's **Mesh Emulator Setup** component in the **Inspector** and then change its **Initial Screen Count** property to 2 (or more).

![A screenshot of the Mesh Emulator Setup No Upload prefab added to the Hierarchy.](../../../media/sample-mesh-101/508-emulator-component-single.png)

For this tutorial, we'll stay with the single view.

1. Press the Unity Editor Play button to enter Play mode.
1. Use the <kbd>W</kbd><kbd>A</kbd><kbd>S</kbd><kbd>D</kbd> keys to walk around inside the Sphere Terrace. You can also use the arrow keys or drag the right mouse button to pan in any direction. When you're done experimenting, click the Unity Editor Play button again to exit Play mode.

### Check the scale of your GameObjects

The tutorial project uses default Unity scale values: 1 unit = 1 meter.
The *MeshEmulatorSetup* avatar is the same height as an average human. When
you're creating your own Environment, you can compare its size to any
custom `GameObject` you add to your project to ensure that those objects
are the size you want.

### Add the Mesh Thumbnail Camera

Adding the `Mesh Thumbnail Camera` provides a thumbnail image that will be
added to your Environment's listing in Mesh on the web and its
selection button in the Mesh app. This comes in handy when you're
selecting Environments in either place because it gives you a visual
reminder of what the Environment looks like.

**To add the thumbnail camera to the scene and set its view:**

1. In the **Scene** window, adjust the view so that it shows what you
    want to display in the thumbnail image (the Thumbnail Camera's view will
    be based on the **Scene** window).

1. Select the "+" drop-down located below the **Hierarchy** tab, and
    then select **Mesh Toolkit** > **Thumbnail Camera**.

1. To see what your thumbnail will look like, view the small **MeshThumbnailCamera** window which appears in the lower right corner of the **Scene** window. 

    ![A screen shot of the Mesh thumbnail camera highlighted in the Hierarchy and the camera's view highlighted in the Scene view.](../../../media/sample-mesh-101/509-thumbnail-camera-view.png)

> **Note**: If you decide you want a different view for the Thumbnail
Camera, the easiest way to achieve this is to delete the Camera, establish the **Scene** view that you want, and then add the Camera again. You can also adjust the Camera GameObject directly in the **Scene**
window or change its **Position** and **Rotation** values in the
**Inspector** prior to uploading your Environment to Mesh.

There are no set rules for how your thumbnail should look---it's totally
up to you. For the example below, we chose a close-up front view of a
wind turbine.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image020.jpg)

## Next steps

> [!div class="nextstepaction"]
> [Chapter 3: Add interactivity with Mesh Visual Scripting](mesh-101-03-visual-scripting.md)