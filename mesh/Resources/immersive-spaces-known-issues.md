---
title: Immersive spaces for Teams known issues
description: Currently active known issues for Immersive spaces for Teams
author: qianw211    
ms.author: qianwen
ms.date: 8/31/2023
ms.topic: Guide
keywords: Microsoft Mesh, immersive spaces, Mesh, release notes
---

# Active known issues - Immersive Spaces for Teams

## Version 2023-8-30

1. **Default Mic/Speaker Settings**: Spatial Audio uses the same microphone and speaker as default OS settings, which might be a different mic and speaker that Teams uses. Users can switch which mic/speaker Mesh uses by going to the Immersive space and select **Settings > Audio** and updating mic and speaker settings.
1. **Bluetooth Headset Limitations**: Most Bluetooth audio headsets switch to mono output when the microphone is in use. With mono output you will not be able to experience spatial audio. Here’s what you can do to resolve the issue: 

    * Switch to a wired headphone, or
    * If you’re on a Bluetooth headset, in Teams **Audio Settings**, update the Microphone setting to use laptop Mic instead.

    >[!Note]
    >The most used Bluetooth audio profiles are **Stereo (recv-only)** and **Mono (send+recv)**. Using laptop mic allows the headphones to use the former mode.

    ![A screenshot of the Device settings menu](media/device-settings-menu.png)
 
1. **Dropped audio when switching environments**: When you switch environments, your audio may temporarily drop. 
1. **Background noise cancelation**: Spatial Audio background noise cancellation is currently limited. 
1. The Mesh app can be pinned to meetings but will not work for immersive spaces. The only way to get to the immersive space is to use the Teams **View** menu from inside a Teams meeting. 

    1. You cannot access immersive spaces with the Mesh app pinned to the Teams menu. 
    1. Same for installing the Mesh app: it’s not useful to install the app. 

1. If you are losing internet connection during a session in the immersive space, you will be disconnected and removed from the space. You will need to join the Teams meeting and rejoin the immersive space manually.
1. Joining an immersive meeting from different Teams rings may cause compatibility issues. Ensure all immersive space users are joining from the highest ring for better stability.
1. There is a room size limit of 16 persons for immersive users, while there’s no limit on the number of participants in a 2D Teams meeting. 
1. Content limitations: PowerPoint Live and Whiteboard are not supported.
1. There is no recording of the immersive space for a Teams meeting. The standard Teams meeting recording will still be available.
1. When sharing screen with audio from a Teams meeting, the audio won’t play in the immersive space on virtual stage.
1. There is now only one **hand-raise** button in the Teams menu. We have removed the hand-raise button from the Immersive space app bar. If you would like to participate in meeting discussions, select the Teams **hand-raise** button to raise your hand.
1. Mesh immersive space for Teams today can take up to a minute to load. Be patient as we improve the performance of the app. 
1.	When you share content while already in an immersive space, you will not see your own content on the virtual stage. Other meeting participants will be able to see the main stage.  You will only see the screen share window in Teams.
1. Using the **React** options in the Teams UI will not trigger any gestures of the avatar in the immersive space. Other users will still see you emote on their screen. Immersive space users should use the Mesh menu bar to emote, which will both trigger your avatar gestures as well as show the emote on other participants screens. 
1. Chat in Quest can’t render images, only text. In addition, texts don’t wrap. 
1.	On Quest, the text doesn't wrap in the feedback form.
1. Mesh immersive spaces will not work for cross-tenant calls. For example, Mesh customers cannot join immersive spaces with their own customers, nor can they join meetings with co-workers in other tenants.
1.	In Teams Immersive spaces, the **Leave seat** and **<** buttons have a black line running through them in high contrast mode.

    ![A screenshot of the Leave seat button](media/leave-seat-button.png)
 
1.	Text for **Microphone** settings in the pre-join dialog box isn’t readable in high contrast mode.
1.	On Quest, if you try to rotate the avatar preview in the Avatar Customizer, your field of view will also move.
1.	Users who are experiencing poor network quality may see problems such as missing avatars and audio glitches. We are actively working on integrating notifications to alert users when they are in this state.
1.	On Quest, the **Event details** dialog and the **Invite list** for an event will show up as blank when accessed through the Dashboard Homepage.
1.	A single user joining Mesh from multiple devices will result in audio issues. Do not join from multiple devices at this time. This is not a supported use case.


