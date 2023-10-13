---
title: Set up your scene
description: Learn how to set up a scene in Unity for Mesh development.
author: vtieto
ms.author: vinnietieto
ms.date: 10/10/2023
ms.prod: mesh
ms.topic: How to
keywords: Microsoft Mesh, Unity, getting started, Unity, scene, teleportation, navmesh, travelpoint, travelgroup
---

# Set up your scene

The operations below are required for new or existing projects.

## Setting up teleportation

In order for a scene to support teleportation, it must have a Navmesh layer. A teleportable surface (for example, a floor or the ground) doesn’t need a Navmesh, but it must meet the following conditions:

--It must have some type of Collider attached (Mesh Collider or Box Collider, for example).
--Its Layer must be set to Navmesh.

## Add a TravelPoint

Every scene must have at least one *travel point*, which is used to configure avatar spawning behavior. If you're new to travel points, we recommend that you [read our TravelPoint and TravelGroup article](../enhance-your-environment/avatar-and-object-interactions/create-avatar-spawn-and-teleport-points.md) and follow the instructions there. When you're finished, continue on with the article named [Building for single and multiple platforms](build-for-single-and-multiple-platforms.md).

## Add the Mesh Thumbnail Camera

Adding the *Mesh Thumbnail Camera* provides a thumbnail image that will be
added to your Environment's listing in the Mesh Portal and its
selection button in the Mesh app. This comes in handy when you're
selecting Environments in either place because it gives you a visual
reminder of what the Environment looks like.

**To add the thumbnail camera to the scene and set its view:**

1. In the **Scene** window, adjust the view so that it shows what you
    want to display in the thumbnail (the Thumbnail Camera's view will
    be based on the **Scene** window).

2. Select the "+" drop-down located below the **Hierarchy** tab, and
    then select **Mesh Toolkit** > **Thumbnail Camera**.

3. To confirm that the view in the Thumbnail Camera is what you want,
    in the **Hierarchy**, select **MeshThumbnailCamera**. The Camera's
    view appears in a small window in the lower right of the **Scene**
    window.

> **Note**: If you decide you want a different view for the Thumbnail
> Camera, you can adjust the Camera GameObject directly in the **Scene**
> window or change its **Position** and **Rotation** values in the
> **Inspector** prior to uploading your Environment to Mesh.

There are no set rules for how your thumbnail should look---it's totally
up to you. The example below is taken from our [Mesh 101 tutorial](../../develop/getting-started/mesh-101-tutorial/mesh-101-01-overview-and-setup.md). The tutorial teaches you how to add Mesh features to an educational experience about wind turbines, so the thumbnail shows the turbines.

![A screenshot of a computer Description automatically generated](../../media/get-started-developing-mesh/001-thumbnail-example.png)

## Next Steps

To enhance your project with features such as Web content, Mesh Interactables, or Mesh Physics, go to:

> [!div class="nextstepaction"]
> [Enhanced features overview](../enhance-your-environment/enhanced-features-overview.md)

If you're interested in some of the more artistic elements of experience creation such as modeling, texture, and lighting, go to:

> [!div class="nextstepaction"]
> [Design overview](../design/overview.md)
