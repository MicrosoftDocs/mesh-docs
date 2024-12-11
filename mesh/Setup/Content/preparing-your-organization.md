---
title: Preparing your organization for Mesh
description: Prepare your organization to adopt Mesh and its features. Organize a team to manage setup, deployment, and onboarding.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 5/20/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, Immersive spaces, Avatars, getting started, documentation, features
---

# Preparing your organization for Mesh

This page covers the required tasks and suggested functional roles
that may need to know about the rollout, but follow your organization's
standard rollout process, including change and configuration management.

This content covers requirements for Mesh implementations for Immersive spaces in Mesh and immersive spaces in Teams. At a high level, the steps are:

1. [Gather your deployment team](#gather-your-deployment-team)

1. [Verify licenses and policies](#verify-your-licenses-and-policies)

1. [Consider tenant selection](#consider-which-tenant-to-provision-for-mesh)

1. [Contact owners of supporting teams](#contact-owners-of-supporting-teams)

1. [Configure service plan to allow user access](#configure-service-plan-to-allow-user-access)

1. [Configure your network for Mesh experiences](#work-with-your-organizations-security-team)

1. [Work with stakeholders to begin deployment](#work-with-stakeholders-that-communicate-change)

After planning for your Mesh implementation, learn how [set up Microsoft Mesh](/mesh/setup/content/setup-m365-mesh#prerequisites) and [set up immersive spaces in Teams](/microsoftteams/meeting-immersive-spaces).

## Gather your deployment team

Executive-level sponsorship is highly advisable to help with any cross-team blocking issues.

You will need access to several administration tools:

- Teams Admin Center (TAC) is needed to configure avatar and immersive spaces administration.

- Azure portal is needed to administer Mesh cloud scripting used for custom Mesh environments (if your environments optionally use that form of scripting).

- Other tasks like permitting URLs and firewall ports will be done in
    whatever administrative tools are used by your organization.
  
- Mesh uses other parts of the Microsoft 365 suite. If your organization restricts access to these resources, parts of Mesh won't work. Talk to whoever has access to the Microsoft 365 Admin tools to determine if there are any restrictions and to test whether those restrictions will interfere with Mesh.

    For example, the table below defines what access is needed for specific actions:

    | Mesh Action | Access Needed |
    | --- | --- |
    | Create a Mesh Collection  | Create Microsoft 365 group |
    | Be added as a member to a Mesh Collection  | Access Microsoft 365 groups |
    | Create a Mesh event | Access to Microsoft 365 Calendar |
    | Be invited to a Mesh event | Access to Outlook Mail |
    | Create a template | Access to SharePoint |
    | Add an image or video top an event or template | Access to either SharePoint or OneDrive |

> [!TIP]
> There are some setup tasks that may require cooperation from individuals
> or departments outside of the individual or team that will be deploying
> and running Mesh, for example Licensing, Security, and
> Endpoint Management. Other stakeholders like Help Desk and Human
> Resources may also need to be consulted.

## Verify your licenses and policies

For avatars and immersive spaces in Teams, your users must have licenses for one of the following: Teams Essentials, Microsoft 365 Business Basic, Microsoft 365 Business Standard, Microsoft 365 Business Premium, Microsoft 365 E3/E5, and Office 365 E1/E3/E5.

[!INCLUDE [Include file for the immersive spaces in Mesh article](../../Includes/license-requirements-for-Mesh.md)]

For help, see the [immersive spaces in mesh licensing Troubleshooting and FAQs](../../Resources/mesh-troubleshooting.md#what-are-the-license-requirements-for-immersive-spaces-in-mesh).

[!INCLUDE [The include file for license reqs for immersive spaces in Teams](../../Includes/license-requirements-for-immersive-spaces-in-teams.md)]

For help, see the [immersive spaces in Teams licensing Troubleshooting and FAQs](../../Resources/mesh-troubleshooting.md#what-are-the-license-requirements-for-immersive-spaces-in-teams).

## Consider which tenant to Provision for Mesh

The two main factors to consider when choosing which tenant(s) to
provision for Mesh are:

1. Which users should be able to access immersive experiences.

    Users with native accounts in your Microsoft Entra ID will have the easiest time accessing your events. You can invite users with Guest accounts in your Microsoft Entra ID to attend your events, but they will have to do extra steps to log into Mesh with their Guest account. Also, Guest users cannot create events or be co-organizers for Mesh events. For more information, see [Invite guest attendees to Mesh events](/mesh/setup/content/guest-access).
   
   
1. The tradeoffs between having unlimited control of a domain and
    having ultimate responsibility for running the domain securely and
    effectively.

### Primary tenant for Mesh

Provisioning up your primary production tenant for Mesh is recommended
because it will give you the biggest scope to test with, but it may
create overhead work through internal procedures and approvals.

### Separate tenant for Mesh

If you want to collaborate with
people outside your production tenant, you might want to set up a separate tenant just for Mesh. There is no technical barrier to creating user accounts in a production tenant for people who do not work for that organization, but there may be strong business reasons against doing so.

> [!NOTE]
> However, creating additional tenants will increase complexity
> for admins and users to manage accounts, may also incur additional
> expenses for licensing and domain management, and may require additional
> process within your organization.

If you expect to use immersive spaces in Teams for users in
your production version of Teams, you will definitely want to provision
your production tenant for Mesh. While you can create other tenants
for testing, people who use Teams throughout the day are highly unlikely
to want to log out of their main Teams account to log into a different
account in a different tenant. A separate tenant is more practical for
the Mesh app, where it's simpler to flip between accounts.

Each tenant can have multiple Azure Storage subscriptions, but the Azure
Storage subscription used for Mesh cloud scripting must be in the same EntraID as
the users who will attend events and the developers who will upload and manage the scripts.

### Contact owners of supporting teams

To complete the steps to get Mesh running, you will need to either
have various rights and permissions or be in contact with people in your
organization who can grant the rights and permissions you will need.
Depending on your company structure and policies, this process can be
time-consuming, so it helps to start the outreach as soon as possible.

The following section lists organizational roles that you will probably need to work with to complete the required pre-deployment tasks:

#### Teams apps managers

The administration for immersive spaces and avatars will happen in the Teams admin
portal, [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
You will need the tenant Global Administrator to assign someone on the
Mesh team the [role of Teams Administrator in Microsoft Entra](/microsoftteams/using-admin-roles), or
you will need to work closely with a current Teams Apps Manager to make
all necessary configurations.

#### Teams apps policies

Two of the Mesh components you will be using are Teams apps; you should
set policy to make sure only approved users have access to them. Modify
the Teams app policies at the Global or custom level to allow/block the
Mesh apps as needed. If you want your designated users to have the Mesh
components installed automatically, you must set the Teams Apps setup
policies too. Coordinate with whoever owns Teams app management to plan
for appropriate policies. For more information about Teams access
control, see
<https://admin.microsoft.com/Adminportal/Home#/rbac/directory>.

#### Teams feedback policies

Microsoft relies on feedback from users to make better products. The
Teams administrator can set whether users can send feedback about Teams
to Microsoft. Feedback can be permitted based on Entra ID
group membership. If Teams feedback is disabled, users will not be able
to send feedback about Mesh features built into Teams. We strongly
encourage your org to permit this feedback for Mesh users but consult
your company policies before making any changes. For more information
about managing feedback, see

[Manage feedback policies in Teams](/microsoftteams/manage-feedback-policies-in-teams)

## Configure service plan to allow user access

For more information about service plans, see [Configure access to Mesh using service plans](setup-m365-mesh.md#configure-access-to-mesh-using-service-plans).

## Review endpoint managers

Make sure you know your organization's process for deploying apps. The Mesh app is available in the Microsoft Store and can be depoloyed from there using your MDM
(mobile device management) solution like Microsoft Intune to deploy the
app and make it show up in the users' Company Portal. If you block
access to the Microsoft Store, you can use WinGet instead. For more information about deploying apps with
Microsoft Intune, see:

[Add Microsoft Store apps to Microsoft Intune](/mem/intune/apps/store-apps-microsoft)

## Configure Azure for Cloud Scripting

If your developers plan to build custom Mesh environments that will use [Mesh Cloud Scripting](../../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts.md), they will require an Azure subscription to which they can deploy their cloud scripting service. An Azure subscription is not required for environments that only use [Mesh Visual Scripting](../../develop/script-your-scene-logic/visual-scripting/visual-scripting-overview.md).

For more details on the prerequisites for Mesh Cloud Scripting, see [Prepare for your first Mesh Cloud Scripting project](../../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-prepare-for-your-project.md).

## Work with your organization's security team

Before deploying any new app or service, you must consider the security
implications and work closely with your security team to make sure you
comply with all standard security policies. Discuss the following Mesh
requirements in advance with the appropriate Security owners.

## Endpoints and firewall configuration

As with all Microsoft products, allowing the endpoints and ports required for Mesh experiences is necessary to achieve full functionality and optimal performance for your users. How you use the network configuration requirements for Mesh depends on your enterprise organization network architecture.

[!INCLUDE [Include file for the immersive spaces ports and firewall requirements article](../../Includes/immersive-spaces-teams-ports-firewall.md)]

[!INCLUDE [Include file for the custom immersive spaces ports and firewall requirements in Mesh article](../../Includes/custom-immersive-spaces-ports-firewall.md)]

## Network bandwidth requirements

[!INCLUDE[Include file for Mesh bandwidth requirements](../../Includes/mesh-bandwidth-requirements.md)]

[!INCLUDE[Include file for Immersive spaces in Teams bandwidth requirements](../../Includes/immersive-spaces-teams-bandwidth-requirements.md)]

### Conditional Access & Quest

> [!NOTE]
> Conditional Access policies should be modified only by someone in your organization with a clear understanding of the implications of the changes. Consult your security team or other expert in your company security policies before making any changes.

> [!NOTE]
> Mesh does not currently support Mobile Application Management (MAM) which would be needed in situations where your organization supports the use of Personal Quest devices (BYOD). As of version 24.18, Mesh now supports conditional access policies through the new and improved native authentication flow on Quest. 

Conditional access is a crucial component of a zero-trust strategy for securing your network and resources. Many companies implement conditional access policies using Microsoft Entra and Microsoft Intune to control which devices are permitted to access company resources. These policies can restrict access based on device types, operating system versions, and configurations. Only devices that meet the specified criteria are granted access; all others are denied.

With native authentication support for Mesh on Quest, organizations can implement managed devices with Quest for Business and use Intune to manage device profiles, conditional access policies, and more. 

Each company using Mesh will have to work with their security and endpoint management teams to decide the following: Do we need to have a managed Quest device fleet? Doing so can ensure compliance with corporate policies and will require the following: 

- **If the organization chooses to have managed Quest devices:** You will need to ensure your Quest device fleet is managed through Quest for Business and an MDM provider. Once managed, [create a device-based Conditional Access policy](/mem/intune/protect/create-conditional-access-intune) to specify the conditions for signing in to applications on the Quest. 

- **If the organization wants to make an exception for Quest:** Create a Conditional Access policy that is acceptable to the company's risk profile while still permitting access to Quest devices. You will need to exclude the Quest device by [filtering for devices](/entra/identity/conditional-access/concept-condition-filters-for-devices) on a new or existing Conditional Access policy.   
  
To exclude filtered devices like the Quest model and Meta manufacturer that are not registered in Entra ID, you can set up a Conditional Access policy using the **negative operator**. To apply a **negative operator**, reference [policy behavior with filter for devices](/entra/identity/conditional-access/concept-condition-filters-for-devices). If you were to use a positive operator, the filter rule would only apply when a device exists in the directory and the configured rule matches the attribute on the device.

Both options will enable the use of Mesh. However, it's recommended that organizations manage their Quest devices to ensure security and compliance. If neither action is taken and a user in your organization attempts to launch Mesh on Quest for an unmanaged device where conditional access policies are applied, they will receive errors [AADSTS50199](/entra/identity-platform/reference-error-codes) and [AADSTS53003](/entra/identity-platform/reference-error-codes).  

For more information about Conditional Access, see:

- [Common ways to use Conditional Access with Intune](/mem/intune/protect/conditional-access-intune-common-ways-use)

- [How can I manage Quest VR headsets for my organization?](../../Resources/mesh-troubleshooting.md#how-can-i-manage-quest-vr-headsets-for-my-organization)

## Work with Stakeholders That Communicate Change

The stakeholders listed above all have active steps that will impact the
setup of your Mesh environment, but there may be other parts of your org
that will be impacted by the deployment or might have policies or
guidelines that need to be considered early in your planning process.
Here are some areas of your organization you might need to reach out to
before you deploy.

- Change Communications: If you have a standard process for contacting
    users about pending changes, make sure Mesh is part of those
    communications.

- Help Desk: Have a support plan in place for users who experience
    issues using Mesh. Make sure your Mesh admins have a way to review
    issues experienced by users so they can be communicated to Microsoft
    as needed.

- Human Resources: While Mesh does not require any specific action
from Human Resources for deployment or operations, HR may be
interested that Mesh is about creating immersive experiences for
users. Check with your HR department for any policies that may
impact your Mesh meeting experience.

- Company Branding: If you decide to create custom meeting experiences
for your users, you should check with your company branding experts
to make sure any meeting assets meets branding standards.

### Preparing Users for Mesh Avatars

When you first roll out the avatar feature in Teams, some users may need
guidance on when it's good to use them, and not good to use them.
Microsoft has published a blog on Avatar etiquette: [How Microsoft
employees are using avatars in Microsoft Teams in their meetings](https://www.microsoft.com/insidetrack/blog/avatar-etiquette-how-microsoft-employees-are-using-avatars-for-microsoft-teams-in-their-meetings/). This
doc can help inform materials you might want to share with your users.

## Summary

Microsoft Mesh offers many powerful features that enhance communication
and collaboration in remote and hybrid workplaces. Because this service
provides experiences that span services, make sure you plan for all
necessary stakeholders to provide input, both those mentioned here and
others specific to your organization.

## Next steps with Mesh

> [!div class="nextstepaction"]
> [Set up Microsoft Mesh](/mesh/setup/content/setup-m365-mesh)

> [!div class="nextstepaction"]
> [Set up immersive spaces in Teams](/microsoftteams/meeting-immersive-spaces)

> [!div class="nextstepaction"]
> [Set up avatars for Teams](/microsoftteams/meeting-avatars)

[service-tag]: /azure/virtual-network/service-tags-overview
[service-tag-api]: /azure/virtual-network/service-tags-overview#use-the-service-tag-discovery-api
[service-tag-download]: /azure/virtual-network/service-tags-overview#discover-service-tags-by-using-downloadable-json-files
