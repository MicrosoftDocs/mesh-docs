---
title: Preparing your organization for Mesh
description: Prepare your organization to adopt Mesh and its features. Organize a team to manage setup and distribution.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 10/11/2023
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

1. [Work with your security team](#work-with-your-organizations-security-team)

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
> and running the Mesh preview, for example Licensing, Security, and
> Endpoint Management. Other stakeholders like Help Desk and Human
> Resources may also need to be consulted.

To participate in the Mesh public preview, you must agree to the terms of use and privacy statements. You should be in contact with your legal and privacy teams to review those terms before accepting them.

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

    All users who will be participating in immersive experiences together must
have native accounts in the same Microsoft Entra ID ([formerly Azure Active Directory](https://www.microsoft.com/en-us/security/business/identity-access/microsoft-entra-id)) - guest access to the tenant does not work.

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
your production tenant for Mesh Public Preview. While you can create other tenants
for testing, people who use Teams throughout the day are highly unlikely
to want to log out of their main Teams account to log into a different
account in a different tenant. A separate tenant is more practical for
the Mesh app, where it's simpler to flip between accounts.

Each tenant can have multiple Azure Storage subscriptions, but the Azure
Storage subscription used for Mesh cloud scripting must be in the same EntraID as
the users who will attend events and the developers who will upload and manage the scripts.

### Contact owners of supporting teams

To complete the steps to get Mesh Public Preview running, you will need to either
have various rights and permissions or be in contact with people in your
organization who can grant the rights and permissions you will need.
Depending on your company structure and policies, this process can be
time-consuming, so it helps to start the outreach as soon as possible.

The following section lists organizational roles that you will probably need to work with to complete the required pre-deployment tasks:

#### Teams apps managers

The adminsitration for immersive spaces and avatars will happen in the Teams admin
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

> [!IMPORTANT]
> In order to streamline the admin experience, admins will no longer need to configure Mesh in M365 Apps Admin Center. If you had previously restricted Mesh access to users or groups in your organization via the Mesh policy found in the M365 Apps Admin Center, you will need to switch to restricting access via the Mesh service plan instead in the M365 Admin Center (MAC) **by the end of February, 2024**.

For more information about service plans, see [Configure access to Mesh using service plans](setup-m365-mesh.md#configure-access-to-mesh-using-service-plans). 

## End user license agreement

Your users must enter a separate agreement directly with Microsoft to enable spatial audio for Mesh experiences. That agreement is presented to your users before the user's first use of Mesh. If a user does not wish to enter into that agreement, the user cannot use Mesh.

If an admin does not agree to the license agreement terms, then admins can disable Mesh for users via Service Plans described above.

For more info about service plans and the end user license agreement, see [End user license agreement](setup-m365-mesh.md#end-user-license-agreement).

## Review endpoint managers

Make sure you know your organization's process for deploying apps. The Mesh app is available in the Microsoft Store and can be depoloyed from there using your MDM
(mobile device management) solution like Microsoft Intune to deploy the
app and make it show up in the users' Company Portal. If you block
access to the Microsoft Store, you can use WinGet instead. For more information about deploying apps with
Microsoft Intune, see:

[Add Microsoft Store apps to Microsoft Intune](/mem/intune/apps/store-apps-microsoft)

## Configure Azure for Cloud Scripting

If your developers plan to build custom Mesh environments that will use [Mesh Cloud Scripting](../../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts.md), they will require an Azure subscription to which they can deploy their cloud scripting service. An Azure subscription is not required for environments that only use [Mesh Visual Scripting](../../develop/script-your-scene-logic/visual-scripting/visual-scripting-overview.md).

See [Set up Cloud Scripting infrastructure in Azure](../../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-setup-infrastructure.md) for more details on these requirements.

## Work with your organization's security team

Before deploying any new app or service, you must consider the security
implications and work closely with your security team to make sure you
comply with all standard security policies. Discuss the following Mesh
requirements in advance with the appropriate Security owners.

### Ensure endpoints can be allowed for immersive spaces in Teams

To ensure the Mesh features work properly, the following endpoints **must**
be allowed through your firewall or proxy server.
All endpoints need to allow traffic on TCP ports 80 and 443:

- \*.microsoft.com

- \*.office.com

- \*.office.net

- \*.cloud.microsoft

To learn more, see how to [Set up immersive spaces in Teams](/microsoftteams/meeting-immersive-spaces).

### Firewall Ports for immersive spaces in Teams

In addition to the endpoints listed above, Mesh also requires that outgoing
traffic be allowed to IP addresses in the "AzureCloud" service tag over the
following protocols and ports:

- TCP ports 80, 443

- TCP & UDP ports 30,000-30,499

- UDP ports 3478-3481

If you need to resolve a service tag to a list of IP ranges, you can
periodically use the [service tag API][service-tag-api] or [download a
snapshot][service-tag-download].

For more information about service tags, see the [Azure service tags overview][service-tag].

To learn more, see how to [Set up immersive spaces in Teams](/microsoftteams/meeting-immersive-spaces).

### Ensure endpoints can be allowed for Mesh avatars in Teams

To ensure avatars in Teams works properly, allow the following
endpoints:
*All endpoints need to allow traffic on TCP ports 80 and 443*:

- \*.microsoft.com
- \*.office.com
- \*.office.net
- \*.cloud.microsoft

Follow this link to learn more about how to Set up avatars for Microsoft
Teams.
[Set up avatars in Microsoft Teams](/microsoftteams/meeting-avatars)

### Ensure endpoints can be allowed for immersive spaces in Mesh (Mesh app)

To ensure Mesh works properly, allow the following endpoints.
All endpoints need to allow traffic on TCP ports 80 and 443:

- \*.officeapps.live.com

- \*.microsoft.com

- \*.office365.com

- \*.office.com

- \*.office.net

- \*.cloud.microsoft

### Firewall Ports for the immersive spaces in Mesh (Mesh app)

In addition to the endpoints listed above, Mesh also requires that outgoing
traffic be allowed to IP addresses in the "AzureCloud" service tag over the
following protocols and ports:

- TCP ports 80, 443

- TCP & UDP ports 30,000-30,499

- UDP ports 3478-3481

If you need to resolve a service tag to a list of IP ranges, you can
periodically use the [service tag API][service-tag-api] or [download a
snapshot][service-tag-download].

For more information about service tags, see the [Azure service tags overview][service-tag].

### Conditional Access & Quest

Conditional access is an important part of a zero-trust approach to helping secure your network and resources. As part of zero trust, many companies use conditional access features policies with Azure Active Directory and Microsoft Intune to restrict the types of devices that are permitted to access company resources, and even the operating system version and configuration on those devices; devices that meet the defined profile are allowed in, and any other device that is not specified is denied access. Meta has released a beta GA version MDM support for Quest that works with Intune. Each company using Mesh in pre-release will have to work with their security and endpoint management teams to decide if a policy can be constructed that is acceptable to the company's risk profile while still permitting access to Quest devices.

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
