---
title: Bandwidth requirements for Microsoft Mesh
description: Bandwidth requirements and limitations that are requied for users to acecss Microsoft Mesh on their networks.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 10/03/2024
ms.topic: overview
keywords: Microsoft Mesh, bandwidth, network, setup, admin, M365
---

## Bandwidth requirements for Mesh events

The following network bandwidth requirements are designed to help users in your organization have the best possible experience with Mesh immersive experiences.

While we are constantly working on improving how Mesh works even in poor network conditions, you may want to further optimize your network if users in your organization report poor audio quality, audio cutting out, or delayed or jerky avatar movement.

Mesh immersive experiences build on top of [Microsoft Teams network bandwidth requirements](/microsoftteams/prepare-network#bandwidth-requirements) for capabilities such as screenshare, with additional bandwidth needed for immersive capabilities such as avatar movement and spatial audio, and to be able to visualize users in other rooms.

### Bandwidth requirements for all events

| **Modality**                                                                          | **Minimum (kbps)** | **Recommended (kbps)** | **Best performance (kbps)** |
|---------------------------------------------------------------------------------------|--------------------|------------------------|-----------------------------|
| Avatar movement  & audio                                                              | 30/370             | 80/700                 | 100/850                     |
| Screenshare ([Same as Teams](/microsoftteams/prepare-network#bandwidth-requirements)) | 250/250            | 2,500/2,500            | 4,000/4,000                 |

### Additional bandwidth requirements for multi-room events

| **Modality**                                                                                         | **Minimum (kbps)** | **Recommended (kbps)** | **Best performance (kbps)** |
|------------------------------------------------------------------------------------------------------|--------------------|------------------------|-----------------------------|
| [Broadcast presenters](../events-guide/produce-event.md#megaphone-or-broadcast-in-multi-room-events) | 30/110             | 80/160                 | 100/180                     |
| [Visualizing users in other rooms](../Resources/mesh-release-notes.md#multi-room-user-visualization) | 65/65              | -                      | -                           |

As an example, a multi-room event such as a team all hands with screenshare, broadcasted presenters, and visualization for users in other rooms will require a minimum of 375 kbps downstream, and 795 kbps upstream, and a maximum of 4,265 kbps downstream and 5,095 kbps upstream.

Note: these metrics are calculated based on maximum room, presenter, and event capacities as documented in [Mesh limitations and specifications](../Resources/limitations-specifications-mesh.md), to help you best prepare your organization's network for Mesh. Smaller event sizes will have lower network requirements, for example due to there being fewer avatars, speakers, and rooms.

Custom content such as videos added [through Mesh event customization](../events-guide/customize-event.md) may require further bandwidth. For events with custom content, we recommend testing your event beforehand with a representative network connection to make sure that content loads correctly and experience performance is adequate.
