---
title: Mesh Physics Programmer's Guide
description: Learn general guidelines and component details for the many available Mesh Physics components.
author: michael-buschbeck-ms
ms.author: vinnietieto
ms.date: 11/07/2023
ms.topic: Guide
ms.service: mesh
keywords: Microsoft Mesh, Mesh physics, physics, environments, interactions, interactables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw
---

# Mesh Physics Programmer's Guide

## General tips

You can start with [scanning the Unity physics docs](https://docs.unity3d.com/Manual/PhysicsOverview.html). There are plenty of resources available on how to optimize physics in Unity.

Mesh Physics comes with some extra challenges. Here are some tips to help overcome them.

* **Make thick walls:** Network synchronization might move rigid bodies slightly. As a result, you'll see some extra penetration between objects. Small dynamic bodies might get pushed through thin walls. For thicker objects and walls, these tunneling effects are less likely. If possible, use convex hull or a small set of convex hulls for dynamic bodies.

* Whenever possible, use thick convex pieces for static geometry. Try to avoid meshes, especially highly dense meshes.

* **Realistic masses in kg**: Content from various sources might interact in the same scene. This works well if the mass ratios between the objects are reasonable. A good starting point is to assign realistic masses to bodies using kg.

## Developing enhanced Mesh Physics content

### Auto-play animations

You can add auto-play animations to the scene that interact with physics bodies. Those animations are automatically synchronized across clients by temporarily adjusting their playback speed (slowing them down or speeding them up) on each client until all clients are in the same animation state at the same time.

**Settings**

* **Play Automatically** enabled.
* **Animate Physics** recommended (but not required) if the animation affects colliders that interact with physics bodies.
* **Culling Type** set to "Always Animate" (automatically enforced by Mesh Physics) because the animation might affect physics bodies even when they're off-screen.

![Screen shot of the Animation component settings in the Inspector.](../../../media/physics-interactions/038_SharedAnimation-Animation.png)

The animation clip used by the auto-play animation can use any **Wrap Mode**. Useful choices are "Loop" and "Ping Pong".

![Screen shot of the Animation Clip asset settings in the Inspector.](../../../media/physics-interactions/039_SharedAnimation-AnimationClip.png)

## Components

Adding one of the following `MonoBehaviour` components to an object will add the specific behavior to this object.

### Sticky Body

Makes bodies stick to other bodies. It could be used to throw darts at other bodies or to attach a picture on a wall. This is implemented by creating a fixed constraint between the two bodies involved.
**Note:** This operation is performed on all clients and therefore is implemented as a special network message.

![Screen shot of the Sticky Body script options in the Inspector.](../../../media/physics-interactions/064-sticky-body.png)

**Settings**

* **Stick:** Defines if the body will stick to dynamic or/and static bodies.
* **When:** Sometimes you want to stick a fast body when it just touches another body, and sometimes you want to stick a body when it is held against another body for a given time, like waiting for glue to harden when you glue a button on a wall.
* **Collision Control** To disable specific collisions between one body and another. Normally you can/should use collision layers. However, since there are only 32 hard-coded collision layers in Microsoft Mesh, this might not be an option. Here you can disable specific bodies.
* **Affected Bodies For Collision** Body filter applied for **Collision Control**.

### Containment Field

Ensures that rigid bodies stay within the boundaries of one or several trigger colliders.

![Screen shot of the Containment Field script options in the Inspector.](../../../media/physics-interactions/065-containment-field.png)

For this component to work, it needs to be attached to one or several trigger colliders. (These trigger colliders can also be nested in the transform hierarchy below the `GameObject` that has this component attached.)

The rigid bodies affected by this component must already be within the boundaries of its trigger colliders (the "trigger volume") when the scene starts. The center of mass of each of these rigid bodies will then be constrained to stay within the boundaries of the trigger volume – it won't be possible to pull or otherwise move the centers of mass of these rigid bodies anywhere outside.

**Settings:**

* **Max Deviation From Containment** allows the center of mass of an affected rigidbody to slightly go outside of the trigger volumes before it snaps back in. This is a performance optimization trade-off: if the allowed max deviation is large, the body might visibly leave the trigger volume and snap back, but the code can avoid having to check and verify the body's position very often when it's resting or moving slowly inside of the trigger volume.

* **Affected Bodies** defines [optional filtering conditions](set-conditions.md) for the bodies affected by this component. (By default, all bodies are affected.)

### Velocity Vector Field

Allows to accelerate/decelerate a rigidbody until it reaches a specific target velocity.

![Screen shot of the Directional Velocity Field script options in the Inspector.](../../../media/physics-interactions/066-velocity-vector-field.png)

This component controls both the magnitude and the direction of velocity. See [Velocity Magnitude Field](#velocity-magnitude-field) to control only magnitude and [Velocity Direction Field](#velocity-direction-field) to control only direction. There are two modes of operation:

* If attached to a rigidbody, this rigidbody will be controlled.
* If attached to a trigger collider, all rigid bodies entering this trigger volume will be affected.

**Settings:**

* **Velocity Type** defines whether we are working on linear or angular velocity.  
* **Direction in Local Space** defines whether target velocity is specified in the local space of the object the component is attached to.  
* **Target Velocity** sets the desired velocity vector in meters/second (or radians/second in case of angular velocity).  
* **Max Acceleration** defines the maximum acceleration applied to reach target velocity.  
* **Acceleration Type** defines a type of acceleration to reach a target velocity.  
  * **Instantaneous** will reach the target velocity immediately (Same as **Constant Acceleration** with **Max Acceleration** = Infinity).  
  * **Constant Acceleration** will ensure the body reaches target velocity no matter what within the limits of the **Max Acceleration** setting.  
  * **Smooth Approach** reduces acceleration the closer you get to target velocity. This means that, in practice, you will never reach the target velocity. Also, should there be any external influence, like going uphill or downhill, this extra influence won't be completely overridden, resulting in going faster downhill than uphill.  
* **Affected Bodies** defines [optional filtering conditions](set-conditions.md) for the bodies affected by this component. (By default, all bodies are affected.)

### Scaled Gravity Field

Changes how gravity affects rigid bodies within the boundaries of one or several trigger colliders.

![Screen shot of the Antigravity Field script options in the Inspector.](../../../media/physics-interactions/067-scaled-gravity-field.png)

For this component to work, it needs to be attached to one or several trigger colliders. (These trigger colliders can also be nested in the transform hierarchy below the GameObject that has this component attached.)

Any rigid bodies that touch or overlap the trigger colliders (the "trigger volume") behave according to the gravity settings of this component rather than global physics gravity. Rigid bodies that have **Use Gravity** disabled are ignored.

There is an interesting relationship between the perception of the player's own size in the world and gravity:

* If gravity is **less** than what we're used to (objects are slower when they fall), the player perceives themselves to be larger – like a giant.
* If gravity is **greater** than what we're used to (objects are faster when they fall), the player perceives themselves to be smaller – like a mouse.

**Settings:**

* **Gravity Preset** allows the selection of several interesting and useful presets for the **Gravity Scale** property: various celestial bodies (Moon, Mars, Earth, Jupiter), no gravity (Outer Space), or inverted gravity (Upside Down). You can always overwrite the **Gravity Scale** with any value you like.
* **Gravity Scale** sets the local gravity inside the trigger volume in relation to the default physics gravity affecting the scene. The default gravity scale of 1 leaves gravity unaffected; larger values increase gravity; 0 removes gravity; negative values switch the direction of gravity.
* **Affected Bodies** defines [optional filtering conditions](set-conditions.md) for the bodies affected by this component. (By default, all bodies are affected.)

### Orbital Gravity Field

Simulates the gravity of a "toy planet" in your scene.

![Screen shot of the Gravity Field script options in the Inspector.](../../../media/physics-interactions/068-orbital-gravity-field.png)

For this component to work, it needs to be attached to one or several trigger colliders. (These trigger colliders can also be nested in the transform hierarchy below the GameObject that has this component attached.)

Any rigid bodies that touch or overlap the trigger colliders (the "trigger volume") are pulled towards the position of the object that has this component attached.

**Settings:**

* **Gravity** defines the magnitude of gravity. This is the acceleration of the orbiting body (the "moon") towards the central body at a one-meter distance. Since the orbital velocity is sqrt(gravity/radius), this value describes the velocity² of a moon in a stable orbit at a radius of one meter.
* **Disable Global Gravity** disables the scene's global physics gravity setting for bodies affected by this component. By default, the global scene gravity will still affect your planet and its moons.
* **Affected Bodies** defines [optional filtering conditions](set-conditions.md) for the bodies that can become moons in this gravity field.

* **Force Moons On Circular Orbit** is a cheat that applies some gentle forces to push the moon into a circular orbit. The motivation is that it is hard for a non-expert to set gravity and initial velocity of the bodies in a way to achieve a circular orbit. Additionally, if this option is enabled, any moons that are placed inside the gravity field in Unity Editor automatically start orbiting their central body when the scene is loaded.
* **Strength Of Forced Orbit** scales the acceleration applied to force the moon onto a circular orbit.
* **Set Forced Radius Where Placed** makes moons that are placed inside the gravity field in Unity Editor automatically adopt their initial distance from the central body as their preferred orbit.
* **Set Forced Radius Where Dropped** makes moons that are interactively grabbed and moved into the gravity field automatically adopt the distance from the central body at which they were dropped as their preferred orbit.
* **Default Force Radius** defines the default radius for the above cheat that's used unless overridden by any of the other options.

### Buoyancy Field

Simulates buoyancy of arbitrary rigid bodies on water: Bodies appear to float on the connected trigger volume.

![Screen shot of the Buoyancy Field script options in the Inspector.](../../../media/physics-interactions/069-buoyancy-field.png)

For this component to work it needs to be attached to one or several trigger colliders. (These trigger colliders can also be nested in the transform hierarchy below the GameObject that has this component attached.)

Any rigid bodies that touch or overlap the trigger colliders (the "trigger volume") experience buoyancy forces (upthrust) to keep them afloat.

This component uses the shape of the rigidbody's colliders to calculate its density (in other words, volume divided by mass), buoyancy, drag, and friction.

### Buoyancy Colliders

**Benefit**: Performance. The compute cost of the buoyancy calculations scales linearly with the number of collider vertices. Typical physics colliders for bodies, even if already simplified, are often significantly more complex (in terms of number of vertices) than requiresd for buoyancy to work well enough.

**How to use**: Add one (or several) additional colliders (they can be disabled) to a body. Mark the colliders as explicit buoyancy hulls by assigning a physics material named `BuoyancyHull` (exact spelling matters!) to them. The configuration details of this physics material don't matter - a suitable physics material is supplied with the Mesh toolkit package. If a body has any colliders marked like that, only these colliders are used for buoyancy calculations; all other colliders are ignored.

**Best practices**: Explicit buoyancy hull colliders to any Rigidbody that can possibly be thrown into a *BuoyancyField*. It's best (and easiest) to use Cube colliders because they have the fewest vertices (eight per collider). Matching the exact visual shape of the buoyant body usually isn't required for a good result; a very coarse approximation is usually sufficient.

**Settings:**

* **Density** is the density of the simulated liquid that "fills" the trigger volume in kilograms per cubic meter. (The default represents the approximate density of water at room temperature.)
* **Surface Type** specifies how the component samples the shape of the water surface to calculate buoyancy forces.
  * **Static Flat** assumes that the water surface is perfectly planar and never moves from its initial position in the scene. The position and orientation of the water surface is determined just once, when the scene starts. This is the computationally cheapest option.
  * **Dynamic Flat** assumes that the water surface is perfectly planar but allows that it can move (for example, the water level can rise or sink). The position and orientation of the water surface is determined once per frame.
  * **Dynamic Flat Per Body** supports a water surface that isn't planar (for example, it can be wavy). For each rigidbody floating on the water surface, a local planar approximation of the water surface underneath the rigidbody is determined once per frame, which is then used to calculate buoyancy forces for this rigidbody.
* **Affected Bodies** defines [optional filtering conditions](set-conditions.md) for the bodies that can float in this buoyancy field. (By default, all bodies are eligible.)
* **Drag** controls movement resistance as the rigidbody hits the water (in other words, friction orthogonal to the body's surface).
* **Skin friction** controls movement resistance as the rigidbody is moved through the water (in other words, friction parallel to the body's surface).

**Important!** To allow the component to access a rigidbody's collider mesh triangles, the "Read/Write Enabled" check box must be selected in the collider mesh's **Import** settings. Otherwise the body will be ignored by the buoyancy field and will fall through the field without being affected by it.

**Important!** Make sure that your physics bodies have plausible masses to ensure they behave as expected in a buoyancy field:

* If the mass of a rigidbody is implausibly high compared to its volume, it will sink to the bottom.
* If the mass of a rigidbody is implausibly low compared to its volume (for example, Unity's `Rigidbody` default of one unit of mass), it will just sit on top of the simulated liquid.

By default, the buoyancy field samples the surface of the trigger volume to determine the shape of the water surface (subject to the chosen **Water Surface Type** setting). Surfaces animated in CPU memory can be sampled that way, but surfaces animated by a GPU vertex shader aren't visible to the script at runtime. The `BuoyancyField` component provides a script-accessible callback delegate named `GetDistanceFromSurface` that allows external scripts to supply information about a GPU-animated water surface shape.

See the `BuoyancyFieldWaves` component below for how to get a wavy water surface with a no-code approach.

### Buoyancy Field Waves

Add-on to the `BuoyancyField` component that works with a specific vertex shader, `BuoyancyFieldWaves_VertexPosition` (available both as a sub-shader graph and an HLSL include file). This creates the visual effect of a wavy water surface together with corresponding behavior of objects floating on the water surface.

![Screen shot of the Buoyancy Field Waves script options in the Inspector.](../../../media/physics-interactions/090-buoyancy-field-waves.png)

This component must be added to a GameObject that already has a `BuoyancyField` component added to it.

The water surface to be animated must be supplied as a flat, tesselated mesh whose boundaries are of the desired shape of the water surface when seen from the top down. The material used for the water surface must use a shader that incorporates the `BuoyancyFieldWaves_VertexPosition` sub-shader to determine the mesh's vertex positions. You can use the included sample `BasicWavyWaterSurface` material (and the shader graph with the same name) as a starting point for your own shader developments.

**Settings:**

* **Waves Mesh Renderer** references the `MeshRenderer` component that renders the water surface mesh.
  * **Material** shows which material is used by the renderer. This is for information only.
  * **Shader** shows which shader is used by the material. This is for information only.
* **Waves Shader Property Names** defines the names of required shader properties that must be exposed by the shader. These properties are accessed by this component at runtime to ensure that the buoyancy field's behavior stays in sync with the water surface visuals across all clients.
  * **Script Controlled Time** is the name of an exposed `float`-type shader property that will be *continually updated* by this component every frame with a continually increasing time (measured in seconds) that is synchronized across all clients. The `BuoyancyFieldWaves_VertexPosition` sub-shader uses this shared time to create a wave pattern that remains in sync on all clients and in sync with the behavior of the buoyancy field.
  * **Wave Speed** is the name of an exposed `float`-type shader property that determines the *base speed* at which the waves propagate horizontally. The property value itself must be set in the material applied to the wave surface mesh. Setting this to zero makes the wave surface become static and unmoving.
  * **Wave Length** is the name of an exposed `float`-type shader property that determines the *coarseness* of the wave pattern. The property value itself must be set in the material applied to the wave surface mesh. Smaller values produce short ripples; larger values produce long, sweeping waves.
  * **Wave Height** is the name of an exposed `float`-type shader property that determines the *base height* of the waves. The property value itself must be set in the material applied to the wave surface mesh. Setting this to zero makes the wave surface become completely flat.

The included sample `BasicWavyWaterSurface` shader graph (used by the material with the same name) uses the required `BuoyancyFieldWaves_VertexPosition` vertex sub-shader to produce the wavy 3D surface, but only includes a minimal stand-in implementation for the fragment shader, which makes it render the surface as an unshaded, plain-colored, semi-transparent mesh.

![Screen shot of the Basic Wavy Water Surface shader graph in the Shader Graph Editor.](../../../media/physics-interactions/035_BuoyancyFieldWaves-BasicWavyWaterSurface.png)

You can customize the **Fragment** path of a shader used with the `BuoyancyFieldWaves` component completely to your liking. However, it's essential that the **Vertex** path of your shader uses the `BuoyancyFieldWaves_VertexPosition` sub-shader graph and that it exposes the four inputs to this sub-shader graph as `float`-type shader properties of the overall shader graph so that the component can access them at runtime. If your shader fails to include the required sub-shader graph or if any of the required shader properties aren't exposed, the component's inspector will display an error message at design time and buoyancy will fail to work at runtime:

![Screen shot of the Buoyancy Field Waves script options showing the error message: Required vertex sub-shader not in use.](../../../media/physics-interactions/036_BuoyancyFieldWaves-error-subshader.png)

![Screen shot of the Buoyancy Field Waves script options showing the error message: Shader property not exposed by material.](../../../media/physics-interactions/037_BuoyancyFieldWaves-error-shaderproperty.png)

The sample `BasicWavyWaterSurface` shader graph can serve as a stand-in during content development and as a starting point for your own shader developments. Alternatively, you can take an existing water surface shader, keep its **Fragment** path, and only replace its **Vertex** path.

### Max Angular Velocity

Overrides the default maximum angular velocity of a physics body.

![Screen shot of the Max Angular Velocity script options in the Inspector.](../../../media/physics-interactions/071-max-angular-velocity.png)

The physics engine won't allow the rigidbody to exceed this angular velocity. This can be useful to either limit the rolling speed of a given rigidbody or to allow it to roll faster than the physics default, which is 50 radians per second (approximately 8 revolutions per second).

The maximum angular velocity must be entered in radians per second. The entered value is also displayed in degrees per second (180 degrees ≈ 3.14 radians) and revolutions per second (1 revolution = 360 degrees ≈ 6.28 radians).

### Velocity Magnitude Field

Allows acceleration/deceleration of a rigidbody until it reaches a speed that's within an allowable range.

![Screen shot of the Velocity Field script options in the Inspector.](../../../media/physics-interactions/072-velocity-magnitude-field.png)

This component controls the magnitude of the velocity and keeps the current direction. Should the object be still, it chooses a random direction for the duration of one frame. There are two modes of operation:

* If attached to a rigidbody, this rigidbody will be controlled.
* If attached to a trigger collider, all rigid bodies entering this trigger volume will be affected.

**Settings:**

* **Velocity Type** defines whether we are working on linear or angular velocity.
* **Speed Limits** sets the desired limits of minimum and maximum speed in meters/second (or radians/second in case of angular velocity). If the current speed is below the minimum it will accelerate, if it is more than the maximum the body will decelerate. If the current speed is already within the limits, the script has no effect. To set a specific target speed, set minimum and maximum to the same value.
* **Max Acceleration** defines the maximum acceleration applied to reach target velocity.
* **Acceleration Type** defines a type of acceleration to reach a target velocity.
  * **Instantaneous** will reach the speed limit immediately (Same as **Constant Acceleration** with **Max Acceleration** = Infinity).
  * **Constant Acceleration** will ensure the body reaches target velocity no matter what within the limits of the **Max Acceleration** setting.
  * **Smooth Approach** reduces acceleration the closer you get to target velocity. This means that, in practice, you will never reach the target velocity. Also, should there be any external influence, like going uphill or downhill, this extra influence won't be completely overridden, resulting in going faster downhill than uphill.
* **Affected Bodies** defines [optional filtering conditions](set-conditions.md) for the bodies affected by this component. (By default, all bodies are affected.)

### Align Field

Aligns the body to the specified axis.

![Screen shot of the Align Field script options in the Inspector.](../../../media/physics-interactions/073-align-field.png)

This component adds torque to the body to align it to a specific direction. Note that torque is always applied in the direction that rotates the body towards the target. There are two modes of operation:

- If attached to a rigidbody, this rigidbody will be aligned.
- If attached to a trigger collider, all rigid bodies entering this trigger volume will be aligned.

**Settings:**

- **Rigidbody Axis** sets the axis of the affected rigidbody which is to be aligned to the target.
- **Alignment Mode** provides different modes to specify target alignment:
  - **In Global Space** to specify target alignment in global Space.
  - **In Local Space** to specify target alignment in local Space (only makes sense with trigger volume).
  - **Direction Of Velocity** to align the body to its linear velocity.
  - **Towards Game Object** to align the body towards a target gameobject.
- **Target Alignment** sets the target direction of the alignment. (Only when **Alignment Mode** is set to **In Global Space** or **In Local Space**.)
- **Target Game Object** sets the target direction of the alignment. (Only when **Alignment Mode** is set to **Towards Game Object**.)
- **Torque Multiplier** scales the applied torque to reach the target alignment; a higher multiplier rotates the body faster (between 1 and 1000).
- **Damping Coefficient** sets the damping factor (between 0 and 5). When set below 1, the body might oscillate around target orientation.
* **Affected Bodies** defines [optional filtering conditions](set-conditions.md) for the bodies affected by this component. (By default, all bodies are affected.)

### Velocity Direction Field

Allows to steer a rigidbody until the velocity reaches a target direction.

![Screen shot of the Velocity Direction Field script options in the Inspector.](../../../media/physics-interactions/074-velocity-direction-field.png)

This component controls only the direction of the velocity and keeps the current speed. There are two modes of operation:

* If attached to a rigidbody, this rigidbody will be controlled.
* If attached to a trigger collider, all rigid bodies entering this trigger volume will be affected.

**Settings:**

* **Velocity Type** defines whether we are working on linear or angular velocity.
* **Follow Game Object** defines whether the target is a predefined direction or a direction towards a specific GameObject. Only works for linear velocity.
* **Target Body** (if **Follow Game Object** is set to true): sets the desired follow direction.
* **Target Direction** sets the desired direction. This value is normalized, so magnitude has no effect.
* **Direction In Local Space** defines whether the direction is specified in a local transform of the explosion.
* **Max Acceleration** defines the maximum acceleration applied to reach target velocity.
* **Acceleration Type** defines a type of acceleration to reach a target velocity.
  * **Instantaneous** will reach the target direction immediately (Same as **Constant Acceleration** with **Max Acceleration** = Infinity).
  * **Constant Acceleration** will ensure the body reaches target velocity no matter what within the limits of the **Max Acceleration** setting.
  * **Smooth Approach** reduces acceleration the closer you get to target velocity. This means that, in practice, you'll never reach the target velocity. Also, if there's any external influence such as going uphill or downhill, this extra influence won't be completely overridden, resulting in going faster downhill than uphill.
* **Affected Bodies** defines [optional filtering conditions](set-conditions.md) for the bodies affected by this component. (By default, all bodies are affected.)

### Magnetic Body

Gives the body a magnetic property which attracts or repels other bodies.

![Screen shot of the Magnetic Body script options in the Inspector.](../../../media/physics-interactions/075-magnetic-body.png)

For this component to work, it needs to be attached to one or several colliders. (These colliders can also be nested in the transform hierarchy below the `GameObject` that has this component attached.)
Each collider exhibits a force on other rigidbodies that are close enough to this collider.

**Settings:**

* **Strength** defines the acceleration of the magnet at the point of contact (when the distance between colliders is zero).
* **Distance Of Influence** controls the range of the magnetic force. Magnetic force is applied only if the shortest distance between colliders is smaller.
* **Field Type** defines how the magnetic force weakens with the distance.
  * **Constant** assumes that the magnetic force is the same independent of the distance.
  * **Linear** assumes that the magnetic force drops linearly from **Strength** to zero (at the **Distance Of Influence**).
  * **Inverse** assumes an inversely proportional dependence to the distance.
  * **Inverse Squared** assumes an inversely proportional dependence to the distance squared (similar to a real magnet).
* **Magnetic Pole** controls which objects are attracted to or repelled by this object.
  * **North Pole** attracts **South Pole** and repels **North Pole**.
  * **South Pole** attracts **North Pole** and repels **South Pole**.
  * **Magnetic** attracts both **South Pole** and **North Pole**.
* **Disable Gravity On Contact**: If this is enabled, *and* **Strength** of the magnet is two times bigger than gravity, gravity is disabled for bodies that are in contact with this magnet. One of the objects must be static for this to have an affect. This is often used to prevent the sliding of bodies down a wall.

### Spherical Explosion

Creates an explosion which causes all bodies within a specific radius to move outwards.

![Screen shot of the Spherical Explosion script options in the Inspector.](../../../media/physics-interactions/076-spherical-explosion.png)

The explosion force depends on the mass of a rigidbody (and potentially the distance from the explosion center).

**Settings:**

* **Strength** defines the effect of the explosion on bodies in meters/second. The actual velocity change is less depending on the **Explosion Type** and **Critical Mass** (see below).
* **Distance Of Influence** controls the range of the explosion force.
* **Field Type** defines how the explosion effect weakens with distance.
  * **Constant** assumes that the effect is independent of the distance.
  * **Linear Drop** assumes that the effect drops from maximum to zero (at the **Distance Of Influence**).
* **Critical Mass** defines the mass of the body not affected by the explosion. Heavier bodies feel less effect than lighter bodies. For example, a rigidbody that weighs one third of the **Critical Mass** will feel two thirds of the **Velocity Change**.
* **Angular Impulse Scale** defines where the force is applied. If set to 0, force is applied at the center of mass, which means no rotation. If set to 1, force is applied at the closest point to the explosion.
* **Occlusion** If enabled, objects hidden behind other objects don't feel the explosion. Only a single ray between the center of the explosion and the center of mass is checked for occlusion.

### Directional Explosion

Creates an explosion which causes all bodies within a trigger to move in a specific direction.

![Screen shot of the Directional Eplosion script options in the Inspector.](../../../media/physics-interactions/077-directional-explosion.png)

The explosion force depends on the mass of a rigidbody. For this component to work, it needs to be attached to a trigger collider. All bodies within the trigger collider are affected.

**Settings:**

* **Strength** defines the effect of the explosion on bodies in meters/second. The actual velocity change is less depending on the **Critical Mass** (see below).
* **Direction** defines the direction of the explosion. This value is normalized, so magnitude has no effect.
* **Direction In Local Space** defines whether the direction is specified in a local transform of the explosion.
* **Critical Mass** defines the mass of the body not affected by the explosion. Heavier bodies feel less effect than lighter bodies. For example, a rigidbody that weighs one third of the **Critical Mass** will feel two thirds of the **Velocity Change**.
* **Angular Impulse Scale** defines where the force is applied. If set to 0, force is applied at the center of mass, which means no rotation. If set to 1, force is applied at the closest point to the explosion.
* **Affected Bodies** defines optional filtering conditions for the bodies affected by this component. (By default, all bodies are affected.)

### Joint Stabilization

Stabilizes the constraint system by adjusting the rigidbody's inertia tensor.

![Screen shot of the Joint Stabilization script options in the Inspector.](../../../media/physics-interactions/078-joint-stabilization.png)

The script works on all children with the Rigidbody or Joint component attached.

**Settings:**

* **Stabilization Factor** defines how much you sacrifice physical correctness for stability. For example, 1 -> mostly physics correct, 4 -> compromise, 10 -> stable with artifacts.
* **Joint Projection** enables constraint projection on all children. This can dramatically improve stability but sacrifices physical correctness. It only works on Configurable and Character Joints.
* **Projection Distance** defines the maximum allowed violation of constraints. To avoid physics issues, try to set this value as high as possible.

### Bouncing Surface

Creates a bouncing surface which causes all colliding objects to bounce off with a predefined velocity.

![Screen shot of the Bouncing Surface script options in the Inspector.](../../../media/physics-interactions/079-bouncing-surface.png)

**Settings:**

* **Bounce Velocity Magnitude** defines the minimum and maximum velocity magnitude of the object after the bounce. See **Bounce Effect** for how direction is determined. Set **Min** and **Max** to equal value if you want to specify a single target velocity.
* **Bounce Effect** defines the intended behavior of bouncing objects.
  * **Perfect Bounce**: the angle of incoming velocity to the collision plane normal is the same as the angle of outgoing velocity.
  * **Set Velocity Magnitude**: the angle of the outgoing velocity to normal is affected by friction.
  * **Set Normal Velocity**: similar to **Set Velocity Magnitude**, but the **Bounce Velocity Magnitude** defines the magnitude of the velocity perpendicular to plane (normal velocity).
  * **Bounce Towards Target Body**: the direction of outgoing velocity is directed towards a target Body. If this option is selected, the **Target Body** property appears and must be set.
* **Friction** controls how much tangential velocity is lost upon collision. When set to 0, the bouncing object retains tangential velocity. When set to 1, the object bounces in direction perpendicular to the surface (tangential velocity is 0). For values more than 1, the object bounces backwards.

### Center Of Mass Offset

Offsets the center of mass of a rigidbody.

![Screen shot of the Center Of Mass Offset script options in the Inspector.](../../../media/physics-interactions/080-center-of-mass-offset.png)

**Settings:**

* **Offset In Local Coordinates** defines the offset in local coordinates.

### Local Physics Scope

All rigidbodies in the **Hierarchy** under this component won't be synced among clients. This script should be added to rigidbodies whose positions or rotations are set through a visual script or an animation.

![Screen shot of the Local Physics Scope settings in the Inspector.](../../../media/physics-interactions/081-local-physics-scope.png)

[Learn about Mesh Visual Scripting physics event nodes](../../script-your-scene-logic/visual-scripting/visual-scripting-node-reference.md#physics-events-nodes).

### Throw Trajectory

Calculates the rigidbody's future position in free space under the effect of gravity.

![Screen shot of the Throw Trajectory script options in the Inspector.](../../../media/physics-interactions/063-throw-trajectory.png)

**Settings:**

- **Rigidbody Mode**: When set to true, the rigidbody position and velocity are taken as initial conditions. Enables real time future position calculation.
- **Rigidbody** (only applies when **Rigidbody Mode** is set to *true*.): Defines which rigidbody is taken. 
- **Initial Velocity**: (only applies when **Rigidbody Mode** is set to false): Defines the initial velocity. The initial position is taken from the position of the GameObject this component is attached to.
- **Max Number Of Points**: Defines the maximum number of calculated points.
- **Time Step**: Defines the time difference between the future positions.
- **Gravity**: This is the gravitational acceleration.
- **Line Renderer**: Specifies the line renderer the position of points are copied to. This displays the throw trajectory.

## Next steps

> [!div class="nextstepaction"]
> [Set conditions for affecting objects](set-conditions.md)