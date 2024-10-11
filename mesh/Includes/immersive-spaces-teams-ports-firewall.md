---
title: Ports and firewall requirements for immersive spaces in Teams
description: Detail on what the firewall and ports requirements are for immersive spaces in Teams.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 06/12/2024
ms.topic: overview
keywords: Microsoft Mesh, Immersive spaces, Immersive spaces in Teams, setup, admin, M365, ports and firewall, requirements
---

### Endpoints and firewall ports for Mesh experiences in Teams

This section outlines the specific endpoints and firewall requirements for the Mesh app in Teams and the Avatars app, which allow users to join an immersive space (3D) while in a Teams meeting and use avatars in meetings.

#### Avatars in Teams

Configure your enterprise firewall settings to align with the standard set of Microsoft 365 requirements outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

#### Immersive spaces in Teams

Configure your enterprise firewall settings to align with the standard set of Microsoft 365 requirements for **Microsoft Teams**, and **Microsoft 365 Common** outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

As part of this, ensure that you have configured your firewall to enable traffic to `*.cloud.microsoft.com`, `*.office.com`, and `*.microsoft.com` over `TCP 443`, `80`.

Mesh also requires the IP addresses and port ranges detailed in [Firewall configuration for Azure Communication Services](/azure/communication-services/concepts/voice-video-calling/network-requirements#firewall-configuration) for media capabilities such as audio, video, and screenshare.

Without access to these, Mesh won't work properly for users in your organization.
