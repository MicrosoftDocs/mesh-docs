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

### Endpoints and firewall requirements for immersive spaces in Mesh

This section outlines the specific requirements for **Immersive experiences in Mesh**, inclusive of the Mesh application and its unique features that your organization can leverage to create dynamic corporate events.

In general, the standard set of Microsoft 365 requirements outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true) applies to all Mesh experiences with some extra steps to enable additional Mesh features like larger multi-room events and Cloud Scripting.

#### Step 1: Configure according to Microsoft M365 requirements

First, configure your enterprise firewall settings to align with the standard set of Microsoft 365 requirements outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

#### Step 2: Configure for additional Mesh features

##### Larger events (Multi-room)

> [!NOTE]
> Currently, there are extra firewall ports required when events in the Mesh app are held with more than 16 people. We appreciate your patience as we move to align with the standards outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

When organizing multi-room events, Mesh also requires that outgoing traffic be allowed to IP addresses in the "AzureCloud" service tag over the following protocols and ports:

- TCP: 443, 80
- TCP & UDP: 30,000-30,499
- UDP: 3478-3481

If you need to resolve a service tag to a list of IP ranges, you can periodically use the [service tag API][service-tag-api] or [download a snapshot][service-tag-download].

For more information about service tags, see the [Azure service tags overview][service-tag].

To learn more about single room vs. multi room events, see [Create an event in Mesh](/mesh/events-guide/create-event-mesh-portal).

#### Cloud scripting

If you or your development team plans to use [Cloud scripting](../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts.md) to display dynamic and rich data in Mesh environments by interfacing with Azure, you'll need to allow traffic to the Azure resources that your enterprise hosts for cloud scripting.

You can do this as new environments using cloud scripting are published by allowing traffic on TCP port 443 (HTTPS) to that environment's hosted app: `<app>.azurewebsites.net`.

#### Embedded content (WebSlate, video/image)

The Mesh app enables dynamic content experiences leveraging the web and Azure. This empowers event organizers to place Video and Image Objects with a no-code event customization experience, and developers to add web interactivity with WebSlates.

Dynamically loaded, embedded content have unique requirements for immersive experiences due to the unique permissions required to access resources while within Mesh experiences.

> [!IMPORTANT]
> There are two considerations to ensure that embedded content is accessible in immersive spaces in Mesh:
>
> - **If stored in SharePoint, the content will follow M365 requirements**: Organizers must ensure attendees have access to URL. Attendees must have permissions to the specified file or Share link.
> - **If not in SharePoint, the content will follow firewall rules**: Organizers must ensure the URL domain is in the firewall/allowlist for TCP Port 443 (HTTPS).  Attendee client devices will download from this URL directly.

**The embedded content types are:**

|Content type  |How it works |
|---------|---------|
|**WebSlate** <p><p> Embed interactive web content in Mesh environments.     | **WebSlates** display web content using a client WebView on each attendee's device.  If their target URLs are blocked for an attendee in a browser, then they will also be blocked in Mesh. |
| **Video & Image Objects** Embed videos and images into Mesh environments. | The Mesh app Editor enables organizers to customize experiences for their Mesh Event. <p><p>To ensure the best experience, direct links to videos and images hosted via SharePoint or HTTPS URLs.         |

> [!TIP]
> In addition to firewall allow lists, WebSlates require that environment developers add the URL's domain to the Unity WebSlate component's allow list as well.
> 
> For more information about WebSlate security and allowlisting, see how to [Display and interact with Web content in Microsoft Mesh | Microsoft Learn](../develop/enhance-your-environment/webcontent.md).
