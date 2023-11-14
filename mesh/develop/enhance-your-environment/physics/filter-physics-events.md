---
title: Filter Physics events with Body Filters
description: Guide to using Mesh physics when creating Environments for Mesh.
author: michael-buschbeck-ms
ms.author: vinnietieto
ms.date: 10/18/2023
ms.topic: Guide
ms.service: mesh
keywords: Microsoft Mesh, Mesh physics, physics, environments, interactions, interactables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw
---

# Filter Physics events with Body Filters

Some components, such as Sticky Body, have a **Body Filter** setting (usually named **Affected Bodies**).

![___](../../../media/physics-interactions/006-trigger-body-filters.png)

This setting makes only Game Objects that meet certain preconditions eligible to trigger events. There are four main preconditions&#8212;to view them, click the plus sign ("+") button to the right of **Body Filter:**

![___](../../../media/physics-interactions/007-trigger-preconditions.png)

To understand the first precondition, **Game Object Name**, let’s imagine that there’s a dart game in your scene and you have numerous dart Game Objects that are named Dart01, Dart02, Dart03, and so on. You want any dart, but *only* darts, to be eligible to trigger events, so you filter for any Game Object that starts with the four letters "Dart".

1. Click the **Body Filter** "+" button and then select **Game Object Name**.  
1. In the text box next to **Starts With**, type in "Dart."

    ![___](../../../media/physics-interactions/008-trigger-starts-with.png)

You aren’t restricted to just using **Starts With**. You can filter for exact names, or only names that *end* with certain letters, and more. To see all your options, click the **Starts With** drop-down.

![___](../../../media/physics-interactions/014-name-options.png)

**Notes**

* Having multiple instances of the **Game Object Name** condition can make sense in certain situations&#8212;for example, to filter for names that have a given prefix *and* a given suffix.

* Text is case-sensitive.

**To filter for bodies based on their tag:**

* Click the **Body Filter** "+" sign and then select **Game Object Tag**.

The options for this condition are similar to the options for Game Object Name.

**Note:** Tag comparison is case-**in**sensitive.

**IMPORTANT:** Unity allows you to create custom tags, but you can’t use custom tags in Mesh. You must choose one of the pre-defined tags that Unity provides.

**To filter for bodies based on their mass:**

1. Click the **Body Filter** "+" sign and then select **Rigidbody Mass**.
1. Enter the minimum and maximum mass values a Game Object must have in order to trigger events.

**Important:** We recommend that you *don’t* have more than one instance of this condition active at any time. You can accommodate all potential Game Objects using a single Min/Max range.

**To filter for bodies based on their root Game Object:**
Let’s say you have a root Game Object named "Robot" in your scene. Robot has numerous child objects&#8212;arms, legs, and so on&#8212;and these have their own child objects. You want Robot and any of the Game Objects in its hierarchy to be eligible to trigger events.

1. Click the **Body Filter** "+" sign and then select **Root Game Object**.
1. Do one of the following:

* Drag the Game Object from the **Hierarchy** and then drop it in the **Root Game Object** field.

    -or-

* Click the round button in the **Root Game Object** field …

    ![___](../../../media/physics-interactions/015-button.png)

    … then, in the **Select GameObject** window, type in the name of Game Object you want to add, and then, in the resulting list, double-click the name of the Game Object.

    ![___](../../../media/physics-interactions/016-select-game-object.png)

Note that in this example, there are two animal robot types in the scene. If you wanted *all* robots to be eligible for triggering, you could add a **Game Object Name** condition that contains the text "Robot" anywhere in the name.

![___](../../../media/physics-interactions/019-name-contains.png)

**Important:** We recommend that you *don’t* have more than one instance of this condition active at any time. This can cause conflicts.

**Filtering with Multiple Conditions**

You can have more than one filter in your condition. For example, let’s say you want only larger or heavier robots&#8212;ones with a higher Mass value&#8212;to trigger events. You could search for Game Object names that contain "Robot" that have a minimum mass value of 100:

![___](../../../media/physics-interactions/020-compound-conditions.png)

**Note:** If multiple conditions are defined, a body must match *all* of the conditions to be eligible for triggering events.

**Options on the 3-dot menu**

Each condition has a 3-dot menu with several options.

![](../../../media/physics-interactions/035-body-filter-menu.png)

**Move Condition Up:** Moves the condition one position higher in the **Body Filter** list.

**Move Condition Down:** Moves the condition one position lower in the **Body Filter** list.

**Delete Condition:** Removes the condition from the **Body Filter** list.

**To make a condition active or inactive:**
Select or clear the checkbox to the left of the condition name.

## Next steps

> [!div class="nextstepaction"]
> [Mesh Physics Overview](../enhanced-features-overview.md)
