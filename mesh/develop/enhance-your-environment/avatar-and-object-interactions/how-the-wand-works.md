---
title: Equippables -- How the Wand works
description: Take an-indepth look at the visual script that makes the Wand Equippable object work.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 5/3/2024
ms.topic: overview
keywords: interactions, interactables, equippables, throwables, avatars, grab, pick up, hold, throw, attach, activate, activation
---

# Equippables: How the Wand works

## Wand Overview



The Wand, under the hood: it has an onHold() event. (?) It changes its state when it goes from not being held to being held. When it's activated, it's a "single instance" activation. It plays the VFX and audio and changes the avatar pose. 


The Wand is in the scene--it's static, it's just sitting there.

In the visual script attached to the Wand, we start in the group named **Checking if Held to start magic glow**.

<overview image>

The node that determines if the Wand is picked up or not is *Mesh Interactable Body: Is Mine*. It's a Boolean, and starts with a value of False.

![______](../../../media/enhance-your-environment/equips-in-detail/010-is-mine-node.png)

When an avatar picks up the Wand, its state changes. The "true" value of *isMind* is passed to an *if* node and this causes a "pickup sound" to trigger.

<image>

... and it also changes the value of the object variable *StartGlowVFX* to "true."

<image>

Note that the text above the *isMind* and *On State Changed* nodes says "Local to this client." 

<image of nodes with text above it highlighted>

These nodes, and the sound that gets triggered, occur locally. However, we want the other attendees in the event to experience what happens with the Wand. This is achieved by inserting the *Set Object Variable* node which displays the text "Shared by all clients." 

< image of set object variable node with text above it >

**Tip**: The *isMine* variable is found in the *Mesh Interactable Body* script.

<image>

We pick up the flow in the node group named **Networking startMagic**.

<overview image>

The state change causes the "true" value of *startFLowVFX* to be passed to an *if* node ..

<image>

... and this causes the value of the *PersistentVFX* object variable to also be true, which triggers the *vfx_wand-ethereal_persistent_02* particle system effect.

<image>

## Activating the Wand

Let's assume the attendee clicks the left mouse button (PC) or controller trigger button (Quest). This is called "activating the Equippable." It causes the avatar's arm position to change, and in the node group named **Networking isPressed** ...

<overview image>

 ... the click is detected by the *Mesh Interactable Body: Is Activated* node. This node is a Boolean with a default value of false. The click changes *Is Activated* to "true"; the *On State Changed* node passes the "true" value on to the *If* node. This causes the *Set Variable* node to set the *isPressed* Boolean to the opposite of what it was before (so now it's "true").

<image>

**Tip**: The *isActivated* variable is found in the *Mesh Interactable Body* script.

<image>

We pick up the flow in the node group named **Spell cast on click**.

<overview image>

The "true" value of isPressed* causes an *if* node to trigger the *Set Variable: Object* node. This node sets the *startGlowVFX* variable to "false", and this triggers the nodes in the **Networking startMagic** node group again. This time, the "false" value of *startGlowVFX* causes the *PersistentVFX* particle effect to turn off.

<image>

Back to the **Spell Cast on click** node group. After a brief cooldown period, a sound is played, and then a different particle effect is triggered at the tip of the wand: *vfx_wand_blast_trail_spheres_01*, which is the value for the *ShootTrailVFX* object variable.

<image>

After another brief cooldown period, the *startGlowVFX** Boolean value is changed back to "true", which turns the *vfx_wand_ethereal_persistent_02* particle system effect back on in the **Networking startMagic** group.

<image>

At this point, the avatar's arm returns to the position it was in before the Wand was activated.

## Releasing the Wand

If the Wand had the activate type "toggle," when the attendee clicked again, it would trigger a second, different "state." However, the Wand's activate type is "single", and this means that every time the attendee clicks, the same "state", or series of actions and effects, is repeated.

To release the Wand, the attendee presses the Space key and the Wand drops to the ground. This causes the nodes in the **If not occupied, Turn off Wand** node group come into play. The purpose of this node group is to turn off the "glow" particle effect. 

<overview image>

While the Wand is being held, the value of the *Mesh Interactable Body: Get Equipped At** is "DefaultHand". The value of the *Equip Location* node (a Boolean) is "None." These two values are compared in the *Equal* node (also a Boolen); since they're not the same, the output of *Equal* is "false" and the *if* node isn't triggered.

When the Wand is dropped, the value of *Get Equipped At* changes to "None." This causes the *Equal* and *If* nodes to output "true." This triggers the *Set Variable: Object* node which turns the value of the *startGlowVFX* object variable to "false." This once again triggers the nodes in the **Networking startMagic** node group and turns off the particle effect--*vfx_wand_ethereal_persistent_02--*that's the value of the *PersistantVFX* object variable.

Suggestions for experimentation with the script

- Create different effects that could be triggered when one of the existing Equippables is picked up and held.
- Create new Equippables that could use some of the existing effects. For example, certain types of fireworks could use the "sparkle" effects that are currently used by the Wand.
- Create different effects and behaviors for a new Equippable that could be triggered when the Equippable is held and the left mouse button (PC) or controller button (Quest 2) is pressed. For example, instead of a Wand, you could have a fishing rod that casts out a lure when you press the button.
- Think about the difference between having an object move right into its "read for action" state when picked up (for example, the Drill) and having an object that starts off in "waiting" mode and moves into "ready for action" mode after the attendee clicks (for example, the Tablet). Make objects that take advantage of both approaches.

