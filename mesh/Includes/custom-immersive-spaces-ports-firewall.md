---
title: Ports and firewall requirements for Custom immersive spaces
description: Detail on what the firewall and ports requirements are for custom immersive spaces accessed through the Microsoft Mesh application.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 06/12/2024
ms.topic: overview
keywords: Microsoft Mesh, Immersive spaces, setup, admin, M365, ports and firewall, requirements
---

### Endpoints and firewall ports for immersive experiences in Mesh

Aligned to standard set of Microsoft 365 requirements outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

#### Additional requirements for optional features

##### Larger events (17+ people, Multi-room)

> [!NOTE]
> Currently, there are extra firewall ports required when events in the Mesh app are held with 17 or more people. We appreciate your patience as we move to align with the standards outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

In addition to the endpoints listed above, Mesh also requires that outgoing traffic be allowed to IP addresses in the "AzureCloud" service tag over the following protocols and ports:

- TCP: 443, 80
- TCP & UDP: 30,000-30,499
- UDP: 3478-3481

If you need to resolve a service tag to a list of IP ranges, you can periodically use the [Service Tag API](azure/virtual-network/service-tags-overview#use-the-service-tag-discovery-api&preserve-view=true) or [download a snapshot](azure/virtual-network/service-tags-overview#discover-service-tags-by-using-downloadable-json-files&preserve-view=true).

For more information about service tags, see the [Azure service tags overview](/azure/virtual-network/service-tags-overview).

To learn more about single room vs. multi room events, see [Create an event in Mesh](/mesh/events-guide/create-event-mesh-portal).

#### Cloud scripting

If you or your development team plans to use [Cloud scripting](../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts.md) to display dynamic and rich data in Mesh environments by interfacing with Azure, you'll need to allow traffic to the Azure resources that your enterprise hosts for cloud scripting.

You can do this by allowing traffic on TCP port 443 (HTTPS) to your hosted app: `<app>.azurewebsites.net`.

#### Embedded content (WebSlate, video/image)

The Mesh app enables dynamic content experiences leveraging the web and Azure. This empowers event organizers to place Video and Image Objects with a no-code event customization experience, and developers to add web interactivity with WebSlates.

Dynamically loaded, embedded content have unique requirements for immersive experiences due to the unique permissions required to access resources while within Mesh experiences.

The embedded content types are:
|Content type  |How it works |
|---------|---------|
|**WebSlate** <p><p> Embed interactive web content in Mesh environments.     | **WebSlates** use the WebView system, which respects all corporate network restrictions implemented by IT Admins. If content is blocked to load in a browser, then it will also be blocked in WebSlate. |
| **Video & Image Objects** Embed videos and images into Mesh environments. | The Mesh app Editor enables organizers to customize experiences for their Mesh Event. <p><p>To ensure the best experience, direct links to videos and images hosted via SharePoint or HTTPS URLs.         |

There are two considerations to ensure that embedded content is accessible in immersive spaces in Mesh:

1. **If stored in SharePoint, the content will follow M365 requirements**: Organizers must ensure attendees have access to URL. Attendees must have permissions to the specified file or Share link.

1. **If not in SharePoint, follow the endpoints and firewall rules**: Organizers must ensure the domain is in the firewall/allowlist for TCP Port 443 (HTTPS). Make sure the URL is in firewall/port allowlist.  

> [!TIP]
> Webslates require that the developers add a URL to the Allowlist in Unity. Those URLs must also be added to the firewall/allowlist for TCP Port 443 (HTTPS).
> 
> For more information about WebSlate security and allowlisting, see how to [Display and interact with Web content in Microsoft Mesh | Microsoft Learn](../develop/enhance-your-environment/webcontent.md).

