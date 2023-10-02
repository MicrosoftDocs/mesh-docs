---
title: Known issues for Mesh
description: Active known issues for Mesh
author: qianw211    
ms.author: qianwen
ms.date: 9/28/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Active known issues - Mesh

## Version 5.2312.0

* The current way for how to determine which version of the environment to use for an event will be improved. 

    This is the current behavior we ship for Public Preview:

    * For a Event Collaboration Session:  The environment used by the event is determined by the first join to the collaboration session. So for example, a Build Review event is created when the latest **Lakehouse** environment is version 1, the collaboration session for the event will always use version 1.

    * For the Event itself: The environment used by the event is determined by the first join to the event.  So let's say by the time someone first joins the same Build Review event, the latest **Lakehouse** environment is version 3, the Build Review event will always use version 3.

    For future releases, organizers to an event will have better control over which version of the environment to use for their event, or the latest version of an environment is used by default. 

* You will need to make a new event for every new version of the environment that you upload. 

    For example:

    1. Upload an environment (let's call it version 1.0.0).
    2. Make an Event based on that environment.
    3. Join the event. At this point in time the event is tied to version 1.0.0.
    4. Re-upload my environment (let's call it version 2.0.0).
    5. Join the event I created in step 3.

    As the result, you'll get environment 1.0.0 rather than 2.0.0.

* If an event organizer uses the Teams' calendar to make changes to the event, the location URI containing the Mesh sessionID will be erased, thus corrupting the Mesh event. Trying to join such a corrupted event in Mesh will make the Dashboard go away, and the prejoin dialog will never show up. 

    *Workaround:* Organizers must not use the Teams' calendar to make any changes to the Mesh event. Using Outlook to make changes will work, but organizers shouldn't turn a Mesh event to a Teams meeting by adding Teams call link to it.
    
* When an avatar is being broadcasted in a Mesh event, it may disappear when viewed from certain angles while the broadcaster visual indicator remains visible during this time. 
* On the Dashboard, the scroll bar length could be too long for the content being displayed. 
* On the Dashboard, go to **All Worlds**, and holding down the scroll bar and leaving the UI dialog will bring you back on top of the screen. 
* On the Dashboard, scrolling through the **All Worlds** menu with the scroll wheel on the mouse jumps multiple pages at a time. 
* When downloading the Mesh app from Microsoft Store, some users will get a blank screen in the web browser. To search for the most current data on the server, press the **CTRL + F5** keys to clear your browser cache.  The latest version of the Microsoft store webpage will then load. 


