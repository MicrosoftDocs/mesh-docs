---
title: Set up your scene
description: Learn how to set up a scene in Unity for Mesh development.
author: vtieto
ms.author: vinnietieto
ms.date: 11/1/2023
ms.service: mesh
ms.topic: How to
keywords: Microsoft Mesh, Unity, getting started, Unity, scene, teleportation, navmesh, travelpoint, travelgroup, player movement
---

# Set up your scene

The operations below are required for new or existing projects.

## Guidelines for Player Movement

The scene should have Colliders for the player to walk and teleport on. In general, a low poly MeshCollider that tightly fits the visual geometry with some rounding on the corners will produce the best results. Box Colliders work great for trivial scenarios, but can result in a number of problems such as causing the player to get stuck on the corners or defeat step height limits.  

**Mesh Player CharacterController movement limits:**
- Maximum walkable slope: <45 degrees
- Maximum step height: 0.3
- Player capsule radius: 0.3
- Player capsule height: 1.9

**Suggestions for best results:**
- Rounded corners help smooth out player movement and prevent the player from getting stuck.  
- To block player movement, use steep slopes or a height much larger than the maximum step height.
- Use a Capsule Collider or similar rounded shape on objects or areas the player shouldn't walk on. These shapes are unwalkable due to the slope and will cause the player to slide off them. Do not add to the NavMesh layer.
- Align the collision surfaces with the visual surfaces that the player will walk on. This is important in order to avoid any issues with the player's position relative to the visual surface (prevent floating or clipping).  

## Supporting Teleportation

In order for a scene to support teleportation, teleportable surfaces (for example, the floor or the ground) must have colliders on the NavMesh layer. In general, any object the player is allowed to walk on should be on the NavMesh layer, unless there is an intentional reason to make it non-teleportable. Visual geometry isn't teleportable and shouldn't be on the NavMesh layer; only Colliders can be on the NavMesh layer. Improper or inconsistent layering can cause undesirable effects when teleporting. 

**A teleportable surface must meet the following conditions:**  
- It must have some type of Collider attached (Mesh Collider or Box Collider, for example).  
- Its **Layer** must be set to NavMesh.  

Be cautious of low ceilings or tunnels; these could potentially affect player grounding and teleportation.  For example, player physics or the teleport arc may intersect or interact with the collider above them. There should be a small buffer of space above the player's head. The minimum height from ground to roof is roughly 3m (~2m player height + ~1m buffer).

- It must have some type of Collider attached (Mesh Collider or Box Collider, for example).  
- Its Layer must be set to Navmesh.

## Add a TravelPoint

Every scene must have at least one *travel point*, which is used to configure avatar spawning behavior. If you're new to travel points, we recommend that you [read our TravelPoint and TravelGroup article](../enhance-your-environment/avatar-and-object-interactions/create-avatar-spawn-and-teleport-points.md) and follow the instructions there.

## Add the Mesh Thumbnail Camera

Every time you upload your Environment, a thumbnail image of your scene will be captured based on the *TravelPoint* component and *LookAt* property using the *MeshThumbnailCamera*; however, you can also add your own *MeshThumbnailCamera* and position it wherever you like. The *Mesh Thumbnail Camera* provides a thumbnail image that will be
added to your Environment's listing in Mesh on the web and its
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

> **Note 1**: If you decide you want a different view for the Thumbnail
> Camera, you can adjust the Camera GameObject directly in the **Scene**
> window or change its **Position** and **Rotation** values in the
> **Inspector** prior to uploading your Environment to Mesh.

> - You can also add the camera as a child of a GameObject: right-click the GameObject and then select **Mesh Toolkit** > **Thumbnail Camera**. The camera position in this case will be 0 so it's important to adjust the position and rotation.

There are no set rules for how your thumbnail should look---it's totally
up to you. The example below is taken from our [Mesh 101 tutorial](../../develop/getting-started/mesh-101-tutorial/mesh-101-01-overview-and-setup.md). The tutorial teaches you how to add Mesh features to an educational experience about wind turbines, so the thumbnail shows the turbines.

![A screenshot of a computer Description automatically generated](../../media/get-started-developing-mesh/001-thumbnail-example.png)

## Next Steps

> [!div class="nextstepaction"]
> [Environment construction tips](./environment-construction-tips.md)
