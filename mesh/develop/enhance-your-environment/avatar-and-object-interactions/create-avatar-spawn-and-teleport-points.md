---
title: Create avatar spawn and teleport points
description: Learn how to create points that an avatar will spawn to or travel to when using teleportation.
author: jackiecurley
ms.author: vinnietieto
ms.date: 10/4/2023
ms.topic: overview
keywords: Microsoft Mesh, object and player interactions, interactables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw, teleport, spawn
---

# Create avatar spawn and teleport points

## TravelPoint and TravelPointGroup

TravelPoints are a component in the Interactables package that can be used to define where to place an avatar when first joining an event or space and also to transport avatars during their experience using Visual Scripting.

If a TravelPoint is not present in an Environment, and there is a floor at the origin, the avatar will be grounded on the floor when spawned.  If no floor is present near the origin, the avatar will spawn above the origin and fall for a little while and then respawn in a loop.

Setting up Travel Groups and Travel Points:

1. Create a Travel Point Group: all travel points must belong to a group; a default group will be assigned to any travel points that don't have one. Every travel group must have a unique name. The default travel group will not be set as a DefaultSpawnGroup unless it is the only group that exist.

    - To do this, create a new GameObject with a TravelPointGroup component attached.

    ![Travel Point Group](../../../media/mesh-scripting/object-player-interactions/006-travel-point-group.png)

2. Add Travel Points to the group. To do this, add new GameObjects as children of the Travel Point Group with a Travel Point Component attached.

    ![Travel Point Component attached](../../../media/mesh-scripting/object-player-interactions/007-travel-point.png)

    ![Travel Point](../../../media/mesh-scripting/object-player-interactions/008-travel-point-in-hierarchy.png)
    
3. Set "Default Spawn Group" to true for travel groups you want avatars to spawn into when initially joining an Event or space and false travel groups that you do not.  

### Settings

**Travel Point**
- **Look At Transform:** the point you want the camera to look at after spawning into that transform. This will default to CenterTransform forward.  
- **Radius:** the size of the travel area. It’s a circle around the center transform.  
- **Single Travel:** If this is true, only one avatar at a time will spawn into this point unless there are no more points to choose from.

**Travel Point Group**
- **Default Spawn Group:** When true this group will be used for finding the default spawn point for an avatar entering a space

### Visual Scripting

- **Travel Point Methods:**
    - **TravelToPoint** – Transport the local avatar directly to a specific travel point
- **Travel Point Group Methods:**
    - **TravelToRandomTravelPoint()** – Transport the local avatar to a random point in the group