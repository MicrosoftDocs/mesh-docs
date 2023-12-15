---
title: Configuring for avatar movement and teleportation
description: Learn how configure your environment so avatars move and teleport correctly.
author: vtieto
ms.author: vinnietieto
ms.date: 11/14/2023
ms.service: mesh
ms.topic: How to
keywords: Microsoft Mesh, Unity, getting started, Unity, scene, teleportation, avatars, teleporting, navigating, layers
---

# Configuring for avatar movement and teleportation

## Overview

In order for Mesh avatars to move around and teleport in your experience successfully, it's important to follow certain design guidelines. In this article, you'll get detailed information about the Layers provided by the Mesh Toolkit and how to ensure that the GameObjects in a Scene are assigned to the appropriate Layer. There are also some general tips for things such as avatar movement limits and collider design.

## Collision Layers

Interactable objects are GameObjects with a non-trigger collider and corresponding visual geometry on one of the object colliding layers.  Avatars can walk and be positioned onto objects with non-trigger colliders, so be mindful of what layer is being used.

To have accurate avatar positioning and teleportation, scene colliders need to be on the appropriate layers.  The local user's avatar will interact with (collide with and walk on) any colliders on the layers that support these interactions.

When the avatar is positioned or teleported, it's important that the avatar collides with a "ground" object and is consistently placed at the same height above the ground (this is called "grounding").  If no ground is detected, the avatar will fall.  This is acceptable if above ground (there is no falling damage!), but if the avatar is placed below the "ground" object, the avatar might fail to register a collision with that object,  causing it to fall out of the environment and respawn.  If the avatar penetrates the ground during repositioning, it will be grounded.

All the avatars in a session should be at a consistent height.  The avatar position is adjusted if its height changes out of range.  For example:

- A VR user physically goes to and from a seated or standing position. The HMD movement causes the avatar in the scene to penetrate the ground or be standing much higher vertically than other avatars.

-- A poorly configured visual script teleports the avatar into a position that they don't fit or is vertically too low.

Another reason this is important is that when the avatar physics updates, if the avatar isn't  grounded, it will jump into position as a result of its capsule colliding with the ground and yanking the avatar into the new position.  This is especially impactful for HMD users because unnatural movements like this can be nausea-inducing.

Layers the avatar interacts with and can walk on:

0 - Default  
2 - Ignore Raycast  
4 - Water (only trigger colliders allowed, not walkable)  
14 - GroundCollision (teleportable)  
18 - TriggerVolume (only trigger colliders allowed, not walkable)  
21 - IgnoreObjects  
26 - Custom26  
27 - Custom27  
28 - Custom28  
29 - IgnoreRealtimeLight  
30 - WallCollision

## Object Layers

When a GameObject has a non-trigger collider, it will collide with other objects if it's on one of the object layers.

0 - Default
2 - Ignore Raycast
4 - Water (only trigger colliders allowed)
14 - GroundCollision
18 - TriggerVolume (only trigger colliders allowed)
20 - ObjectCollision
26 - Custom26
27 - Custom27
28 - Custom28
29 - IgnoreRealtimeLight
30 - WallCollision
31 - IgnoreParticipant

The default layer in Unity is the layer named "Default", so you may need to use a different layer if you don't want to interact with other objects. For example, IgnoreParticipant is used for objects that shouldn't interact with the avatar and IgnoreCollisions is used for objects that shouldn't interact with anything.

## Some important layers

**Default**

If not otherwise specified, a Collider will be on the Default layer.  This is a walkable layer, and the avatar will be correctly grounded.  It is not a valid teleport target for the local user.  This layer interacts and collides with other objects.

**GroundCollision layer**

Only colliders on the GroundCollision layer are valid teleport targets for the local user.  It is otherwise identical to the Default layer.

Visual geometry not backed with collision is not walkable and does not block the avatar, so is an improper teleport target and should not be on the GroundCollision layer.

**WallCollision layer**

The WallCollision layer is used to indicate walls the avatar should not penetrate in order to constrain the avatar within a playable space.  VR users can move their avatars in arbitrary ways with HMD movement during roomscale locomotion and may physically walk through a virtual wall.  The avatar will be teleported back to the bounds of the play area after they have walked a set distance.  It otherwise identical to the Default layer.

## Layer Definitions

Defined layers by id and name, including blocking semantics and description:

0. Default

    *[Avatar/Object/Raycast Blocking]*

    Used for collision and lighting, avatar can walk on, but not teleport onto.  Default for most props.  Objects on the Default layer receive Realtime Directional Light from the environment.

1. TransparentFX

    *[Not Blocking]*

    Special handling in Unity's rendering pipeline for transparent and special effects objects; ensures correct rendering order for transparency.

2. IgnoreRaycast

    *[Avatar/Object Blocking]*

    Collision enabled layer that does not block raycasts, such as non-interactable objects or invisible walls that avatars cannot pass, but physics objects can pass through (ie. railings that objects can be thrown over, but avatars can't hop over).

3. n/a

4. Water

    *[Not Blocking]*

    Specifically for water surfaces - can be used for specialized rendering and physics interactions with water.  Do not use with non-trigger colliders.

5. n/a

6. n/a

7. n/a

8. n/a

9. n/a

10. n/a

11. n/a

12. n/a

13. n/a

14. GroundCollision

    *[Avatar/Object/Raycast Blocking]*

    Used for walkable collision surfaces that CAN be teleported onto.

15. n/a

16. n/a

17. IgnoreCollisions

    *[Not Blocking]*

    Doesn't interact with anything, can clip through the environment and other objects.

18. TriggerVolume

    *[Not Blocking]*

    Layer for objects that should not be affected by physics or raycasts and have no special usage otherwise.  Do not use on objects with non-trigger colliders.

19. n/a

20. ObjectCollision

    *[Object Blocking]*

    Layer to collide with objects but not the avatar or raycasts.

21. IgnoreObjects

   * [Avatar/Raycast Blocking]*

    Layer to collide with avatar but not objects.

22. RaycastOnly

    *[Raycast Blocking]*

    Layer for objects that block raycasts or can be selected but don't affect avatar or object collision.

23. n/a

24. n/a

25. n/a

26. Custom26

    *[Avatar/Object/Raycast Blocking]*

    User custom defined layer.

27. Custom27

    *[Avatar/Object/Raycast Blocking]*

    User custom defined layer.

28. Custom28

    *[Avatar/Object/Raycast Blocking]*

    User custom defined layer.

29. IgnoreRealtimeLight

    *[Avatar/Object/Raycast Blocking]*

    Specify which art objects in the environment DON'T receive realtime directional light, such as most static objects (use baked lighting instead via the lightmap).

30. WallCollision

    *[Avatar/Object/Raycast Blocking]*

    Collision which prevents clipping through a scene. If an HMD user sticks their head through the wall, they are respawned to a nearby location on the playable area.

31. IgnoreParticipant

    *[Object/Raycast Blocking]*

    Objects that block raycasts and other objects, but not avatars.

## Layer Table

Builtin Layers
Mesh Layers
Custom Layers

LayerId Layer   Is An Object    Object Collision    Partcipant Collision    Teleport Target Blocks Raycast
0   Default ✅   ✅   ✅   ❌   ✅
1   TransparentFX   ❌   ❌   ❌   ❌   ❌
2   IgnoreRaycast   ✅   ✅   ✅   ❌   ❌
4   Water   ❌   ✅   ✅   ❌   ✅
14  GroundCollision ✅   ✅   ✅   ✅   ✅
17  IgnoreCollisions    ❌   ❌   ❌   ❌   ❌
18  TriggerVolume   ❌   ✅   ✅   ❌   ❌
20  ObjectCollision ✅   ✅   ❌   ❌   ❌
21  IgnoreObjects   ❌   ❌   ✅   ❌   ✅
22  RaycastOnly ❌   ❌   ❌   ❌   ✅
26  Custom26    ✅   ✅   ✅   ❌   ✅
27  Custom27    ✅   ✅   ✅   ❌   ✅
28  Custom28    ✅   ✅   ✅   ❌   ✅
29  IgnoreRealtimeLight ✅   ✅   ✅   ❌   ✅
30  WallCollision   ✅   ✅   ✅   ❌   ✅
31  IgnoreParticipant   ✅   ✅   ❌   ❌   ✅

 
Avatar Movement Guidance
The scene should have Colliders for the avatar to walk and teleport on. In general, a low poly Mesh Collider that tightly fits the visual geometry will produce the best results. Box Colliders work great for trivial scenarios, but can result in some problems such as causing the avatar to get stuck on the corners or defeat step height limits.
Mesh avatar movement limits:
Maximum walkable slope: <45 degrees
Maximum step height: 0.3
Avatar capsule radius: 0.3
Avatar capsule height: 2
Avatar height: 1.8
Suggestions for best results:
Align the collision surfaces with the visual surfaces that the avatar will walk on. This is important to avoid issues with the avatar's position relative to the visual surface (to prevent floating or clipping).
Rounded corners help smooth out avatar movement and prevent the avatar from getting stuck.
To block avatar movement, use steep slopes or a height much larger than the maximum step height.
Modify the shape of your colliders to create surfaces that are naturally difficult or impossible for the avatar to traverse. For instance, using a Mesh Collider with an irregular shape that doesn't provide a flat surface or walkable slope for the avatar to stand on.
In some cases a Capsule Collider or similar rounded shape on objects or areas the avatar shouldn't walk on may suffice. These shapes are unwalkable if the slope is steep enough and will cause the avatar to slide off.

Supporting Teleportation
For a scene to support teleportation, teleportable surfaces (for example, the floor or the ground) must have colliders on the GroundCollision layer. There are other walkable layers, but only GroundCollision is teleportable. Visual geometry isn't teleportable and shouldn't be on the GroundCollision layer; only Colliders can be on the GroundCollision layer. Improper or inconsistent layering and collision can cause undesirable effects when teleporting or finding the ground.
A teleportable surface must meet the following conditions:
It must have some type of non-trigger Collider attached (Mesh Collider or Box Collider, for example).
Its Layer must be set to GroundCollision.
Be cautious of low ceilings or tunnels; these could potentially affect avatar grounding and teleportation. For example, avatar physics or the teleport arc may intersect or interact with the collider above them. The height from ground to roof for a traversable area should be more than the 2m avatar capsule height, as there needs to be a small buffer of space above the avatar's head, especially if the roof is sloped instead of flat.
The locomotion physics provide smooth avatar movement with all participant interactable colliders and prevent the penetration of areas that are too small for avatar collision. However, rogue ground collision or problematic environment geometry such as wedge shapes or very narrow spaces can potentially cause the avatar or the camera to penetrate objects or get stuck.  It is essential to thoroughly playtest all walkable and teleportable surfaces.
 
Internal Documentation
mesh.toolkit.internal users only - not for public
Layers
Layer definitions
Layer interactions
Layer table
LocalPlayer
CharacterController
LocalPlayer Capsule
LocalPlayer Collision Layers
CapsuleCaster
LocalPlayer capsule cast visualization
Avatar bone renderer
Seating
Test levels
 
Layers

Layer Definitions
Defined layers by id and name, including blocking semantics and description:
Default
[Player/Object/Raycast Blocking]
Used for collision and lighting, player can walk on, but not teleport onto, default for most props.  Objects on the Default layer receive Realtime Directional Light from the environment.
TransparentFX
[Not Blocking]
Special handling in Unity's rendering pipeline for transparent and special effects objects; ensures correct rendering order for transparency.
IgnoreRaycast
[Player/Object Blocking]
Collision enabled layer that does not block raycasts, such as non-interactable objects or invisible walls that avatars cannot pass, but physics objects can pass through (ie railings that objects can be thrown over, but avatars can't hop over).
PostUI
[Not Blocking]
For UI elements that need to render on top of UI elements.
Water
[Not Blocking]
Specifically for water surfaces - can be used for specialized rendering and physics interactions with water.  Do not use with non-trigger colliders.
UI
[Raycast Blocking]
Dedicated to user interface elements. Layer that UI renders on and ensures UI elements are rendered above other objects and interact properly with the UI system and UI Interactor.
Reserved06
Reserved
 
PerspectiveUI
[Raycast Blocking]
Renders before 2D UI but after the scene. UI pointers (mouse and hand rays) can click on it. Will Interact with OVROverlays this to render PostUI cursors onto Overlays. Interacts with 2d interactor, used in lakehouse for environment UI elements. Used for all 3D UI that needs to still render over other GameObjects (nametags, info buttons, etc.). Not depth tested.
Reserved08
Reserved
Reserved09
Reserved
Reserved10
Reserved
Reserved11
Reserved
Reserved12
Reserved
Reserved13
Reserved
GroundCollision
[Player/Object/Raycast Blocking]
Used for walkable collision surfaces that CAN be teleported onto.
Avatars
[Not Blocking]
Used by Avatar MeshRenderer.
CharacterController
[Not Blocking]
Layer for the LocalPlayer's CharacterController.
IgnoreCollisions
[Not Blocking]
Doesn't interact with anything, can clip through the environment and other objects.
 
TriggerVolume
[Not Blocking]
Layer for objects that should not be affected by physics or raycasts and have no special usage otherwise.  Do not use on objects with non-trigger colliders.
Reserved19
Reserved
ObjectCollision
[Object Blocking]
Layer to collide with objects but not the player or raycasts.
IgnoreObjects
[Player/Raycast Blocking]
Layer to collide with player but not objects.
RaycastOnly
[Raycast Blocking]
Layer for objects that block raycasts or can be selected but don't affect player or object collision.
HideFromCamera
[Player/Object/Raycast Blocking]
Used by the UI layer for Avatar preview camera and the Teams stage. Affects physics/raycast but not seen by camera. Also used for emulator avatar.
AudioOccluder
[Not Blocking]
Used for volumes that block sound, but not the player.
Reserved25
Reserved
Custom26
[Player/Object/Raycast Blocking]
User custom defined layer.
Custom27
[Player/Object/Raycast Blocking]
User custom defined layer.
 
Custom28
[Player/Object/Raycast Blocking]
User custom defined layer.
IgnoreRealtimeLight
[Player/Object/Raycast Blocking]
Specify which art objects in the environment DON'T recieve realtime directional light, such as most static objects (use baked lighting instead via the lightmap).
WallCollision
[Player/Object/Raycast Blocking]
Collision which prevents clipping through a scene - if HMD user sticks their head through the wall, they are respawned to a nearby location on the playable area.
IgnoreParticipant
[Object/Raycast Blocking]
Objects that block raycasts and other objects, but not the player.
 
Layer interactions

 
Table with layer definitions on following page
Builtin Layers
Mesh Layers
Reserved Layers
Custom Layers
 
LayerId Layer   Toolkit Upload  Object  Player  Object Collision    Player Collision    Teleport Target Blocks Raycast
0   Default ✅   ✅   ❌   ✅   ✅   ❌   ✅
1   TransparentFX   ✅   ❌   ❌   ❌   ❌   ❌   ❌
2   IgnoreRaycast   ✅   ✅   ❌   ✅   ✅   ❌   ❌
3   PostUI  ❌   ❌   ❌   ❌   ❌   ❌   ❌
4   Water   ✅   ❌   ❌   ✅   ✅   ❌   ✅
5   UI  ❌   ❌   ❌   ❌   ❌   ❌   ❌
6   Reserved06  ❌   ❌   ❌   ❌   ❌   ❌   ❌
7   PerspectiveUI   ❌   ❌   ❌   ❌   ❌   ❌   ✅
8   Reserved08  ❌   ❌   ❌   ❌   ❌   ❌   ❌
9   Reserved09  ❌   ❌   ❌   ❌   ❌   ❌   ❌
10  Reserved10  ❌   ❌   ❌   ❌   ❌   ❌   ❌
11  Reserved11  ❌   ❌   ❌   ❌   ❌   ❌   ❌
12  Reserved12  ❌   ❌   ❌   ❌   ❌   ❌   ❌
13  Reserved13  ❌   ❌   ❌   ❌   ❌   ❌   ❌
14  GroundCollision ✅   ✅   ❌   ✅   ✅   ✅   ✅
15  Avatars ❌   ❌   ❌   ❌   ❌   ❌   ❌
16  CharacterController ❌   ❌   ✅   ✅   ❌   ❌   ❌
17  IgnoreCollisions    ✅   ❌   ❌   ❌   ❌   ❌   ❌
18  TriggerVolume   ✅   ❌   ❌   ✅   ✅   ❌   ❌
19  Reserved19  ❌   ❌   ❌   ❌   ❌   ❌   ❌
20  ObjectCollision ✅   ✅   ❌   ✅   ❌   ❌   ❌
21  IgnoreObjects   ✅   ❌   ❌   ❌   ✅   ❌   ✅
22  RaycastOnly ✅   ❌   ❌   ❌   ❌   ❌   ✅
23  HideFromCamera  ❌   ✅   ❌   ✅   ✅   ❌   ✅
24  AudioOccluder   ❌   ❌   ❌   ❌   ❌   ❌   ❌
25  Reserved25  ❌   ❌   ❌   ❌   ❌   ❌   ❌
26  Custom26    ✅   ✅   ❌   ✅   ✅   ❌   ✅
27  Custom27    ✅   ✅   ❌   ✅   ✅   ❌   ✅
28  Custom28    ✅   ✅   ❌   ✅   ✅   ❌   ✅
29  IgnoreRealtimeLight ✅   ✅   ❌   ✅   ✅   ❌   ✅
30  WallCollision   ✅   ✅   ❌   ✅   ✅   ❌   ✅
31  IgnoreParticipant   ✅   ✅   ❌   ✅   ❌   ❌   ✅
 
LocalPlayer
The local user's player, the "soul", the avatar the "body". This class is responsible for many different aspects of controlling the user's representation in the space.  It handles the positioning and placement, local inputs, and IK, among other things.
 
LocalPlayer CharacterController
The local player uses a Unity CharacterController for movement.  This defines the player capsule and movement restrictions and characteristics.
 
LocalPlayer Capsule
Selecting the LocalPlayer object will show the player capsule in the scene view.  This is useful for visualizing the player's bounds relative to the environment.
 
LocalPlayer Collision Layers
Layers the CharacterController is configured to walk on and interact with (via Physics project settings):
0 - Default
2 - Ignore Raycast
4 - Water (only trigger colliders allowed, not walkable)
14 - GroundCollision
18 - TriggerVolume (only trigger colliders allowed, not walkable)
21 - IgnoreObjects
23 - HideFromCamera
26 - Custom26
27 - Custom27
28 - Custom28
29 - IgnoreRealtimeLight
30 - WallCollision

 
CapsuleCaster
The LocalPlayer uses a capsule cast to find an appropriate ground location when being positioned.  It can be created with a player capsule radius and height, or there are static versions of all the functions.  There are a variety of capsule casting functions, ground information finding functions, and some debug disagnostics.
CapsuleCaster.cs - Repos (azure.com)

LocalPlayer Capsule Cast visualizer
This debug utility visualizes what the player grounding and positioning are doing in their black box.  It draws the player capsule, ground position (red sphere), head position (blue sphere), and the capsule cast extents (yellow capsule, by default 1m above head, 10m cast range).
Select LocalPlayer (child of LocalPlayerController)
Right click on the Local Player component and select Toggle Capsule Cast Visualizer
Optionally you can toggle the Enable Capsule Cast box, and configure the cast "above distance" and the cast range
  

Capsule cast visualization
 

Avatar bone renderer
Really handy way to visualize the avatar's skeleton, and more importantly, where the feet are relative to the ground.  (scene view)
Find the avatar you are interested in, in this case the Local Avatar.
Select the UnityAnimationRiggingIKRig object
Right click on the UnityAnimationRiggingIKController component, select Build Bone Renderer

 
 

 
Bone Renderer visualization
 

 

Avatar bone renderer and local player capsule cast visualization

 

 
Seating
This guidance is for the legacy seating system currently in Mesh.  There are plans to overhaul this with a new seating framework using our packages, rather than a one-off in MeshBrowser.
The player's seated position must be over a collider on the NavMesh layer as the player needs to be able to find the floor when standing up.  If no ground is found, it may result in the player falling out of the environment.
In this example, there is a portion of the floor bordering the wall that is on the Wall layer.  This is to prevent the player from teleporting right next to the wall.  However, care is needed to place the GameObject with the Seat component over the ground enough that the player's capsule will collide with it when they stand up and are grounded.
 

 
Test levels

Player Movement
Specifically for testing, stressing, and tuning player movement and teleportation.  Contains a variety of test objects and terrain to put it through its paces.
In the MeshForTeams PlayerInteractions world:  Player Interactions Collection
 
 
Related Public Documentation
Make sure this documentation is up to date with the approved guidance and layer name:
https://learn.microsoft.com/en-us/mesh/develop/build-your-basic-environment/set-up-your-scene#setting-up-teleportation
Pending update: mesh-docs/mesh/develop/build-your-basic-environment/set-up-your-scene.md at 88a8883004c409e76e61448b67ec93d185073399 · whitetigerhelix/mesh-docs (github.com)

https://learn.microsoft.com/en-us/mesh/develop/getting-started/mesh-101-tutorial/mesh-101-02-prepare-the-project#choose-the-navmesh-layer

 
Notes
Unity - Scripting API: CharacterController.isGrounded (unity3d.com)
CharacterController.isGrounded != Mesh "grounding", but similar concept.  Mesh is more specific about which collider it's touching.

Teams conversations
Liam Walsh: Renaming NavMesh layer to TeleportTarget
posted in Mesh / ⭐ Engineering on Wednesday, November 1, 2023 5:47 AM
Malcolm Tyrrell: NavMesh Layer
posted in Mesh / Mesh Toolkit - Design on Friday, October 27, 2023 4:34 AM

Related work items
Bug 28280: NavMesh layer needs a new name that does not conflict with Unity's NavMesh component
Task 29277: Draft some documentation on ground and wall layers usage and semantics we are committing to for 3P devs
Task 27057: Player's capsule collider not taken into account when determining teleport endpoint


