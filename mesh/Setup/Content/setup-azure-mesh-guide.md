---
title: Set up Azure for Mesh
description: Set up Azure to manage Mesh worlds, events, environments, and deploy Mesh to your organization.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: Tutorial
keywords: Microsoft Mesh, Azure, admin, documentation, features
---

# Set up Azure for Mesh

Microsoft Mesh offers a host of powerful features that enhance communication and collaboration in remote and hybrid workplaces. Corporate teams can interact in 3D with their custom expressive Avatars.

All this, with the power of Azure for Resource management and Identity and Access Management (IAM) policies to suit most needs that are already met by Microsoft Teams, with the added power of three-dimensional environments. This document covers the security, administration, and deployment of Mesh within your business.

This article covers the security, administration, and deployment of Mesh within your business.

## Explore other resources to learn about Mesh setup and deployment

See the Intro to Mesh article to learn about Mesh at a high-level, explore the possibilities, and understand all the resources available to you.

## Azure portal (Preview)

The Azure portal (Preview) is the link to use as a Admin tasked with setting up Azure to deploy Mesh to your organization.

[Azure portal (Preview)](https://portal.azure.com/?microsoft_azure_metaverseExtension_assettypeoptions=%7B%22metaverse%22%3A%7B%22options%22%3A%22%22%7D%7D&microsoft_azure_metaverseExtension=true&feature.canmodifyextensions=true#home)

## Azure portal features for Meshh

1. Tenant set up. Set up the tenant for Mesh inside Azure portal to set up service principals for managing Mesh worlds resources, users, and events.
1. Mesh worlds creation and management. Create and manage Mesh worlds to suit corporate needs and organizational structures.
1. Access policies & permissions per Mesh world or event. Assign access for Azure portal management and give permissions to design teams for environment uploading. For events, assign event host permissions, and adjust who can access events through the Microsoft Mesh app on PC or Quest 2.
1. Mesh Toolkit Uploader for environments. Upload custom environments and deploy and publish the Azure resources needed by the Mesh app.
1. Environment selection and adjustment. Use the Azure portal to assign environments to Mesh worlds or events once environments are uploaded by 3D designers via the Mesh Toolkit Uploader.

## Security

Some management of Mesh will happen in the Azure portal, but it will be limited to resources specific to Mesh. Anyone listed as the Owner of the Storage subscription you provided when you enrolled will be able to see the Mesh app after it is installed to your Azure tenant. The owner can also assign additional access to the subscription. Note that by default the Global Admin does not have access to subscriptions they do not own, but you can [elevate access to manage all Azure subscriptions](/azure/role-based-access-control/elevate-access-global-admin).

The Storage subscription owner should create one or more resource groups, which will serve as containers for Mesh worlds. Owners can assign additional Owner, Content contributor, or read only access roles as needed.

- Owner. Allows users to manage all Mesh resources in your resource group.

- Content contributor. Allows users to see and manage Mesh resources in your resource group, create/delete events, select environments, add users, and share events.

- Read permissions. Allows users to see the resources in the Mesh resource group, but not manage or edit them.

Make sure you have access to an Owner of the Storage subscription, so you will be able to get resource groups created and access assigned as soon as the Mesh app is available to you.

### Work with your security organization

Before deploying any new app or service, you must consider the security implications and work closely with your security team to make sure you comply with all standard security policies. Discuss the following Mesh requirements in advance with the appropriate Security owners.

## Allow endpoints

If your organization allows or blocks access to certain endpoints, you will need to work with them in advance to enable the endpoints required for Mesh.

**Ensure endpoints are allowed**
To ensure Mesh works properly, allow the following endpoints.

```dotnetcli
- *.officeapps.live.com
- *.microsoft.com
- *.meshxp.net
- *.office365.com
- *.office.com
- *.office.net
- *.servicebus.windows.net
```

## Firewall ports

In addition to the endpoints listed above, Mesh also requires the following outgoing ports to be opened in your firewall: 

- TCP ports 80, 443, 8089, and 8989
- TCP & UDP ports 30,000-31,000
- UDP ports 3478-3481

Mesh traffic will use IP addresses in the AzureCloud service tag.
For more information about service tags, see the [Azure service tags overview](/azure/virtual-network/service-tags-overview).

### Conditional access

Conditional access is an important part of a zero-trust approach to helping secure your network and resources. As part of zero trust, many companies use conditional access features with Azure Active Directory and Microsoft Intune to restrict the types of devices that are permitted to access the network, and even the operating system version and configuration on those devices; devices that meet the defined profile are allowed in, and any other device that is not specified is denied access.
In the future, Meta has stated that Quest 2 will provide support for MDM which will probably provide more specific control over how Quest 2 devices are permitted or denied access. In the meantime, because Quest 2 devices cannot be recognized and managed, allowing them access to your network may involve changes to your conditional access policy that go against company security standards. Each company using Mesh in pre-release will have to work with their security and endpoint management teams to decide if a policy can be constructed that is acceptable to the company’s risk profile while still permitting access to Quest 2 devices.

For more information about Conditional Access, see [conditional access and common uses of Intune](/mem/intune/protect/conditional-access-intune-common-ways-use).

## Verify your licensing

All tenants that you use for Mesh for Teams must have a Microsoft 365 E3 or E5 license, including any test tenants. You must also have a Storage subscription for Azure where your Mesh resources can be uploaded.


### License requirements for Mesh

Ensure that you have proper licenses to access Mesh.

*Need assistance? Contact your Microsoft partner for clarification.*

|Mesh Experience   | Mesh for Teams                | Custom Worlds                          | Mesh for Teams & Custom Worlds  |
|------------------|-------------------------------|----------------------------------------|---------------------------------|
|Subscriptions     |  Microsoft 365 E3 or E5       |   Azure subscription with storage      |  Microsoft E3 or E5 & Azure subscription       |

## Provide Microsoft with required information

Microsoft requires certain information to provision tenants, users, and subscriptions for pre-release features in Mesh.

After you have the information, request [Allowlist for Custom Worlds here](https://forms.office.com/r/tUxeatkdiA).

Fill out the form once per tenant you want provisioned, including dev and pre-production tenants.

### Tenant ID

Before your tenant can be onboarded, you must provide Microsoft with the unique ID assigned to each Azure Active Directory tenant.

#### Who can do this?

Any user in the domain can see the tenant ID.

#### Where?

Go to [https://aa.portal.azure.com](https://aa.portal.azure.com) and look under Basic information.