---
title: Bandwidth requirements for Immersive spaces in Teams
description: Bandwidth requirements and limitations that are requied for users to acecss Microsoft Mesh on their networks.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 10/03/2024
ms.topic: overview
keywords: Microsoft Mesh, bandwidth, network, setup, admin, M365
---

## Bandwidth requirements for Immersive spaces in Teams

The following network bandwidth requirements are designed to help users in your organization have the best possible experience with Mesh immersive experiences.

While we are constantly working on improving how Mesh works even in poor network conditions, you may want to further optimize your network if users in your organization report poor audio quality, audio cutting out, or delayed or jerky avatar movement.

Mesh immersive experiences build on top of [Microsoft Teams network bandwidth requirements](/microsoftteams/prepare-network#bandwidth-requirements) for capabilities such as video and screenshare, with additional bandwidth needed for immersive capabilities such as avatar movement and spatial audio.

### Immersive participants

| **Modality**             | **Minimum (kbps)** | **Recommended (kbps)** | **Best performance (kbps)** |
|--------------------------|--------------------|------------------------|-----------------------------|
| Avatar movement  & audio | 30/370             | 80/700                 | 100/850                     |

### Non-immersive participants

| **Modality**                     | **Minimum (kbps)** | **Recommended (kbps)** | **Best performance (kbps)** |
|----------------------------------|--------------------|------------------------|-----------------------------|
| Audio ([Same as Teams](/microsoftteams/prepare-network#bandwidth-requirements))        | 30/370             | 80/700                 | 100/850                     |
| Video ([Same as Teams](/microsoftteams/prepare-network#bandwidth-requirements)) | 150/200              | 2,500/4,000                      | 4,000/4,000                           |
| Screenshare ([Same as Teams](/microsoftteams/prepare-network#bandwidth-requirements))              | 250/250            | 2,500/2,500            | 4,000/4,000                 |

As an example, a meeting with some participants in immersive, some participants not in immersive with their video on, and screenshare will require a minimum of 440 kbps downstream, and 830 kbps upstream, and a maximum of 8,176 kbps downstream and 8,926 kbps upstream.

Note: these metrics are calculated based on immersive spaces being at its 16-person capacity, to help you best prepare your organization's network for Mesh. Smaller event sizes will have lower network requirements, for example due to there being fewer avatars and speakers.
