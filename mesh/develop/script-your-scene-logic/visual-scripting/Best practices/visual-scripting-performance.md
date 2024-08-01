---
title: Mesh Visual Scripting best practices for performance
description: Learn about improving performance for Visual Scripting in Mesh.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 8/1/2024
ms.topic: conceptual
keywords: Microsoft Mesh, scripting, visual scripting, coding, nodes, units, graphs, Mesh, best practices, performance
---

# Mesh Visual Scripting best practices for performance

## Overview

Visual scripts aren't slow, but they're much, much slower than, for example, C# code.

When you create visual scripts in your environment, it's best to use them to connect existing functionality, not for heavy lifting: **make glue, not girders**. The simplest way to ensure that your visual scripts don't impact the overall performance of your environment is to make sure they're not doing much at all in the first place.

## High- and low-frequency script events

Visual Scripting offers a wide selection of events you can use to trigger visual script flows.

Try to avoid:

- *On Update*, *On Fixed Update*, *On Late Update*, and similar. These events trigger very frequently (often at the same rate as render frames), and even if your script doesn't do a lot, even just starting it up has an overhead that can noticeably impact your environment's performance if it happens in many places at once. 

- *On Trigger Stay* and *On Collision Stay*. Even though these events are only active under certain conditions (for example, when a physics object is inside a physics trigger volume or touching a collider), while those conditions are given, they'll trigger very frequently.

There's no direct preferred replacement for these high-frequency events. They're not disabled, so you can use them if it's absolutely necessary, but we recommend that you try to leverage built-in functionality such as the Animator component, which can be controlled by visual scripts, or restructure your script logic to be reactive rather than active--for example, by using *On State Changed* events.

If you can't avoid these high-frequency events, you may be able to reduce their impact by keeping the entire *Script Machine* component inactive when it's not needed. Another visual script can use *Script Machine* | *Set Enabled* to disable and enable an entire script graph. While disabled, none of its event nodes trigger, and it has zero runtime cost.

These are slightly dangerous for performance but sometimes necessary:

- *On Collision Enter* and *On Collision Exit*. Normally, these events are triggered only once when a physics body touches the collider, and once again when it stops touching. However, sometimes a physics body gets stuck between two colliders; in that case, it can start jittering rapidly back and forth, triggering many *On Collision* events in very quick succession. We recommend that you use *On Trigger*  events instead.

These are okay to use in certain situations:

- *On Interval* lets you trigger script flows in customizable intervals (for example, once per second) defined through its *Interval* setting. You can use the *Delay* setting to stagger execution of different *On Interval* events that have the same interval.

- The Timer node isn't an event but will trigger its *Tick* port once per frame for the timer's duration once it has been started by entering its *Start* port. When the timer isn't running, it has zero runtime cost.

Try not to use these events to keep checking if certain variables, properties, or conditions have changed--instead, it's better to use an *On State Changed* event to listen to changes at zero idle cost.

These are always okay to use:

- *On State Changed* triggers only if and when any of its input ports change their value. For script variables and component properties, this is implemented very efficiently in a way that incurs zero runtime cost as long as nothing changes.

- *On State Changed* can also be used to observe more complex inputs (for example, the results of a calculation) that require it to re-evaluate the input once per frame to determine if it has changed. You'll have to enable the *Allow Polling* option to enable this feature; the script editing user interface will inform you of this and warn you about the potential performance impact. Even so, it'll still be a bit more efficient than to script your own polling logic using an *On Update* event.

- *On Dictionary Item Added* and *On Dictionary Item Removed* work in a similar way and have zero runtime cost as long as nothing changes.

- *On Trigger Enter* and *On Trigger Exit* have none of the potential performance dangers of the corresponding *On Collision* events (see above).

## Next steps

> [!div class="nextstepaction"]
> [Visual Scripting best practices overview](./visual-scripting-best-practices-overview.md)
> [Visual Scripting best practices for networking](./visual-scripting-networking.md)
> [Visual Scripting best practices for debugging](./visual-scripting-debugging.md)
