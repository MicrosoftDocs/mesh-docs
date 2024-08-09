---
title: Known issues for Mesh
description: Active known issues for Mesh
ms.service: mesh
author: typride    
ms.author: tmilligan
ms.date: 4/19/2024
ms.topic: release-notes
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Active known issues - Mesh

## Mesh app in Teams (August 12, 2024)

> [!IMPORTANT]
> Currently, the Mesh app in Teams only available to organizations in [Mesh TAP](../develop/mesh-tap-participants.md).

For Mesh TAP participants that are testing the Mesh app in Teams, please read through the known issues and limitations listed below:

* **Outlook Calendar invites** for Mesh events will provide the option to open the Mesh app for Windows only. To join events using the Mesh app in Teams, please open to the Mesh app in Teams and join events directly.

* **Attendees**

  * Audio device selection does not inherit automatically from Teams.
  * Some text that is shown as users launch the Mesh app may not yet be localized into languages other than English.
  * The selfie feature is disabled currently.
  * Outgoing screenshare is not currently supported.

* **Organizers**

  * Image/Video objects cannot reference SharePoint URLs.
  * There is currently no warning to organizers when attempting to create an event and use environment in the Mesh app in Teams that does not have the WebGL build module. For environments to be used in the Mesh app in Teams they must have been published using the Mesh Toolkit uploader with the WebGL build module.

* **Developers**

  * Visual artifacts may arise if custom Unity materials write to depth (e.g., translucency).
  * If you intend to use WebSlates in an environment for the Mesh app in Teams (building environments for HTML5), we recommend ensuring that all content can run inside of an `<iframe>`. To ensure this, use embeddable content URLs on WebSlates.
  * WebSlates that do not work in an `<iframe>` will show an error message on the slate. Keep in mind that testing in Play Mode will show content as if it's running on native PC app.
  * Coming soon: Web content incapable of running in the Mesh app in Teams will show an error message during Build and Publish in the Mesh Uploader.

## Version 5.2403.0 (April 18, 2024)

* Single room and multi-room events require the same firewall endpoint and port configurations. We are actively working to resolve this issue and apologize for any inconvenience.

## Version 5.2402.0 (March 12, 2024)

* There may be a travel time latency that occurs when joining a space, which can cause avatar movement and audio to be out of sync, causing confusion while interacting with other users in the same space. This issue is more pronounced in custom environments where certain environment and event building occurs, causing the aggregate latency to be more pronounced.

* On starting a broadcast, broadcasters may experience a temporary low framerate. (32963)

* Keys for dropping interactables, like marshmallow sticks in the Lake House, are the middle mouse button (scroll wheel) and space bar. This is communicated via a short pop up that users might overlook. (32968)

## Conditional access on Quest

* In order to access Mesh on Quest with conditional access policies that may block Mesh on Quest, the solution is to create a custom conditional access policy in Microsoft Entra to exclude Microsoft Mesh Services and Office 365.

## Version 5.2401.0 (February 20, 2024)

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
