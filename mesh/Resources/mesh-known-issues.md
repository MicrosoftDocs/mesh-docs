---
title: Known issues for Mesh
description: Active known issues for Mesh
ms.service: mesh
author: typride    
ms.author: tmilligan
ms.date: 1/17/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Active known issues - Mesh

## Version 5.2401.0

* On starting a broadcast, broadcasters may experience a temporary low framerate. (32963)

* On Quest, the avatar's level of details (LOD) may seem off or changing depending on the actions an avatar takes such as nodding or looking up and down. (32894)

## Version 5.2315.0

* Pressing Mesh buttons + the **Enter** key on keypad produces no action, the same **Enter** key on the main keyboard selects the button and executes the associated action. (26462)

* When downloading the Mesh app from Microsoft Store, some users will get a blank screen in the web browser. To search for the most current data on the server, press the **CTRL + F5** keys to clear your browser cache. The latest version of the Microsoft store webpage will then load. (14921)

* On Quest, when a user is trying to join an immersive space meeting and is shown a "loading is taking a long time" popup dialog, the user will get kicked out of the immersive meeting with an error. (32893)

* On PC, the avatar's eyes do not follow the selfie camera. (32895)

* Users may find it hard to figure out how to drop interactable objects. The keys for dropping interactable objects - such as marshmallow sticks in the Lake House environment, are the middle mouse button (scroll wheel) and the space bar. This is communicated via a short pop up that users might overlook. (32968)

### Events

* If an event organizer uses the Teams' calendar to make changes to the event, the location URI containing the Mesh sessionID will be erased, thus corrupting the Mesh event. (21568)

    *Workaround:* Organizers must not use the Teams' calendar to make any changes to the Mesh event. Using Outlook to make changes will work, but organizers shouldn't turn a Mesh event to a Teams meeting by adding Teams call link to it.

* The current way for how to determine which version of the environment to use for an event will be improved. (23681)

    This is the current behavior we ship for Public Preview:

    * For a Event Customization Session: The latest version of an environment is always used in an event customization session.

    * For the Event itself: The environment used by the event is determined by the first join to the event.  So let's say by the time someone first joins the same Build Review event, the latest **Lakehouse** environment is version 3, the Build Review event will always use version 3.

    For future releases, organizers to an event will have better control over which version of the environment to use for their event, or the latest version of an environment is used by default.

* On Quest devices: users who remain idle for some time will be ejected out of an event. (21976)

* On starting broadcast, broadcasters might experience temporary low framerate due to unoptimized code. (32963)

## Current limitations

* Currently, audio capture and text input from users are not supported in Mesh. (35598)
