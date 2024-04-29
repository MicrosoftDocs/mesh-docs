---
title: Grab and manipulate objects realistically
description: Learn about various equippable objects and the realistic ways they can be grabbed and manipulated.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 4/24/2024
ms.topic: overview
keywords: Microsoft Mesh, object and player interactions, interactables, manipulables, equippables, throwables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw, attach, Mesh emulator, emulator, Mesh Emulation Mode
---

# Grab and manipulate objects realistically

## Equippables

The Toybox sample contains ten different Equippable prefabs. In Unity in the **Scene** window, they're located on a table against the back wall.

![A screen shot of the equippables in the Scene window.](../../../media/enhance-your-environment/equips-in-detail/004-equips-in-building.png)

In the **Hierarchy**, they're nexted prefabs to **Equipable Interactable Samples**, which is connected to a prefab named *toybox_Equipable_Interactable_Samples*.

![A screen shot of the equippable prefabs in the Hierarchy.](../../../media/enhance-your-environment/equips-in-detail/001-equips-in-the-hierarchy.png)

For each Equippable, there are two activation types.

![A screen shot of the visual scripts for the single and toggle equippable activation types.](../../../media/enhance-your-environment/equips-in-detail/002-activation-type-scripts.png)

Examples:

- The Wand has the activate type *Single*.  You grab the Wand and click; the Wand raises and throws off some fireworks, and then returns to its default position.
- The Wineglass has the activation type *Toggle*. There are two states, and the avatar controls the transition between them. You grab the glass--that's the first state. You click--the glass raises, and that's the second state. To lower the glass to its default position, you must click again.

![Screen shots of avatars holding the Wand, which is the single equippable activation type, and the Drill, which is the toggle equippable activation type.](../../../media/enhance-your-environment/equips-in-detail/003-activation-type-examples.png)

The Equippable prefabs live in subfolders of the *Runtime* folder. These folders start with *Toybox_* followed by the name of the prefab. For example, the Wineglass prefab is stored in the *Toybox_Wineglass* folder.

![Screen shot of the wineglass prefab in the Toybox_WineGlass folder.](../../../media/enhance-your-environment/equips-in-detail/005-wineglass-location-in-folder.png)

**Tip**: To quickly find a prefab in the **Project** folder, in the **Hierarchy**, select the prefab, and then, in the **Inspector**, click the **Select** button.

## Equippable behaviors

### Wineglass

Activation mode: toggle

When an attendee grabs a Wineglass, their hand holds the glass by the stem. To raise the glass in a toast, press the left mouse button (Windows) or (TBD) (Quest 2).

![Screen shots of an avatar holding a Wineglass in the default position and raising it in a toast.](../../../media/enhance-your-environment/equips-in-detail/006-wineglass-toast.png)

### Birthday Cake


### Drill

Activation mode: toggle




### Wrench


### Baseball


### Beachball

The Beachball uses a specfic type of throwing--it's more of a push than a throw. It's based on a vector from the attendee's neck and chest area towards the target reticle. The attendee can move around and aim the push. 

![Screen shots of an throwing the Beachball with a pushing motion.](../../../media/enhance-your-environment/equips-in-detail/009-beachball-throw.png)


### Trophy


### Tablet

## Grab and throw behaviors

In real life, certain objects that are in the same general category but have different shapes and sizes--for example, a softball, football, and beach ball--are held and thrown in different ways. With Mesh Equippables, these objects are grouped together into one category of "tossable" objects; all objects in this category are held and thrown the same way. A tossable object connects with a specific pre-loaded animation contained in the avatar. Providing more variety presents a technical challenge because it calls for more animations to be pre-loaded which could result in decreased performance. Despite this, we're working on an inverse kinematics (IK) system which we expect will provide more realistic grab-and-hold behaviors per object.


With this animation, you can look around the room--up, down, left or right 


Activation mode: toggle

An attendee may want to move around in an event and access a user interface that they can carry with them. The Tablet can provide this; you can attach events to objects on the screen of the Tablet, and then the attendee can trigger the events by touching the screen. One way to achieve this is by attaching a [WebSlate](../../enhance-your-environment/webcontent.md).

When the Tablet is activated, the attendee holds the Tablet up to their face but slightly lower than eye level. This means that the attendee has an unobstructed view if they look around the room. When the Tablet is deactivated, the Tablet is still held in front of the attendee but in a lower position.

![Screen shots of an avatar holding a Wineglass in the default lower position and the raised position.](../../../media/enhance-your-environment/equips-in-detail/008-tablet-hold.png)

### Coffee cup


### Wand




## Position of objects

There are different ways of holding an object. Some objects, when grabbed, are designed to be held away from the body and high enough to be in your field of view (for example, the Wineglass or Trophy). 

< TBD image>

Other objects are designed to be hold closer to the body and *not* in your field of view (for example, the Wrench). 

< TBD image>





NOTES:

Brandon said Equippables well be moving to an Assets/Equippables folder sometime soon.

For 3P developers (from David Wilson): when they go into Play mode they get no avatars spawned. They can't see what's going on with the interaction with the Equippable. They're 100% when trying to set up an object. They can only get to a result after they save, publish, and then create an enter an event. At that point they can't edit anything live. 7:52

Wineglass raise: the Animator is on the avatar. There are signals from the Interactable to the avatar via the Mesh Interactable Body component. With the Wineglass: 
Body type is Equippable (the object will be attached to the hand of the avatar.)
The dev can change the activation type via "Activate Target Poses." It's currently set to Toggle. Other choices: None and Single.
Dev can change the object type to "Throwable."

Wand, under the hood: it has an onHold() event. (?) It changes its state when it goes from not being held to being held. When it's activated, it's a "single instance" activation. It plays the VFX and audio and changes the avatar pose. 

To change the state, the avatar can click the screen anywhere except on the Equippable they're holding. 

There can be more than one pose that's incorporated into a transition. For example, with the Wand, it's not just a linear transition from A to B; there can be a wrist flick and the durtation of that transition can be adjusted in the Animation Curve.

![______](../../../media/enhance-your-environment/equips-in-detail/007-animation-curve.png)

Wand: The trigger is sent just before the last pose. If you're looking at the trigger activation that's sent by Mesh Interactable Setup, it sends it just before the last (pose?) there.

TO DO: David said there's a GIF available with the transition of the sizes of a ball pose for the hand. A Cylinder holding, and a pinch kind of pose. That's accessible in the old hand pose or in the throw hand pose or in the aim hand pose in the setup options. 21:00. The hand pose refers to the finger position (shows the avatar holding a coffee mug). Those are a series of dictated hand positions. Within the ball, pinch and cylinder, there's a flexible range that devs are able to tune. (Visual of the avatar holding a tea cup). This shows a small pinch vs. something else with a larger pinch. 

(David:)" We've created the prefabs in a way that devs can take their own art and if it's in a similar size and similar type of orientation, they can turn off ours (art?) and turn on theirs in the same structure. Each Equippable has a child object named "Artwork" which is where you can insert your custom model.  

Question: David mentioned that they're working on putting an avatar in the scene so devs have a basis of comparison for determining scale. He said it hasn't been approved yet. What's the status of that right now? Is this the object that Cameron talked about recently?

Brandon talks about the script graphs:

Nodes: IsMine, EquipLocation. If "EquipLocation" = None, that means the object was dropped. (I think you have to look for this in Mesh Interactable Setup). 39:42

Wand

The Wand is in the scene--it's static, it's just sitting there.

In the visual script attached to the Wand, the node that determines if the Wand is grabbed or not is *Mesh Interactable Body: Is Mine*. It's a Boolean, and starts with a value of False.

![______](../../../media/enhance-your-environment/equips-in-detail/010-is-mine-node.png)

My interpretation of the graph:

Things start with section 2:

IsMine is a Boolean with a default value of false.

TBD: Where does the value of  If the attendee picks up the Wand (IsMine = true), the state changes from false to true. If true, it triggers Play Mesh Audio and sets the startGlowVFX variable to true.

Section 5

With startFlowVFX now true, its state changes. If true, it sets the PersistentVFX variable to true. This is a variable of type *Object* and its value is the GameObject *vfx_wand_ethereal_perisstent_02*, which has a particle system attached which is now triggered.

Section 4

Activating the avatar

The click to activate the avatar is detected by the *Mesh Interactable Body: Is Activated* node. It's a Boolean with a default value of false. When the attendee clicks in the event, *Is Activated* changes to "true"; the *On State Changed" node detects the change and passes the "true" value on to the *If* node. This causes the *Set Variable* node to set the *isPressed* Boolean to the opposite of what it was before (so now it's "true").

Section 3

The *isPressed* node, a Boolean with a default value of "false", is now "true" and this true value reaches the *Set Variable: Object" node. This node sets the *startGlowVGX* variable to "false" and then, after a brief *Cooldown* period (TBD), it triggers a sound (TBD) and a particle system object named vfx_wand_blast_trail_spheres_01* which is the value of the *ShootTrailVFX* Object variable (TBD).

(After this, in the event, the avatar's arm returns to its starting position.)

Releasing the Wand

To release the Wand, the attendee presses the Space key and the Wand drops to the ground. When this happens, the *On State Changed* node (TBD) detects the change


