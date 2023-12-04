---
title: Known issues for Mesh
description: Active known issues for Mesh
ms.service: mesh
author: qianw211    
ms.author: qianwen
ms.date: 12/4/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Active known issues - Mesh

## Version 5.2314.0

* Searching for co-organizers on the Invite page yields no results. (29365)

* On Quest, the user is disconnected from an event if headset is removed. (25764)

* Pressing Mesh buttons + the **Enter** key on keypad produces no action, the same **Enter** key on the main keyboard selects the button and executes the associated action. (26462)

* When downloading the Mesh app from Microsoft Store, some users will get a blank screen in the web browser. To search for the most current data on the server, press the **CTRL + F5** keys to clear your browser cache.  The latest version of the Microsoft store webpage will then load. (14921)

### Events

* If an event organizer uses the Teams' calendar to make changes to the event, the location URI containing the Mesh sessionID will be erased, thus corrupting the Mesh event. (21568)

    *Workaround:* Organizers must not use the Teams' calendar to make any changes to the Mesh event. Using Outlook to make changes will work, but organizers shouldn't turn a Mesh event to a Teams meeting by adding Teams call link to it.

* The current way for how to determine which version of the environment to use for an event will be improved. (23681)

    This is the current behavior we ship for Public Preview:

    * For a Event Customization Session: The latest version of an environment is always used in an event customization session.

    * For the Event itself: The environment used by the event is determined by the first join to the event.  So let's say by the time someone first joins the same Build Review event, the latest **Lakehouse** environment is version 3, the Build Review event will always use version 3.

    For future releases, organizers to an event will have better control over which version of the environment to use for their event, or the latest version of an environment is used by default.

* On Quest devices: users who remain idle for some time will be ejected out of an event. (21976)

* The Megaphone indicator is currently broken - it doesn't tell the users who's currently using the megaphone feature. (29315)


## Version 5.2313.0

* On Quest: the Mesh UI is currently locked with the user's head view. As you turn your head, the Mesh UI will also turn, which can give a nauseating experience in VR. (13061)

* During a seating layout change, if you click on one of the seats in the old layout, you maybe seated in the new layout without a seat underneath your avatar. You will be locked in the seating position, unable to get out of the seat that's no longer there or move. (27509)

* If a participant teleports to an inclined surface, they may exprience a slight bump in their position. (24915)

* On Quest, when running multiple video players will cause the videos to flicker intensely. (24490)

* Pressing Mesh buttons + the **Enter** key on keypad produces no action, the same **Enter** key on the main keyboard selects the button and executes the associated action. (26462)

* The settings dialogs currently don't show the selected state for many settings. (17308)

* On PC and Quest, when attempting to delete any artifacts in the **Environment Editor** will crash Mesh while running. (28903)

* When trying to throw an object by clicking on the object, the cursor still shows. (25542)

* On Quest devices: to pick up an [equippable object](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects), you need to point the controller ray at the object and click the Grip button. If you simply bring your hand close to the object and click Grip button, nothing will happen.  This feels very unnatural for interaction with objects that are near.  When you're very close to an object, it's hard to point your controller ray at it to interact. (24187)

* On the Dashboard, the scroll bar length could be too long for the content being displayed. (19501)
* When downloading the Mesh app from Microsoft Store, some users will get a blank screen in the web browser. To search for the most current data on the server, press the **CTRL + F5** keys to clear your browser cache.  The latest version of the Microsoft store webpage will then load. (14921)
=======

* The Megaphone indicator is currently broken - it doesn't tell the users who's currently using the megaphone feature. (29315)

### Events

* If an event organizer uses the Teams' calendar to make changes to the event, the location URI containing the Mesh sessionID will be erased, thus corrupting the Mesh event. (21568)

    *Workaround:* Organizers must not use the Teams' calendar to make any changes to the Mesh event. Using Outlook to make changes will work, but organizers shouldn't turn a Mesh event to a Teams meeting by adding Teams call link to it.

* The current way for how to determine which version of the environment to use for an event will be improved. (23681)

    This is the current behavior we ship for Public Preview:

    * For a Event Customization Session: The latest version of an environment is always used in an event customization session.

    * For the Event itself: The environment used by the event is determined by the first join to the event.  So let's say by the time someone first joins the same Build Review event, the latest **Lakehouse** environment is version 3, the Build Review event will always use version 3.

    For future releases, organizers to an event will have better control over which version of the environment to use for their event, or the latest version of an environment is used by default.

* On Quest devices: users who remain idle for some time will be ejected out of an event. (21976)

* For users with a license for Teams Premium but without Teams Core, they can start Mesh on PC, but they will not be able to access any events. The error message "Couldn't connect to Teams" doesn't describe this specific problem. (25623)

* Currently, all-day event times are being converted to local time zones. (26665)

* When a template name is updated, the name change doesn't immediately show up in the customization session of the event. (25153)

* In the **Control Panel** dialog, the **Video Player** URL box incorrectly displays the text "Placeholder" (14889)

* The Megaphone indicator is currently broken - it doesn't tell the users who's currently using the megaphone feature. (29315)
