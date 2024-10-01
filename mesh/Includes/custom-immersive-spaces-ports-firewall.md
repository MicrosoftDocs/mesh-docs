---
title: Ports and firewall requirements for Custom immersive spaces
description: Detail on what the firewall and ports requirements are for custom immersive spaces accessed through the Microsoft Mesh application.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 8/15/2024
ms.topic: overview
keywords: Microsoft Mesh, Immersive spaces, setup, admin, M365, ports and firewall, requirements
---

### Endpoints and firewall requirements for immersive spaces in Mesh

This section outlines the specific endpoints and firewall requirements for **Immersive experiences in Mesh**, inclusive of the Mesh application and its features that your organization can leverage to create dynamic corporate events.

In general, the standard set of Microsoft 365 requirements outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true) applies to all Mesh experiences with some extra steps to enable additional Mesh features like larger multi-room events, Cloud Scripting, and embedded content (WebSlate, Video/Image objects).

#### Step 1: Configure according to Microsoft M365 requirements

Configure your enterprise firewall settings to align with the standard set of Microsoft 365 requirements for **Microsoft Teams**, and **Microsoft 365 Common** outlined in [Microsoft M365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Mesh also requires the IP addresses and port ranges detailed in [Firewall configuration for Azure Communication Services](https://learn.microsoft.com/azure/communication-services/concepts/voice-video-calling/network-requirements#firewall-configuration) for media capabilities such as audio, video, and screenshare.

Without access to these, Mesh won't work properly for users in your organization.

#### Step 2: Enable attendee access to scripts and content over time

##### Cloud scripting

If you or your development team plans to use [Cloud scripting](../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts.md) to display dynamic and rich data in Mesh environments by interfacing with Azure, you'll need to allow traffic to the Azure resources that your enterprise hosts for cloud scripting.

You can do this as new environments using cloud scripting are published by allowing traffic on TCP port 443 (HTTPS) to that environment's hosted app: `<app>.azurewebsites.net`.

##### Embedded content (WebSlate, video/image)

The Mesh app enables dynamic content experiences leveraging the web and Azure. This empowers event organizers to place Video and Image Objects with a no-code event customization experience, and developers to add web interactivity with WebSlates.

Dynamically loaded, embedded content have unique requirements for immersive experiences due to the unique permissions required to access resources while within Mesh experiences.

> [!IMPORTANT]
> There are two considerations to ensure that embedded content is accessible in immersive spaces in Mesh:
>
> - **If stored in SharePoint, the content will follow M365 requirements**: Organizers must ensure attendees have access to URL. Attendees must have permissions to the specified file or Share link.
> - **If not in SharePoint, the content will follow firewall rules**: Organizers must ensure the URL domain is in the firewall/allowlist for TCP Port 443 (HTTPS).  Attendee client devices will download from this URL directly.

|Content type  |How it works |
|---------|---------|
|**WebSlate** <p><p> Embed interactive web content in Mesh environments or templates.     | **WebSlates** display web content using a client WebView on each attendee's device.  If their target URLs are blocked for an attendee in a browser, then they will also be blocked in Mesh. |
| **Video & Image Objects** Embed videos and images into Mesh environments. | The Mesh app enables organizers to customize experiences for their Mesh Event by referencing image and video URLs. <p><p>If these URLs are blocked for an attendee in a browser, then they will also be blocked in Mesh. |

> [!TIP]
> In addition to firewall allow lists, WebSlates require that environment developers add the URL's domain to the Unity WebSlate component's allow list as well.
> 
> For more information about WebSlate security and allowlisting, see [WebSlate performance and security](../develop/enhance-your-environment/web-content/webslate-performance-and-security.md).

