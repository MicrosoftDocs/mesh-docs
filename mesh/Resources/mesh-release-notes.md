---
title: Release notes for Mesh
description: Mesh release notes
author: qianw211    
ms.author: qianwen
ms.date: 11/13/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Mesh release notes

**Release notes and known issues for the Immersive spaces in Microsoft Mesh on PC & Quest 2**

## Version 5.2314.0 (Preview)

### What's new

### Resolved product issues

* On Quest: the Mesh UI no longer locks with the user's head view. As you turn your head, the Mesh UI will now remain stationary. (13061)

* While a seating layout change is in progress, the seats are no longer clickable. (27509)

* You will no longer feel a slight bump in your position after teleporting to an inclined surface. (24915)

* The settings dialogs now show the current selected state for many settings. (17308)

* When trying to throw an object by clicking on the object, the cursor no longer shows. (25542)

* On Quest devices: to pick up an [equippable object](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects), you can simply bring your hand close to the object and click the Grip button.  

    Previously, you need to point the controller ray at the object and click the **Grip** button. This feels very unnatural for interaction with objects that are near.  When you're very close to an object, it's hard to point your controller ray at it to interact. (24187)

#### Events

* For users with a license for Teams Premium but without Teams Core, we do not block their entrance into Mesh on PC, however they will not be able to access any events. We have provided the user with a more accurate error why they are not able to see events. (25623)

* All-day event times are no longer being converted to local time zones. (26665)

* Fixed the issue: on template name update, changes are not immediately reflected in customization session. (25153)

* In the **Control Panel** dialog, the **Video Player** URL box no longer incorrectly displays the text "Placeholder" (14889)

## Version 5.2313.0

### Resolved product issues

* On Quest, there’s a crackling sound when you try to click on the **Customize** button under **Profile**. (16203)
* In the Mesh user profile dialog box, switching avatars will cause the avatar preview to briefly flash. (12762)
* On Quest, the **Event details** dialog and the **Invite list** for an event will show up as blank when accessed through the Dashboard Homepage. (13085)
* For some microphones, the user may sometimes need to speak louder than normal to trigger both lip-sync and background highlighting of the name plate. (48816)
