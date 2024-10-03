---
title: Release notes for Immersive spaces in Teams
description: Immersive spaces in Teams release notes
ms.service: mesh
author: typride 
ms.author: tmilligan
ms.date: 4/19/2024
ms.topic: release-notes
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Immersive spaces in Teams release notes

**Release notes for the Immersive spaces in Microsoft Teams on PC & Quest 2**

## Version 5.1414.XX (September 30, 2024)

### Limitations & specifications for Immersive spaces

We have released a page describing the [limitations and specifications for immersive spaces in Teams](limitations-specifications-mesh.md), including the max number of participants across Mesh event scenarios, max duration of events, and more.

### Network bandwidth requirements for Immersive spaces

We have released the [network bandwidth requirements for various immersive experience scenarios](../Setup/Content/preparing-your-organization.md#network-bandwidth-requirements).

### Simplified firewall setup requirements

We have completed the rollout to simplify firewall setup requirements for immersive spaces in Teams. As part of this, you will no longer need to allow traffic to IP addresses in the "AzureCloud" service tag. To read more about the updated firewall setup requirements, see how to [Manage the Mesh app in Microsoft Teams](/microsoftteams/meeting-immersive-spaces).

For more info, please refer to [firewall requirements for Microsoft Mesh and immersive spaces in Teams](../Setup/Content/preparing-your-organization.md#endpoints-and-firewall-configuration).

## Version 5.2412.XX (September 03, 2024)

* Fixed an issue where customizing an avatar during a meeting could sometimes cause that avatar to not render correctly (shadows would be too strong).

* Fixed an issue where avatars could become invisible if more than six participants joined an Immersive Meeting.

* Fixed an issue where some avatars would only partially render (e.g., torso would be invisible) during an Event after teleporting.

## Version 5.2411.XX (August 20, 2024)

* Mesh participants will see reaction animations from Teams 2D participants overlaid on the appropriate webcam gallery tile inside the immersive space.

* Adding multi-keyboard support to Mesh, enabling keyboard interaction for millions of people that use languages like Hindi, Arabic, French (Azerty format) Russian, Thai, Kazakh, Bulgarian, Dvorak and Colemak.

* Multiple accessibility improvements including high contrast focus indicator, screen reader announcements, zoom in/out tooltips, and high contrast green screen settings.

## Version 5.2410.XX (August 5, 2024)

## Version 5.2409.XX (July 23, 2024)

### Avatar Reactions

* Ready to dance in Mesh? Get groovy with Avatar Reactions!

    We are excited to announce the release of Avatar Reactions for Mesh immersive experiences! In addition to the standard emoji-based reactions, you can now react with a wider variety of Avatar reactions, making avatar interactions more dynamic, personal, and fun!

    **Key Features:**

    *Expressive Animations:* Avatars can now perform a wider variety of reactions, including dancing, celebrating, and more.

    *Real-Time Reactions:* Reactions are performed in real-time, enhancing the liveliness of virtual meetings and interactions.

    :::image type="content" source="media/Avatar-reactions-immersive-space.png" alt-text="Screenshot of the reactions menu in an immersive space (3D).":::

    In addition to the standard Avatar reactions, you can find a lot of other reactions sorted into seven categories, including a category for ASL signs.

    :::image type="content" source="media/Reactions-immersive-spaces-menu-expanded.png" alt-text="Screenshot of the Reactions menu in an immersive space (3D)":::

### New loading screens

* Updated images and text when joining an Immersive Space in Teams.

### Personal boundary

* Avatars now have a Personal Boundary that prevents other avatars from walking, standing, and teleporting too close to your avatar.

* If you're in the middle of a crowd, you can now also teleport through other avatars to move away from the crowd.

## Version 5.2408.XX (July 01, 2024)

### Immersive spaces available on Mac

As of July 8th, 2024, the **View** > **Immersive space (3D)** option is available in Teams desktop for Mac, removing the requirement to be a part of the Teams Preview Experience to access immersive spaces on Mac.

### Resolved issues

* Fixed an issue where changing the environment settings in a Teams meeting in a channel didn't apply correctly. (17706)

## Version 5.2406.0 (May 23, 2024)

* For returning users, the pre-join screen with avatar selection and customization is skipped to make the experience of joining the immersive space faster. The second pre-join screen following the avatar selection and customization screen was also removed for new and returning users.

* If a user rejects the Terms of service, there is now the option to go Back to the Teams meeting.

## Version 5.2405.0 (May 13, 2024)

* More professional wardrobe styles are coming to the Avatar builder. Customize your avatar to see all the new and updated looks available to freshen up your avatar for your next meeting.

    :::image type="content" source="media/Avatar-wardrobe-update.png" alt-text="Screenshot of Avatar wardrobe updates. ":::

* Immersive spaces in Teams is now supported on Mac devices for customers in the [Teams Public Preview program](/MicrosoftTeams/public-preview-doc-updates?tabs=new-teams-client) in Rings 0, 1, 1.5, 2, and 3. 

* The Lakehouse icebreaker activity is localized into 41 languages.

* Seating layout names are now translated into 41 languages in the Oasis immersive environment.

* All default environments have their name and description localized into 41 languages.

## Version 5.2403.0 (April 18, 2024)

### What's new

### Resolved product issues

* In high contrast mode, the descriptions for Topics now don't disappear. (28695)

* On Quest, while loading an immersive meeting, the screen may go black and take longer than expected, causing users to become disoriented and hear other users before they enter the space. This has been fixed. (32893)

## Version 5.2401.0 (February 20, 2024)

### What's new

**Default Mic/Speaker Settings:** When going to the immersive space, Mesh will now sync with your Teams' audio device selection, resolving the previous potential misalignment with your system default audio device selection.

* Icebreaker activity with spheres is localized (translated) into 20+ different languages.

* Admins can now enable immersive spaces for users using service plans, instead of the previous method of using OCPS. Please refer to the [Mesh setup for admins](../Setup/Content/setup-m365-mesh.md) for more detail.

## Version 5.2315.0

### What's new

* The Meeting zone is now called the Teams screen share area. For more information, please see the immersive spaces documentation on [Spatial audio in Microsoft Teams meetings](https://support.microsoft.com/en-us/office/spatial-audio-in-microsoft-teams-meetings-547b5f81-1825-4ee1-a1cf-f02e12db4fdb?preview=true).

### Resolved product issues

The following product issues have been fixed for this release:

* Keys for dropping interactables, like marshmallow sticks in the Lake House, are the middle mouse button (scroll wheel) and space bar. This is communicated via a short pop up that users might overlook.

* Pressing Mesh buttons + the **Enter** key on the keypad produces no action. The same **Enter** key on the main keyboard selects the button and executes the associated action. (26462)

* If a user declines to give Mesh access to their microphone upon first launch in immersive spaces, they'll be completely muted without additional notification. 

    *Workaround:* If this occurs, you need to first switch to the new Teams client, and then try either of the following:
    
    - go into your Teams **Settings -> App permissions**. Select the **Mesh** app, and switch the **Media permissions** on.

        ![A screenshot of the Teams settings menu](media/teams-settings.png)

        ![the Mesh app permissions dialog in Teams settings](media/teams-app-permissions.png)

    - or [clear the Teams cache](/microsoftteams/troubleshoot/teams-administration/clear-teams-cache).


* When clicking the Immersive view in Teams, the user isn't able to get into the immersive space, and gets an error instead. (29271)

* In the new Teams client, when the presenter changes shared content, an error dialog pops up and displays: "Can't display content". (22587)

* In the new Teams client, going from immersive view back to the Teams gallery and then back to immersive space for the second time will crash Teams. (22854)

* When pressing the right mouse button inside the viewport and releasing it outside the viewport, whichever keyboard button pressed at the time of release will continue to trigger as soon as the user re-enters the immersive space. As a result, the user might walk or rotate (and possibly do other things) even when it's unintended. To resolve the issue, the user needs to trigger the same button again. (27944)


## Version 5.2314.0

### Resolved product issues

* Fixed: On Quest, two different mics are shown and both are named *Quest*. The second one won't capture audio, and no error is shown. (20795)

* The **Prejoin** dialog now show a thumbnail picture of the event. (20071)

* When trying to throw an object by clicking on the object, the cursor no longer shows. (25542)
* On the Teams meeting details page, event dates and times according now align with the Mesh event list to account for all-day or multiday events. (28309)

* All-day event times are no longer being converted to local time zones. (26665)

* Seats in the immersive spaces no longer show as blue and available even when there's another user sitting on it. (21535)

* When joining a Teams meeting, users on Quest no longer see a screenshare instead of the default background wall in the Lakehouse environment. (27425)

* The settings dialogs now show the current selected state for many settings. (17308)

* On Quest: the Mesh UI no longer locks with the user's head view. As you turn your head, the Mesh UI will now remain stationary. (13061)

* On Quest, you'll no longer be disconnected from a meeting when you remove your headset. (25764)

* Fixed the issue: On PC and Quest, when attempting to delete any Objects in the Environment Editor will crash Mesh while running. (28903)

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



