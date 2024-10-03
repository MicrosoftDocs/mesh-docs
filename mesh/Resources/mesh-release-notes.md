---
title: Release notes for Mesh
description: Mesh release notes
ms.service: mesh
author: typride  
ms.author: tmilligan
ms.date: 09/18/2024
ms.topic: release-notes
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Mesh release notes

## Version update history

Microsoft Mesh application

| Release year | Release date | Mesh version |
|--------------|--------------|--------------|
| 2024         | September 30 | 5.2414.XX    |
| 2024         | September 17 | 5.2413.XX    |
| 2024         | September 02 | 5.2412.XX    |
| 2024         | August 19    | 5.2411.XX    |
| 2024         | August 05    | 5.2410.XX    |
| 2024         | July 23      | 5.2409.XX    |
| 2024         | July 02      | 5.2408.XX    |
| 2024         | June 17      | 5.2407.XX    |
| 2024         | May 23       | 5.2406.XX    |
| 2024         | May 13       | 5.2405.XX    |
| 2024         | April 18     | 5.2403.XX+   |
| 2024         | April 09     | 5.2403.XX    |
| 2024         | March 11     | 5.2402.XX    |

**Release notes for Microsoft Mesh on PC & Quest 2**

## Version 5.2414.XX

## What's new

### Simplified firewall setup requirements

We have completed the rollout to simplify firewall setup requirements for immersive spaces in Teams. As part of this, you will no longer need to allow traffic to IP addresses in the "AzureCloud" service tag. To read more about the updated firewall setup requirements, see how to [Manage the Mesh app in Microsoft Teams](/microsoftteams/meeting-immersive-spaces).

Additionally, users will no longer need to agree to the terms associated with Mesh's previous spatial audio infrastructure. Mesh events now use the same audio infrastructure as Microsoft Teams.

Please refer to [firewall requirements for Microsoft Mesh and immersive spaces in Teams](../Setup/Content/preparing-your-organization.md#endpoints-and-firewall-configuration) for more info.

### Avatar mouth movement

Avatar mouth movement is now more realistic, conveying the words you speak or vocalize more accurately than before. Mouth movement for avatars in Mesh events is now equivalent in terms of realism to the mouth movement seen in Avatars in Teams.

## Resolved issues

* Avatar body now disappears when the camera or perspective enters the avatar position to prevent the avatar body from obscuring anybody's perspective. (63532)

* App crashes caused by leaving a session or loading the text controllable. (63983, 640530)

## Version 5.2413.XX

## What's new

### New Workshop environment

The Workshop environment is now available to all customers for use in Events or immersive spaces in Teams meetings.

:::image type="content" source="media/Workshop-environment.png" alt-text="Screenshot of workshop environment in the Mesh app in Teams, the environment switcher is open.":::

Use the main stage to get the whole the team together then use the four breakout spaces to convene in and workshop ideas.

:::image type="content" source="media/Workshop-environment-2.png" alt-text="Screenshot of workshop environment in Mesh.":::

### Anyone in your organization can now join Mesh events using the event link

Now anyone in your organization can join a Mesh event using just the Mesh event link.

Using the same link that's used to join a Mesh event directly or rejoin past events, you can now share that link with other people in your organization who you didn't specifically invite in Mesh on the web.

:::image type="content" source="../media/mesh-event-producer-guide/Join-event-link-calendar-rejoin.png" alt-text="Screenshot of calendar invite for a Mesh event showing the join the event link highlighted.":::

> [!IMPORTANT]
> As of now, in order for someone to join using the event link without being invited, someone who is invited must join first, such as a the organizer, co-organizer(s), or attendee(s).

To recap some great new features, Mesh event links can be:

* Shared with anyone in your organization to join Mesh events directly (as long as someone who *is* invited joins first)

* Used to rejoin past events

* Used to join Mesh events directly

## Resolved issues

* Closing the standalone app, while joining an event, won't show an error to the user anymore. (20151)

* Network connection issues, when in an event, would sometimes show a generic error message instead of telling the user they lost their network connection. (20760)

* Fixed a regression in app startup performance introduced in 24.12. (202250)

* Resolved an issue where cross-room reaction visualizations might not appear for organizers. (211430)

## Version 5.2412.XX

## What's new

### Mesh in Teams

We're excited to announce our first Mesh TAP preview of Mesh events running inside Teams!

:::image type="content" source="media/Mesh-in-teams-marketing-3.png" alt-text="Screenshot of Mesh in Teams showing the Mesh app open in Teams.":::

This key next step for Mesh addresses many of the top requests we've heard from you since Mesh reached GA:

- **Mac support:** Attendees can now join Mesh events from Mac devices

- **No native app needed:** IT admins no longer need to deploy a Mesh native app for Windows

- **Runs in web browsers:** Supports the Teams web client in Edge/Chrome, in addition to the Teams desktop client

- **Trust:** Run your Mesh events inside Teams, the app your employees already trust for secure communication

Mesh events run inside the Mesh app within Teams.  This app is available to preview now for Mesh events that you organize in any
Mesh TAP tenant, even if your tenant runs Teams in its Public ring.  This Mesh app is the same app that has supported
immersive spaces in Teams meetings since GA. What's new now is that the app is visible in the left rail of the Teams client and can be used to browse/join Mesh events.

This Mesh TAP preview supports creating Mesh events using the built-in environments, Oasis and Meadow. This preview does not support other environments you upload from Unity using the Mesh Toolkit, as they will not contain a WebGL asset bundle.  We don't have anything to announce today regarding support for custom environments uploaded with the Mesh toolkit.

### Organizer tools and People panel

The menu bar in the Mesh application has been reorganized to help Mesh event organizers better manage attendee participation and see who is in their Mesh event.

1. **Organizer tools**: Mute all, enable/disable Handraise, Megaphone, Screenshare, and Broadcast (for Multi-room events) are all located in the left Organizer tools button in the Menu bar.

    **Single room events**

    :::image type="content" source="media/Organizer-tools-people-panel-single-room-2412.png" alt-text="Screenshot of the organizer tools and people panel in the Mesh app.":::

    **Multi-room events**

    :::image type="content" source="media/Organizer-tools-people-panel-multi-room-2412.png" alt-text="Screenshot of Organizer tools and People panel in the Mesh app.":::

1. **People panel**: The people in your event can now be found in the People panel. In this panel, you can see who has raised their hand and megaphone or broadcast (in multi-room events) them.

    **Single room events**

    :::image type="content" source="media/People-panel-single-room-2412.png" alt-text="Screenshot of the Mesh app showing the people panel in a single room event.":::

    **Multi-room events**
    For Multi-room events, you'll be able to switch between the People tab and the Additional rooms tab

    :::image type="content" source="media/People-panel-multi-room-2412.png" alt-text="Screenshot of Mesh app showing the people panel expanded in a multi-room event.":::

### Larger events supported

Multi-room events now support up-to 330 people, up from the previous limit of 200.

### Rejoin previous events

It's now possible to rejoin past events! Using the invite link for the Mesh event (found in the calendar invite or via Mesh on the web), anyone can rejoin past events for up-to 5 years after an event completes.

Whether you loved the experience so much that you want to go back to the event or you want a Mesh drop-in space for your team, now you can by rejoining using the Mesh event link.

:::image type="content" source="../media/mesh-event-producer-guide/Join-event-link-calendar-rejoin.png" alt-text="Screenshot of calendar invite for a Mesh event showing the join the event link highlighted.":::

## Version 5.2411.XX

## What's new

#### Multi-room user visualization

* We are improving our cross-room visualization for event hosts, allowing hosts to see attendees who have raised their hand. Additionally, hosts can now see emojis that attendees use in other rooms.

    :::image type="content" source="media/Emoji-reactions-hand-raise-multi-room.png" alt-text="Screenshot of a multi-room event in Mesh showing the emojis for other people in the event.":::

## Version 5.2410.XX

### What's new

#### WebSlate

With the release of the 24.10 Mesh Toolkit, developers now have the ability to add WebSlate Controllables to environments. These WebSlates enable event attendees to interact with a webpage through WebSlates while in a Mesh event and empower event organizers to dynamically change the content that's displayed on the WebSlates in real-time.

An event host could display Microsoft Whiteboard, for example:

:::image type="content" source="media/WebSlate-example-of-whiteboard.png" alt-text="Screenshot of a Mesh event with a WebSlate showing Microsoft Whiteboard with two avatars interacting with it.":::

* **Developer updates:** Same simple workflow for adding Webslates, with minor additional configurations to add Controllable capabilities.

* **Event organizer experience:** Toggle URLs, visibility (on/off), and optionally Prevent suspension (to keep WebSlates always on). Via the Control Panel, changing the URL at runtime updates WebSlates for all users in the event, instantly (global refresh).

* **End user experience:** Upon cursor/controller hover, a menu bar with a built-in refresh button and a tooltip briefly explaining single-user nature of webslates has been added (some webapps may offer shared experiences). This provides a way to return to the URL set by organizers (in the case the user navigates away) and can be used incase webapps have issues during experiences.

### Resolved issues

* Fixed issue executing ActionGroups for Streamed and Embedded Video Controllables with no backplate. (19130)

* Added a volume setting for controlling UI audio. (18650)

## Version 5.2409.XX

### What's new

#### Avatar Reactions

* Ready to dance in Mesh? Get groovy with Avatar Reactions!

    We are excited to announce the release of Avatar Reactions for Mesh immersive experiences! In addition to the standard emoji-based reactions, you can now react with a wider variety of Avatar reactions, making avatar interactions more dynamic, personal, and fun!

    **Key Features:**

    *Expressive Animations:* Avatars can now perform a wider variety of reactions, including dancing, celebrating, and more.

    *Real-Time Reactions:* Reactions are performed in real-time, enhancing the liveliness of virtual meetings and interactions.

    :::image type="content" source="media/Basic-avatar-emotes-standalone.png" alt-text="Screenshot of basic avatar emotes in the Mesh application.":::

    In addition to the standard Avatar reactions, you can find a lot of other reactions sorted into seven categories, including a category for ASL signs.

    :::image type="content" source="media/Catalog-avatar-reactions-emotes-standalone.png" alt-text="Screenshot of avatar reactions catalog in standalone application for Mesh.":::

#### Personal boundary

* Avatars now have a Personal Boundary that prevents other avatars from walking, standing, and teleporting too close to your avatar.

* If you're in the middle of a crowd, you can now also teleport through other avatars to move away from the crowd.

### Resolved issues

#### Reliability improvements

- Improved the ability to join an event when experiencing poor network conditions. (56032)

## Version 5.2408.XX

### What's new

#### Multi-room events

> [!IMPORTANT]
> We are currently rolling out an update to transition multi room events in the Mesh app on PC and Quest to use the same backend infrastructure as Teams for spatial audio. During the rollout, you may find that the additional endpoint and firewall requirements for multi-room may not be required. This rollout should complete by the end of July, 2024.
>
> For more information, please see the admin portal message center post at [https://portal.office.com/adminportal/home?ref=MessageCenter/:/messages/MC807460](https://portal.office.com/adminportal/home?ref=MessageCenter/:/messages/MC807460) or read our documentation for the Mesh [Endpoints and firewall configuration](../Setup/Content/preparing-your-organization.md#endpoints-and-firewall-configuration).

* We now support up to five broadcasters in multi-room events, up from the previous limit of three. With this change, more people can engage across rooms, including hosts that broadcast themselves or attendees who raise their hand.

    For more info, see [how to Broadcast when producing an event](../events-guide/produce-event.md#megaphone-or-broadcast-in-multi-room-events).

* Event hosts can call on attendees from the Host panel when attendees raise their hand to directly to start broadcasting them.

#### Event customization

* Text object is now available when customizing your event. Add text like any other object (Screenshare, Image, Video), move it around the environment, then edit its properties like text style, or size.

    :::image type="content" source="media/Customization-editor-text.png" alt-text="Screenshot of customization session in the Mesh app showing the Text  object.":::

#### Error messaging

* Improved error messaging when a user joins an environment that is not compatible with their application version. In most cases, this is specific to when experimental features are in use.

* Added a **Give feedback** button to error messages that may be hard to diagnose or don't have adequate resolution steps provided.

* Improved error messaging should better inform the user as to why the error occurred.

#### Resolved issues

* Fixed issues that can prevent people from joining an event. (17412, 18048)

* Fixed issue with error message being dismissible when joining events through a link. (18081)

* Fixes to host panel and host user experience. (16512, 16397, 16874)

* The loading background should now display when joining an event directly from Mesh on the web.
(17420)


## Version 5.2407.XX

### What's new

#### Text object added to event customization catalog

* There's now a Text object available in the Catalog when customizing an event. The text object has a cou

#### Endpoint and firewall requirements

* Guidance for endpoints and firewall requirements has been improved to cover the base requirements and additional steps required for cloud scripting and shared content.

    For more info, see the improved [endpoints and firewall configuration guidance](../Setup/Content/preparing-your-organization.md#work-with-your-organizations-security-team).

* With this release, we are starting to transition multi room events in the Mesh app on PC and Quest to use the same backend infrastructure as Teams for spatial audio. This will result in improved audio quality and simplify the set of URL/port requirements needed to run events in Mesh once the rollout is complete later in July.

    For more info, see [Endpoints and firewall configuration](../Setup/Content/preparing-your-organization.md#endpoints-and-firewall-configuration) in the Preparing your organization for Mesh article.

### Resolved product issues

* Fixed a keyboard navigation issue in the avatar customizer.

* Fixed an issue where you might not always see your avatar's reaction after you click on a reaction button.

## Version 5.2406.XX

### What's new

* The Mesh Toolkit contains an updated Mesh 201 tutorial. The tutorial contains two new stations:

    Station 5: Pull data from internal or public sources into your scene. An attendee in the event can click an interactive globe to view live weather data from three different cities.

    Station 6: Set up AI-powered interactions using Azure OpenAI. An attendee can click an "Info" button and ask questions about the best locations for wind farms.

    The documentation for the tutorial has also been updated.

#### Audit logging for Microsoft Mesh

Audit logging help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations. This article summarizes how to query and request audit logs for Microsoft Mesh operations and events. Some operations are Mesh specific, while others are associated with other M365 operations, such as M365: Exchange, SharePoint, Microsoft Entra (Azure AD) operations, Microsoft Teams, etc. With audit logging for Mesh, an admin can gather insights into individual or bulk operations that relate to User Activity or operations which result from interactions with M365 services for Microsoft Mesh. Audit logging can be performed using Exchange Online PowerShell or Microsoft Purview.

For more info, see [Audit logging in Mesh](../Setup/Content/audit-logging-in-mesh.md).

## Resolved product issues

* Various bug fixes and reliability improvements.

* After leaving a meeting and rejoining, shared video playback is synced to all users including the broadcaster.

* Improved performance for video streams should make the overall experience of videos playing in Mesh better.

## Version 5.2405.0

> [!IMPORTANT]
> The Microsoft Mesh application will only have a Public version starting with the 5.2405 build. This means that there will be no Preview version of the Mesh application. The Preview application will be deprecated and will stop being functional. Please uninstall the Preview version of the Microsoft Mesh app.
>
> **Why are we making this change?**
>
> With this change, the Public build will receive updates faster and include newer updates that would've otherwise been flighted in the Preview release before going to the Public release. Each Public build will continue to be released every 3-weeks.
>
> **Mesh Toolkit**
>
> The Mesh Toolkit will not be releasing Preview versions following the 5.2405 version release. The delivery of the Mesh Toolkit package will continue to be released 7 days after the release of the Public Mesh application to ensure the Mesh Toolkit package is compatible with the new version of the Mesh application.
>
> The Immersive spaces in Teams delivery schedule is not affected by this change.
>
> We hope this delivery schedule change will lead to a faster update cadence with newer features reaching the public app sooner than before.

### What's new

* Action groups are now available in the event or template customization flow. This new feature allows an organizer to simultaneously control multiple objects in a event with the the control panel to dynamically change the environment to suit your event needs. Display several images of your team and play a video with the push of a button or show a ScreenShare screen and display supplementary images at the same time.

    :::image type="content" source="../media/mesh-event-producer-guide/Action-groups-gif.gif" alt-text="Gif showing how action groups work while in the Mesh application.":::

    For more detail, see [how to create an Action Group](../events-guide/customize-event.md#create-an-action-group).

* More professional wardrobe styles are coming to the Avatar builder. Customize your avatar to see all the new and updated looks available to freshen up your avatar for your next meeting.
    :::image type="content" source="media/Avatar-wardrobe-update.png" alt-text="Screenshot of Avatar wardrobe updates. ":::

* As an Event host, you can now see your own ScreenShare when sharing your screen in Mesh. Before this update, event hosts were unable to see their own screen on ScreenShare objects, limiting the usability and deteriorating the screen sharing experience for hosts. This update should resolve some of these usability issues and enhance the sharing experience for hosts.

* As an Event host, when using PowerPoint for a presentation that's displayed on a ScreenShare object, you can now use Powerpoint Slideshow to present content. Alike Microsoft Teams, Mesh will now display the presenter view of a PowerPoint presentation.

* Search and filter for content in the Editor and Control panel to search for objects or controls in a Customization session for an environment or template.

    :::image type="content" source="media/Customization-search-objects.png" alt-text="Screenshot of the search functionality available in the Editor tool when customizing an environment in Mesh.":::

* All default environments have their name and description localized into 41 languages.

### Mesh on Quest

* Unexpected startup failure error related to Conditional Access has been replaced with a more verbose and helpful error message:

    Either your Quest device or Mesh app is currently blocked by your organization's AAD Conditional Access policies. Please contact your IT administrator for assistance.

### Resolved product issues

* In the previous release, there was requirement that single room and multi-room events required the same firewall and port configurations. This issue is resolved. Single room events now align to [the standard set by Microsoft Teams](/microsoft-365/enterprise/urls-and-ip-address-ranges), and Multi-room events still require additional ports, as noted in [Endpoints and firewall ports for custom immersive spaces in Mesh](../Setup/Content/preparing-your-organization.md#work-with-your-organizations-security-team).

* In the previous release, there was a slight latency in audio when joining an event. This has been resolved. (29657)

## Version 5.2403.0

### What's new

* [Updated firewall requirements](../Setup/Content/preparing-your-organization.md#work-with-your-organizations-security-team) for single room events in the Microsoft Mesh app.

#### Accessibility features

* High-Contrast modes are available in Settings > Accessibility for low and colorblind users. The **Aqua** and **Desert** color modes make it easier for low vision users to see and interact with content. It can help to distinguish between different colors and shades, making it easier to read text, view images, and navigate through experiences.

    :::image type="content" source="media/Accessibility-high-contrast.png" alt-text="Screenshot of high-contrast accessibility features in Microsoft Mesh.":::

* The Mesh Magnifier lens tool is incredibly useful for accessibility for low vision customers. This feature allows users with low vision to zoom in on objects and text, making it easier for them to see and interact with the virtual environment. The Mesh Magnifier Lens can greatly enhance the user experience for those who may otherwise struggle to navigate and engage with VR content. Additionally, magnifier lens tools can be used by anyone who wants to take a closer look at details within the virtual environment, making them a valuable tool for all users.

    :::image type="content" source="media/Accessibility-magnifier-tool.png" alt-text="Screenshot of Magnifier accessibility tool, available in the Accessibility settings for the Microsoft Mesh application.":::

#### Conditional access on Quest

* If you have Conditional Access policies in place for your organization that my block on Mesh on Quest, the solution is to create a custom conditional access policy in Microsoft Entra Admin Center to exclude Microsoft Mesh Services and Office 365.

### Resolved product issues

The following product issues have been fixed for this release:

* In high-contrast mode, the descriptions for environments will not disappear.

* Fixed environment startup delays (both in Mesh Emulator and the Mesh app) that could be triggered by environments that contain visual scripts with many variable or computed targets for property updates or method invocations while also containing many potential component instances of the corresponding target type. (47009)

* Fixed a latency issue when joining an event that was passed onto the user, especially noticeable in custom environments. (29657)

* The radio in the Lakehouse has a properly functioning button to start/stop playing music.

* Avatar eye saturation is improved to be more accurate to the user-selected color palette.

* Fixed an issue where visual scripts using a computed or variable reference to access `Transform` component instances in large environments could cause a spike in network traffic on environment load.

* Fixed a rare issue where an isolated `TravelPoint` (not parented by a `TravelPointGroup`) in a user environment could lead to an internal error that caused visual scripts to be deactivated.

* The On State Changed event node can now be used in subgraph assets without issue. Previously, attempting to use it in a subgraph asset caused a `GraphPointerException` error to be logged.

## Version 5.2402.0

### What's new

* Presenters can now see their own screenshare when sharing content in Mesh. Previously, screenshared content was only visible to participants other than the presenter, requiring the presenter to navigate out of Mesh to see the content being shared.

## Version 5.2401.0 (February 20, 2024)

### Resolved product issues

The following product issues have been fixed for this release:

* Unexpected startup failure when launching Quest app related to conditional access now provides a more relevant error message: "Either your Quest device or Mesh app is currently blocked by your organization's AAD Conditional Access policies. Please contact your IT administrator for assistance."

    This should provide more clarity when conditional access is blocking usage of the quest application, helping customers better understand why the app failed to load. (38252)

## Version 5.2315.0

### What's new

* The new Microsoft Mesh trial license offering is now publicly available for enterprise customers to access Mesh for 6 months! For more information on how to sign up, see [IT admin-led trials for Microsoft Mesh](/mesh/setup/content/it-admin-led-trials). You can also find additional licensing requirements in [Troubleshooting and FAQ](/mesh/resources/mesh-troubleshooting).

* Controls in the **Environment Editor** and the **Control Panel** are now ordered based on relevance or priority, so it's easier for users to find the controls they need.

* If a user joins an event with a different tenant ID from that of the event organizer, we now show the following error dialog: **Join space from different tenant than the meeting owner is not allowed. Please use a different account to join this space.**

* We have improved ambient indicators as to who is megaphoning, broadcasting, or screen sharing.

    ![A screenshot showing the improved ambient indicators](media/ambient-indicators.png)

### Mesh on the web

Mesh on the web is moving to cloud.microsoft with the [Microsoft 365 apps and services](https://techcommunity.microsoft.com/t5/microsoft-365-blog/introducing-cloud-microsoft-a-unified-domain-for-microsoft-365/ba-p/3804961). Currently, we are providing two links for Mesh on the web to ensure a smooth transition. For the new [cloud.microsoft](https://mesh.cloud.microsoft) link, make sure you have allowed the proper endpoints. See [Preparing your organization](../Setup/Content/preparing-your-organization.md#work-with-your-organizations-security-team) for details.

The Mesh on the web link is:

https://mesh.cloud.microsoft

### Resolved product issues

The following product issues have been fixed for this release:

* On Quest, the user is disconnected from an event if headset is removed. (25764)

* Searching for co-organizers on the Invite page yields no results. (29365)

## Version 5.2314.0

### What's new

#### New UI termonlogy

| UI terms previously used   | New terms  |
|---|---|
| Event template   | Template   |
| Mesh World, World   | Environment collection, collection  |
| Artifact   | Object  |
| Environment Editor | Editor |
| App Menu |  Menu bar |
| Mesh Portal | Mesh on the Web |

#### Avatar customizer

* Users are now prompted to confirm if they're sure they'd like to lose their changes before exiting the avatar customizer.

#### Event production

* New hand raise functionality:

    * Hosts can now see who raised their hand, and then enable **Broadcast** and **Megaphone** for them. **Broadcast** allows the user to be visible in multiple rooms,  and **Megaphone** allows them to be heard.

    * Users can now raise their hand and wait to be called on by the host(s) in an event. Once called, their avatar will be **Broadcasted** (in multiple-room events) and **Megaphone** will be turned on.

* Updated the dialog box for when an attendee is invited to accept broadcast. You can either choose to **Decline** or **Confirm** to start broadcasting. (24459)

    ![A screenshot of the go-on the air dialog](media/go-on-the-air-dialog.png)

* New screen share UI:

    * Before starting a screen share, the dotted line indicates you can share to that screen.

        ![A screenshot of the screen sharing UI](media/before-screen-share.png)

    * Once screen sharing is started, you see a **You are screen sharing** toast notification, and the **Stop sharring** option. The solid line indicates you're currently sharing a screen.

        ![A screenshot of the screen sharing UI during a screen share](media/after-screen-share.png)

* New **Control panel** dialog where the **Controls** list is now on a separate tab:

    ![A screenshot of the **Control panel** dialog showing the **Controls** tab](media/controls-tab.png)
  
* Save customizations in a customization session using the **Save** buttton.

    :::image type="content" source="../media/mesh-event-producer-guide/Customize-event-object-save-changes.png" alt-text="Screenshot of save dialogue and button in a customization session.":::
        
#### New controls for interactive objects

* Throwable (for example: [the bean bag toss](https://support.microsoft.com/en-us/office/use-in-meeting-controls-for-immersive-spaces-in-microsoft-teams-ccf689d0-b47e-4e11-9eff-2ca0ce87f422#bkmk_social_games)):

    * Aim and left mouse click to throw

    * Press **Space bar** to drop

* Activatable (for example: [the marshmallow stick in the Lakehouse environment](https://support.microsoft.com/en-us/office/use-in-meeting-controls-for-immersive-spaces-in-microsoft-teams-ccf689d0-b47e-4e11-9eff-2ca0ce87f422#bkmk_social_games)):

    * Click to use

    * Press **Space bar** to drop

* [Equippable objects](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects) without any special interactions:

    * Press **Space bar** to drop


### Resolved product issues

* On Quest, when running multiple video players will cause the videos to flicker intensely. (24490)

* On Quest: the Mesh UI no longer locks with the user's head view. As you turn your head, the Mesh UI will now remain stationary. (13061)

* While a seating layout change is in progress, the seats are no longer clickable. (27509)

* You will no longer feel a slight bump in your position after teleporting to an inclined surface. (24915)

* The settings dialogs now show the current selected state for many settings. (17308)

* When trying to throw an object by clicking on the object, the cursor no longer shows. (25542)

* On Quest devices: to pick up an [equippable object](/mesh/develop/enhance-your-environment/avatar-and-object-interactions/interactables#equippable-objects), you can simply bring your hand close to the object and click the Grip button.  

    Previously, you need to point the controller ray at the object and click the **Grip** button. This feels very unnatural for interaction with objects that are near.  When you're very close to an object, it's hard to point your controller ray at it to interact. (24187)

* Fixed the issue: On PC and Quest, when attempting to delete any Objects in the Environment Editor will crash Mesh while running. (28903)

#### Events

* In the case of a failure to connect to Mesh services when joining an event, we now show an error dialog asking users to contact their IT admin. Consult the Mesh admin documentation, and in particular the details about [configuring firewalls](/mesh/setup/content/preparing-your-organization#work-with-your-organizations-security-team), to ensure traffic to and from Mesh services are allowed. (27527) 

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
