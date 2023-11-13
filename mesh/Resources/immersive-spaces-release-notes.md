---
title: Release notes for Immersive spaces in Teams
description: Immersive spaces in Teams release notes
ms.service: mesh
author: qianw211    
ms.author: qianwen
ms.date: 11/13/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Immersive spaces in Teams release notes

**Release notes and known issues for the Immersive spaces in Microsoft Teams on PC & Quest 2**

## Version 5.2314.0 (Preview)

### Resolved product issues

1. Fixed: On Quest, two different mics are shown and both are named *Quest*. The second one won't capture audio, and no error is shown. (20795)

1. The **Prejoin** dialog now show a thumbnail picture of the event. (20071)

1. When trying to throw an object by clicking on the object, the cursor no longer shows. (25542)

1. On the Teams meeting details page, event dates and times according now align with the Mesh event list to account for all-day or multiday events. (28309)

1. All-day event times are no longer being converted to local time zones. (26665)

1. Seats in the immersive spaces no longer show as blue and available even when there's another user sitting on it. (21535)

1. When joining a Teams meeting, users on Quest no longer see a screenshare instead of the default background wall in the Lakehouse environment. (27425)

1. The settings dialogs now show the current selected state for many settings. (17308)

1. On Quest: the Mesh UI no longer locks with the user's head view. As you turn your head, the Mesh UI will now remain stationary. (13061)

1. On Quest, you'll no longer be disconnected from a meeting when you remove your headset. (25764)

1. Fixed the issue: On PC and Quest, when attempting to delete any artifacts in the Environment Editor will crash Mesh while running. (28903)

## Version 5.2313.0

### What's new

New interactions for [equippable objects](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects) in the Bean Bag Toss and Marshmallow social games and activities.

#### For Bean Bag Toss on PC (in Teams)

* Left mouse click on the bean bag to pick it up (same behavior as before).

* Once you click on a bean bag, you'll go into aim mode:  

    * You can move the mouse cursor around to aim where you want to throw.

    * If you want to drop the bean bag, click **Space bar** on your keyboard. 

* Left mouse click to throw the bean bag.

#### For Marshmallow Roasting on PC (In Teams)

* Left mouse click on the marshmallow stick to pick it up (same behavior as before)

* To roast the marshmallow, you simply walk up to the firepit so the marshmallow is over the fire.  

    >[!Note]
    >It's no longer required to left mouse click to extend the marshmallow into the fire.

* To drop the marshmallow, click **Space bar** on your keyboard



