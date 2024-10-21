---
title: Features in development
description: This page details a host of upcoming features that customers may see if they are in the Mesh Technology Adoption Program.
ms.service: mesh
author: typride    
ms.author: tmilligan
ms.date: 08/29/2024
ms.topic: release-notes
keywords: Microsoft Mesh, Mesh toolkit, Mesh Developer, Mesh Technology Adoption Program, Mesh TAP, Upcoming Features
---

# Features in development for Microsoft Mesh

In this article, you can find details about upcoming features, spanning all Mesh experiences, including Immersive experiences in Mesh, Immersive experiences in Teams, Avatars, and Mesh on the web.

> [!IMPORTANT]
> Features in development roll out through a sphere framework, allowing organizations who have opted in to the [Mesh Technology Adoption Program (Mesh TAP)](../develop/mesh-tap-participants.md) to test and provide feedback on features before they reach general availability.
>
> As these features roll out, some customers may see features before other customers.

> [!NOTE]
> This article reflects our current expectations about Mesh capabilities in an upcoming release. Dates and individual features might change. This article doesn't describe all features in development. It was last updated on the date shown under the title.

## October 2024

Theses are features that we are rolling out as of October 2024.

### Guest access

We are rolling out guest access for Mesh in the Mesh application for PC! Event organizers will soon be able to invite guest users outside their organization, providing an opportunity for broader collaboration and networking in Mesh events. Guests can sign in to the Mesh app to join events, participate in discussions, and experience the same interactive features as internal users, all while maintaining secure access control.

**Guests** - people who are logged in from outside your organization who access shared resources by signing in using a guest account in your directory. Guests appear with "(Guest)" appended to their name in meetings. A guest user is invited as guest to the organizer tenant. They must have a guest account created for them with Microsoft Entra ID, which provides the same compliance and auditing protection as other Microsoft 365 users. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Mesh events.

A few important notes to consider are:

* Guest users' creation [follows the existing process for tenant guest user creation using Microsoft Entra ID](/entra/external-id/b2b-quickstart-add-guest-users-portal).

* As of now, guest users also require a [Teams Premium license](/microsoftteams/teams-add-on-licensing/licensing-enhance-teams) and [Mesh license](../Setup/Content/it-admin-led-trials.md) similar to all other Mesh event attendees.

* Guest access is not supported on the Mesh app for Quest.

### Event tools for hosts and attendees

* Reaction visualization for attendees is coming to multi-room Mesh events. Attendees who are raising their hand or actively reacting with emojis are now visualized across all rooms as spatial 3D bubbles. These simple visualizations persist ephemerally and dynamically display information about others who are in the event based on proximity and location. They do not support direct interaction, but rather aim to create a sense of the audience-as-a-whole and communicate the general sentiment of participants in multi-room events.

* We are also adding a new interaction capability for both attendees and hosts. As an attendee, selecting or clicking on an avatar will now raise a menu with the option to open someone's profile card or view their current mic-state. As a host, selecting or clicking an attendee avatar will raise a menu with options to megaphone or broadcast (dependent on the room size of the event: single or multi-room), mute the attendee, or open their profile card.

* Room Hopping for event hosts is coming to multi-room Mesh events. Hosts will be able to open the People Panel, navigate to the Rooms tab, and select a room to travel to. Movement between rooms will fade out the people and content from the current room, while loading the people and content in the new room. Hosts can freely move between any open rooms and a maximum of two hosts will be able to bypass the capacity limit for currently full rooms. (Note: Certain scripting content performance may differ after Room Hopping. We recommend pre-event testing to ensure experience predictability.)

## September 2024

Theses are features that we are rolling out as of September 2024.

* In the Microsoft Mesh application, the mouth movement and lip synchronization for avatars will soon more accurately reflect words spoken by users.

* We are rolling out the ability to room hop as a host, empowering hosts to connect with attendees in each room.
