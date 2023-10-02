---
title: Set up your scene
description: Learn how to set up a scene in Unity for Mesh development.
author: vtieto
ms.author: vinnietieto
ms.date: 10/2/2023
ms.prod: mesh
ms.topic: How to
keywords: Microsoft Mesh, Unity, getting started, documentation
---

## Set up your scene

## Add a Navmesh

<TBD>

## Add a TravelPoint

Every scene must have at least one TravelPoint, which is used to configure avatar spawning behavior. If you're new to TravelPoints, we recommend that you [read our TravelPoint and TravelGroup documentation](../enhance-your-environment/object-avatar-interactions.md#travelpoint-and-travelpointgroup) and follow the instructions there. When you're finished, continue on with the article named [Building for single and multiple platforms](build-for-single-and-multiple-platforms.md).

## Add the Mesh Thumbnail Camera

Adding the `Mesh Thumbnail Camera` provides a thumbnail image that will be
added to your Environment's listing in the Azure Portal and its
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
up to you. For the example below, we chose a close-up front view of a
wind turbine.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image020.jpg)
