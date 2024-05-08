---
title: Hold objects realistically with Equippables
description: Learn about various equippable objects and the realistic ways they can be picked up and held.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 5/2/2024
ms.topic: overview
keywords: interactions, interactables, equippables, throwables, avatars, grab, pick up, hold, throw, attach, activate, activation
---

# Hold objects realistically with Equippables

## Overview

In the Toybox sample, certain prefabs are a type of [Interactable](./interactables.md) known as *Equippable*. When you pick up such an object, your hand and arm position adjust to hold the object in a realistic way. This is called *equipping an object to your hand*.

> [!NOTE]
> The Toybox sample is where we currently showcase our Equippables prefabs, but you can use the prefabs or create your own Equippables in any project.

There are eight Equippables:

- Wine glass
- Birthday cake
- Drill
- Wrench
- Trophy
- Tablet
- Coffee Cup
- Wand

To see the Equippables in Unity, in the **Scene** window, navigate into the building with the fish on the front. The Equippables are on two tables against the back wall.

![A screen shot of the first set of equippables in the Scene window.](../../../media/enhance-your-environment/equips-in-detail/012-table1.png)

![A screen shot of the second set of equippables in the Scene window.](../../../media/enhance-your-environment/equips-in-detail/013-table2.png)

Note that not all the objects on the tables are Equippables--the Baseball and Beach Ball are [*throwables*](./interactables.md#throwable). 

**To determine an object's type**:
1. Select the object.
1. In the **Inspector**, navigate to the *Mesh Interactable setup* component and then view the **Object Type** property.

    ![A screen shot of an object's type in its Mesh Interactabe Setup component.](../../../media/enhance-your-environment/equips-in-detail/014-object-type.png)

## Where to find Equippables

In the **Hierarchy**, the Equippables are nested prefabs to **Equipable Interactable Samples**, which is an instance of the prefab named *toybox_Equipable_Interactable_Samples*.

![A screen shot of the equippable prefabs in the Hierarchy.](../../../media/enhance-your-environment/equips-in-detail/001-equips-in-the-hierarchy.png)

In the **Project** window, the Equippable prefabs live in subfolders of the *Runtime* folder. These folders start with *Toybox_* followed by the name of the prefab. For example, the Wineglass prefab is stored in the *Toybox_Wineglass* folder.

![Screen shot of the wineglass prefab in the Toybox_WineGlass folder.](../../../media/enhance-your-environment/equips-in-detail/005-wineglass-location-in-folder.png)

**Tip**: To quickly find a prefab in the **Project** folder, in the **Hierarchy**, select the prefab, and then, in the **Inspector**, click the **Select** button.

## Position of objects

There are different ways of holding an Equippable object. Some objects, when when picked up, are designed to be held away from the body and high enough to be in your field of view (for example, the Wineglass or Trophy). Other objects are designed to be held closer to the body and *not* in your field of view (for example, the Wrench).

## Equippable behaviors

For some Equippables, you can pick them up and then press the left mouse button (PC) or controller button (Quest 2) to trigger an action that's appropriate for that Equippable. Examples:

- Raise and lower a Wine glass.
- Generate sparkles from the end of a Wand.
- Turn a drill off and on.

This is called *activating* the object. You can see the possible activate types in the object's *Mesh Interactable Setup* component. There are three activate options: *Single*, *Toggle*, and *None*.

![A screen shot of an object's activate type in its Mesh Interactabe Setup component.](../../../media/enhance-your-environment/equips-in-detail/015-activate-type.png)

**Single**: The object has a single "state", or set of behaviors. Example: the Wand. Think of this as turning the object "on" and "off" with one click. When you pick up the Wand, it's in its default (non-activated) state. When you click, the Wand runs through its behaviors and then immediately returns to its default state. If you click again, the object repeats the same set of behaviors.

**Toggle**: The object has two "states." When you pick it up, it might be in its activated or non-activated state. When you click, it toggles from whatever state it's in to its second state. This state, and the behaviors it triggers, remain active until you click again. This second click toggles the object back to the original state. Examples: the Wine Glass and the Drill. This should become more clear when we examine individual object behaviors in the sections below.

**None**: The object can't be activated. Example: the Birthday Cake. After you pick it up, there's nothing further you can do with it; you just hold it until you decide to release it.

![Screen shots of avatars holding the Wand, which is the single equippable activation type, and the Drill, which is the toggle equippable activation type.](../../../media/enhance-your-environment/equips-in-detail/003-activation-type-examples.png)

**Release an Equippable**

To release an Equippable, press the Space bar. This causes the Equippable to drop downwards.

## How each Equippable object works

### Wine glass

**Activation mode**: toggle

After you pick up the Wine glass, you click, and the glass raises--that's the activated state. To lower the glass to its default position and non-activated state, you must click again.

![Screen shots of an avatar holding a Wineglass in the default position and raising it in a toast.](../../../media/enhance-your-environment/equips-in-detail/006-wineglass-toast.png)

### Birthday Cake

**Activation mode**: None

![Screen shot of an avatar holding the Birthday Cake.](../../../media/enhance-your-environment/equips-in-detail/011-birthday-cake.png)

### Drill

**Activation mode**: toggle

When you pick up the drill, it's automatically activated--it's held out in front of you and turned on. When you click, the drill turns off and your arm moves the drill down to your side. When you click again, the drill goes back into its turned-on state. This is a good example of the "toggle" activate type, which always toggles between two states.

![Screen shot of an avatar holding the Drill.](../../../media/enhance-your-environment/equips-in-detail/016-drill.png)

### Wrench

**Activation mode**: toggle

When you pick up the Wrench, it's automatically activated--it's held out in front of you almost chest high. When you click, the wrench is lowered to your side and de-activated. Click again to activate it again.

![Screen shot of an avatar holding the Wrench.](../../../media/enhance-your-environment/equips-in-detail/017-wrench.png)

### Trophy

**Activation mode**: toggle

When you pick up the Trophy, you hold it out in front of you chest high. Click to activate it; this raises the Trophy above your head in a "salute" position. Click again to lower (and de-activate) the Trophy.

![Screen shot of an avatar holding the Trophy.](../../../media/enhance-your-environment/equips-in-detail/018-trophy.png)

### Tablet

**Activation mode**: toggle

The Tablet is viewed by many as one of the more useful Equippables because you can attach a UI object with buttons or a [WebSlate](../webcontent.md) to its screen and then move around the scene with it. When you pick up the Tablet, you hold it out in front of you chest high. Click once to activate the Tablet--this raises it up to almost eye level, but leaves you with an unobstructed view if you wish to look around the room. Click again to lower it back to its initial position (and de-activate it).

![Screen shot of an avatar holding the Tablet.](../../../media/enhance-your-environment/equips-in-detail/019-tablet.png)

## Coffee cup

**Activation mode**: none

![Screen shot of an avatar holding the Coffee cup.](../../../media/enhance-your-environment/equips-in-detail/020-coffee-cup.png)

## Wand

**Activation mode**: single

When you pick up the Wand, you hold it out in front of you almost chest high. The tip of the Wand displays a sparkly vapor particle effect. 

:::image type="content" source="../../../media/enhance-your-environment/equips-in-detail/wand-holding1.gif" alt-text="GIF that shows an event attendee holding the Wand in its non-activated state.":::

Click to activate the Wand; your arm thrusts forward and the tip of the Wand emits fireworks that are generated through another particle effect. 

:::image type="content" source="../../../media/enhance-your-environment/equips-in-detail/wand-thrusting1.gif" alt-text="GIF that shows an event attendee activating the Wand which then generates fireworks.":::

Since the Wand has the *single* activate type, as soon as it runs through its behaviors, it de-activates and your arm returns to its initial position. Click again to repeat the behaviors.



## Create a custom Equippable

If you have a model that's similar in size and orientation to one of our Equippable prefabs, you can replace the Equippable model with your model. Each prefab has a child object named "Artwork" which is where you can insert your custom model.

## Next steps

> [!div class="nextstepaction"]
> [Equippables&#8212;How the Wand works](./how-the-wand-works.md)