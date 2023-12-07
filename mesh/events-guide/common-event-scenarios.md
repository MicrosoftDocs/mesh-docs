---
title: Common scenarios for event hosts
description: How to run or manage common event scenarios in Microsoft Mesh.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 12/01/2023
ms.topic: Overview
keywords: Microsoft Mesh, M365, events, hosting, event producer, event organizer, Q&A, scenarios
---

# Common scenarios for event hosts

There are a host of scenarios that Mesh can be used for, including Q&A (Question and Answer), screen sharing with a large audience, and much more.

In this article, we'll cover how to run a Q&A session; involve the audience and make attendees audible to all participants even if they aren't a host.

## Multi-room vs single room events

Single room events can host up-to 16 people. For larger events, participants are grouped into 16 person rooms to provide the optimal experience for all users.

As a host, your host tools will be slightly different in a multi-room scenario.

### Host tools in a single room event

In a single room event, you have access to the **Mute all**, **Hand Raise**, **Megaphone**, and **Screenshare** controls.

:::image type="content" source="../media/common-event-scenarios/single-room-host-tools.png" alt-text="Screenshot of the host tools in a single room event.":::

### Host tools in a multi-room event

In a multi-room event, you have access to the **Mute all**, **Hand Raise**, **Megaphone**, **Broadcast**, and **Screenshare** controls.

:::image type="content" source="../media/common-event-scenarios/multi-room-host-tools.png" alt-text="Screenshot of the host tools in a single room event.":::

Broadcast is the notable difference here, which shows your avatar and makes your voice audible to all participants in all rooms.

> [!TIP]
> Use **Broadcast** as a host while in a multi-room event otherwise participants won't be able to see or hear you.

## Using hand raise for Q&A

As a host, you may want participants to be able to ask their questions or say comments to the whole event.

### Enable Hand Raise for all participants

To allow participants to raise their hand, you must **enable Hand Raise** bold **Host Panel**.

1. Open the Host Panel.

    :::image type="content" source="../media/mesh-event-producer-guide/host-panel-menu-bar-2314.png" alt-text="Host panel button to see participant list and tools":::

1. Select the Hand Raise button in the host panel to enable it.

    :::image type="content" source="../media/common-event-scenarios\producer-tools-hand-raise-2314.png" alt-text="Mute all button in host panel":::

### Call on people in single room events

In single room events, as a host you'll see who has their hand raised in the host panel and in the event. Use the Megaphone button next to their name to enable **Megaphone** for attendees so all participants can hear them.

:::image type="content" source="../media/common-event-scenarios/hand-raise-call-on-attendees.png" alt-text="Screenshot of Mesh showing hand raise icon next to attendee names that indicates they have hand raised.":::

### Call on people in multi-room events

In multi-room scenarios, attendees will only be able to talk to other people in their room. As a host, you will not see or hear the attendees until you broadcast them.

To call on them, look in the host panel and select the **Broadcast** button, as shown below.

:::image type="content" source="../media/common-event-scenarios/Multi-room-broadcast-hand-raise.png" alt-text="Screenshot of Mesh multi-room scenario, broadcast button highlighted next to attendee name.":::

Once you select broadcast, they will receive a notification request for them to be broadcast. Once they accept, they will then be broadcast to the whole event and all participants.

#### Visual indicators for attendee megaphone or broadcast

When an attendee is megaphoned or broadcast, there are a few visual indicators and notifications that you will see in the host panel, and all participants will see in the Mesh window.

In the host panel, their name will be highlighted and show a Megaphone or broadcast logo next to their name.

In the Mesh window there is a notification at the bottom of the screen, as shown below:

:::image type="content" source="../media/common-event-scenarios/Megaphone-broadcast-Visual-indicator.png" alt-text="Screenshot of Mesh showing visual indicators that attendees are megaphoned or broadcast.":::

### Controls while attendee is Megaphoned or Broadcasted

As a host, you'll be able to disable attendee Megaphone or Megaphone or broadcast at any time

Simply select the **Megaphone** or **Broadcast** button, or select the **Mute microphone** button next to their name to disable their communication abilities.

#### In a single room event

Use the **Megaphone** or **Mute Microphone** to stop their megaphone or mute their microphone.

:::image type="content" source="../media/common-event-scenarios/Controls-during-attendee-answer-single-room.png" alt-text="Screenshot of Mesh showing controls that host has to limit attendee answer communication.":::

#### In a multi-room event

Use the **Broadcast** or **Mute Microphone** to stop their broadcast or mute their microphone.

:::image type="content" source="../media/common-event-scenarios/Controls-during-attendee-answer.png" alt-text="Screenshot of Mesh showing controls that a host has to disable attendee communication.":::

## Next steps

   > [!div class="nextstepaction"]
   > [Produce your event](produce-event.md)