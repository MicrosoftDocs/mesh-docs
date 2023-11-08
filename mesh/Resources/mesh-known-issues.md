---
title: Known issues for Mesh
description: Active known issues for Mesh
ms.service: mesh
author: qianw211    
ms.author: qianwen
ms.date: 11/2/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Active known issues - Mesh

## Version 5.2313.0

* On Quest devices: users who remain idle for some time will be ejected out of an event. (21976)

* The current way for how to determine which version of the environment to use for an event will be improved. (23681)

    This is the current behavior we ship for Public Preview:

    * For a Event Customization Session: The latest version of an environment is always used in an event customization session.

    * For the Event itself: The environment used by the event is determined by the first join to the event.  So let's say by the time someone first joins the same Build Review event, the latest **Lakehouse** environment is version 3, the Build Review event will always use version 3.

    For future releases, organizers to an event will have better control over which version of the environment to use for their event, or the latest version of an environment is used by default.

* If an event organizer uses the Teams' calendar to make changes to the event, the location URI containing the Mesh sessionID will be erased, thus corrupting the Mesh event. (21568)

    *Workaround:* Organizers must not use the Teams' calendar to make any changes to the Mesh event. Using Outlook to make changes will work, but organizers shouldn't turn a Mesh event to a Teams meeting by adding Teams call link to it.
    
* On the Dashboard, the scroll bar length could be too long for the content being displayed. (19501)
* When downloading the Mesh app from Microsoft Store, some users will get a blank screen in the web browser. To search for the most current data on the server, press the **CTRL + F5** keys to clear your browser cache.  The latest version of the Microsoft store webpage will then load. (14921)


