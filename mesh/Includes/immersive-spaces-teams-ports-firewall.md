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

Configure your enterprise firewall settings to align with the standard set of Microsoft 365 requirements outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

> [!NOTE]
> Currently, there are extra firewall ports required when in an immersive spaces are held with more than 16 people. We are currently working to align with the standards outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true). We appreciate your patience as we make this infrastructure change.

#### Immersive spaces in Teams

1. Aligned to standard set of Microsoft 365 requirements outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

1. In addition to the endpoints listed above, Mesh Immersive Spaces in Teams currently requires that outgoing traffic also be allowed to IP addresses in the "AzureCloud" service tag over the following protocols and ports:

    * TCP: 443, 80
    * TCP & UDP: 30,000-30,499
    * UDP: 3478-3481

If you need to resolve a service tag to a list of IP ranges, you can periodically use the [service tag API][service-tag-api] or [download a snapshot][service-tag-download].

For more information about service tags, see the [Azure service tags overview][service-tag].

#### Avatars in Teams

Aligned to standard set of Microsoft 365 requirements outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).
