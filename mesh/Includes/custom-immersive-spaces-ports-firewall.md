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

### Endpoints and firewall ports for custom immersive spaces in Mesh (Mesh app)

|   | Single room event in the Mesh app | Multi room event in the Mesh app  | 
|---|---|---|
| **Required endpoints** | Aligned to standard set of Microsoft Teams requirements outlined in [Microsoft 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams&preserve-view=true). | To ensure Mesh works properly, allow the following endpoints. All endpoints need to allow traffic on TCP ports 443: <p><p> \*.officeapps.live.com <br> \*.microsoft.com <br> \*.office365.com <br> \*.office.com <br> \*.office.net <br> \*.cloud.microsoft <p><p> |
| **Firewall ports** | Aligned to standard set of Microsoft Teams requirements outlined in [Microsoft 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams&preserve-view=true). | In addition to the endpoints listed above, Mesh also requires that outgoing traffic be allowed to IP addresses in the "AzureCloud" service tag over the following protocols and ports: <p><p> TCP ports 80 <br> TCP & UDP ports 30,000-30,499 <br> UDP ports 3478-3481 <p><p> TCP port 443  <p><p>If you need to resolve a service tag to a list of IP ranges, you can periodically use the [service tag API][service-tag-api] or [download a snapshot][service-tag-download]. <p><p> For more information about service tags, see the [Azure service tags overview][service-tag]. |

To learn more about single room vs. multi room events, see [Create an event in Mesh](/mesh/events-guide/create-event-mesh-portal).

### Allowlisting requirements for objects and cloud scripting in custom immersive experiences

The Mesh app enables dynamic content experiences leveraging the web and Azure, empowering no-code users to place content such as Video and Image Objects and for developers to add interactivity with Mesh Scripting via Azure.

Dynamically loaded content is a unique requirement for immersive experiences because users require permission to access resources while within Mesh experiences.

#### Scenarios with unique allowlisting requirements

There are a few unique permissions and allowlisting considerations for the following objects and scenarios:

|Scenario  |Unique permissions or allowlisting requirements |
|---------|---------|
|[Video and image objects](../events-guide/customize-event.md#types-of-customizations) added to events or templates within a customization session.    |  Existing Entra ID rules apply: If a link is accessible to them, it will be visible. If permissions limit access to the content, users will not be able to see the content.       |
|[Interactive web content](../develop/enhance-your-environment/webcontent.md), such as WebSlates, added in Unity with the Mesh Toolkit.    |   WebSlates require allowing direct traffic to the sites they render. [See Security Restrictions & Domain allowlist here](../develop/enhance-your-environment/webcontent.md)  |
|[Cloud scripting](../develop/script-your-scene-logic/mesh-scripting-overview.md#benefits-of-cloud-scripting) to expand your environment by calling any .NET API and connecting to any of your Azure resources.    |  (Optional) If your event uses [Cloud scripting](../develop/script-your-scene-logic/mesh-scripting-overview.md), you'll need to allow traffic to the Azure resources that your enterprise hosts for cloud scripting. <p><p>You can do this by allowing traffic on TCP port 443 (HTTPS) to your hosted app: <p><p> `<app>.azurewebsites.net`.       |
