---
title: Mesh physics overview
description: Read an overview of how to use Mesh physics when creating Environments for Mesh.
author: michael-buschbeck-ms
ms.author: vinnietieto
ms.date: 10/18/2023
ms.topic: Guide
ms.service: mesh
keywords: Microsoft Mesh, Mesh physics, physics, environments, interactions, interactables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw
---

# Mesh Physics Overview

In a Mesh experience, physics simulation is key to enabling engaging dynamic content. In order to provide Mesh participants with high quality shared physics experiences and offer developers a productive workflow in creating custom content, we've created the *Mesh Physics* system. Mesh Physics is based on local authoritative simulation, which results in a very simple architecture. There's no need for server-side logic and special logic on the clients. Most importantly, this approach results in a very responsive and low-latency experience for each player interacting with their environment, even when connected to a high-latency network.

**Distributed physics simulation**

![A screen shot showing distributed physics objects.](../../../media/physics-interactions/002_20220718_133302_image.png)

Mesh physics synchronizes the positions of rigid bodies and should work out-of-the-box, assuming all clients share the same scene. Most Unity physics features (for example, rigidbodies, colliders, materials, and constraints)  will be synchronized without extra developer effort:

**Notes:**

* Only rigidbody positions & orientations are synchronized with interpolation
* Discrete state changes (for example, breakable constraints) and trigger events must be avoided

Each client is responsible for simulating some of the bodies, called the distributed simulation *ownership*. When a player touches a rigid body, simulation ownership is immediately transferred to allow low-latency interaction. For neighboring bodies, the physics synchronization engine performs local prediction, interpolation, and automatic ownership redistribution to minimize visual artifacts.

Mesh Physics offers interaction and additional physics-related functionalities such as:

* various fields to physically influence bodies inside (buoyancy, gravity)
* various components to modify the behavior of individual bodies (magnetic, sticky, throwable)
* the ability to reset bodies to their startup positions (selective scene cleanup)
* [Mesh Emulation Mode](../../debug-and-optimize-performance/mesh-emulator.md) support for multi-user testing of the features above

Here are more things you can do with Mesh Physics features:

* Allow participants to grab and carry objects.

* Control how gravity affects objects.

    ![Screen shot of a game that uses gravity.](../../../media/physics-interactions/105-ball-drop.png)

* Make an object “sticky”—it sticks to whatever it hits. Examples: throwing a dart at a dart board, attaching a picture to a wall.

    ![Screen shot of paintings attached to a wall.](../../../media/physics-interactions/003-sticky-pictures.png)

* Add auto-play animations that interact with physics bodies.

    ![Screen shot of an animation trigger.](../../../media/physics-interactions/010-animation-trigger.png)

* Allow participants to reset objects (for example, reset a chess board, or clean up a room after objects have been scattered about).

    ![Two-part screen shot of a room with furniture in disarray and then the same room with furniture back in place.](../../../media/physics-interactions/002-rearrange.png)

* Fire events when an object enters a trigger collider.

    ![Screen shot of a trigger volume.](../../../media/physics-interactions/030-trigger-volume.png)

* Create a containment field. Objects will stay within the boundaries of the field.

    ![Screen shot of a containment field.](../../../media/physics-interactions/061-containment-field-in-scene-view.png)

* Control the velocity of an object.

* Control the buoyancy of objects&mdash;for example, make boats and other seagoing objects “float.”

    ![Screen shot of a boat floating on water.](../../../media/physics-interactions/007-buoyancy-field.png)

* Control the angular velocity of an object.

* Create an explosion, causing nearby objects to move outward or in a specific direction.

* Create “bouncy” objects that bounce off each other with a predefined velocity.

    ![Screen shot of numerous balls in mid-bounce.](../../../media/physics-interactions/006-balls-bounce.png)

* Teleport an object to a new position and (optional) new rotation.

    ![Two-part screen shot of the start and end points of a teleportation process.](../../../media/physics-interactions/034-teleport-path.png)

## Terminology

Throughout the Mesh Physics articles, "body" is used as shorthand for "Rigidbody."

## Next steps

> [!div class="nextstepaction"]
> [Mesh Physics in Samples](mesh-physics-in-samples.md)