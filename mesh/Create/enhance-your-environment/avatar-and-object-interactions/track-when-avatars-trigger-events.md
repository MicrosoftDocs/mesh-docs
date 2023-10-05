---
title: Track when avatars trigger events
description: Learn how to set up trigger volumes that avatars can enter to trigger events.
author: jackiecurley
ms.author: vinnietieto
ms.date: 10/4/2023
ms.topic: overview
keywords: Microsoft Mesh, object and player interactions, interactables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw
---

# Track when avatars trigger events

## AvatarTrigger

An object that tracks when the local avatar enters and exits its trigger volume.

![Avatar Tether Script](../../../media/mesh-scripting/object-player-interactions/Picture3.png)

### Settings

**[Required Component] Collider:** A Collider is required to know what the trigger volume is. This should have **IsTrigger** set to true.

### Visual Scripting
- **Properties:** 
    - **LocalAvatarInTrigger** – true when the local avatar is inside the trigger
