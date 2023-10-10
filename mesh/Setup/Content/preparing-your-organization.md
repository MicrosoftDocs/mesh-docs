---
title: Preparing your organization for Mesh
description: Prepare your organization to adopt Mesh and its features. Organize a team to manage setup and distribution.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, Immersive spaces, Avatars, getting started, documentation, features
---

# Preparing your organization for Mesh

## Gather Your v-team

This page covers the required tasks and suggest functional roles
that may need to know about the rollout, but follow your organization's
standard rollout process, including change and configuration management.

Executive-level sponsorship is highly advisable to help with any cross-team blocking issues.

You will need access to several administration tools, so either get
access to those tools or get people on the v-team who can access the
tools.

- Teams Admin Center (TAC) is needed to configure avatar and immersive spaces administration

- Azure portal is needed to administer Mesh cloud scripting (if your environments optionally use that form of scripting).

- Other tasks like permitting URLs and firewall ports will be done in
    whatever administrative tools are used by your organization.

There are some setup tasks that may require cooperation from individuals
or departments outside of the individual or team that will be deploying
and running the Mesh preview, for example Licensing, Security, and
Endpoint Management. Other stakeholders like Help Desk and Human
Resources may also need to be consulted.

To participate in the public preview, you must agree to the terms of use and privacy statements. You should be in contact with your legal and privacy teams to review those terms before accepting them.

## Verify Your Licensing

For immersive spaces in Teams, your users must have licenses for one of the following: Teams Essentials, Microsoft 365 Business Basic, Microsoft 365 Business Standard, Microsoft 365 Business Premium, Microsoft 365 E3/E5, and Office 365 E1/E3/E5.

For Microsoft Mesh, a Teams Premium license is required during the Public Preview. If you plan to use Mesh cloud scripting, you must also have an Azure subscription with storage.

If your organization plans to create custom worlds for Microsoft Mesh,
your world building team will need licenses for Unity.

## Which Tenant Should I Provision for Mesh Public Preview?

The two main factors to consider when choosing which tenant(s) to
provision for Mesh are:

1. Which users you want to participate in immersive experiences

2. The tradeoffs between having unlimited control of a domain and
    having ultimate responsibility for running the domain securely and
    effectively.

Mesh Public Preview will allow participants to provision multiple tenants.
Provisioning up your primary production tenant for Mesh is recommended
because it will give you the biggest scope to test with, but it may
create overhead work through internal procedures and approvals. You may
also want to provision tenants for test/dev/pre-production. Because all
users who will be participating in immersive experiences together must
have accounts together in the same Microsoft Entra (formerly Azure Active Directory), you may
want to consider using a separate tenant if you want to collaborate with
people outside your production tenant; guest accounts in Entra do not have
access to Mesh experiences. There is no technical barrier to
creating user accounts in a production tenant for people who do not work
for that organization, but there may be strong business reasons against
doing so. However, creating additional tenants will increase complexity
for admins and users to manage accounts, may also incur additional
expenses for licensing and domain management, and may require additional
process within your organization.

If you expect to use immersive spaces in Teams for users in
your production version of Teams, you will definitely want to provision
your production tenant for Mesh Public Preview. While you can create other tenants
for testing, people who use Teams throughout the day are highly unlikely
to want to log out of their main Teams account to log into a different
account in a different Entra. A separate tenant is more practical for
the Mesh app, where it's simpler to flip between accounts.

Each tenant can have multiple Azure Storage subscriptions, but the Azure
Storage subscription used for Mesh scripting must be in the same Entra as
the users who will attend events and the developers who will upload and manage the scripts.

### Contact Owners of Supporting Teams

To complete the steps to get Mesh Public Preview running, you will need to either
have various rights and permissions or be in contact with people in your
organization who can grant the rights and permissions you will need.
Depending on your company structure and policies, this process can be
time-consuming, so it helps to start the outreach as soon as possible. The following section lists organizational
roles that you will probably need to work with to complete the required
pre-deployment tasks.

#### Teams Apps Managers

Most of the administration for Mesh will happen in the Teams admin
portal, [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
You will need the tenant Global Administrator to assign someone on the
Mesh team the role of Teams Administrator in Azure Active Directory, or
you will need to work closely with a current Teams Apps Manager to make
all necessary configurations.

#### Teams App Policy

Two of the Mesh components you will be using are Teams apps; you should
set policy to make sure only approved users have access to them. Modify
the Teams app policies at the Global or custom level to allow/block the
Mesh apps as needed. If you want your designated users to have the Mesh
components installed automatically, you must set the Teams Apps setup
policies too. Coordinate with whoever owns Teams app management to plan
for appropriate policies. For more information about Teams access
control, see
<https://admin.microsoft.com/Adminportal/Home#/rbac/directory>.

#### Teams Feedback Policies

Microsoft relies on feedback from users to make better products. The
Teams administrator can set whether users can send feedback about Teams
to Microsoft. Feedback can be permitted based on Entra
group membership. If Teams feedback is disabled, users will not be able
to send feedback about Mesh features built into Teams. We strongly
encourage your org to permit this feedback for Mesh users but consult
your company policies before making any changes. For more information
about managing feedback, see

[Manage feedback policies in Teams](/microsoftteams/manage-feedback-policies-in-teams)

## Office Apps Admin

You must have a policy set in Office Cloud Policy Service to permit user to access any form of Mesh. Also, OCPS
lets you enforce policy settings
for whether users can send feedback about Microsoft 365 apps for
enterprise; this is a separate setting from the Teams feedback policies
discussed previously and must be enabled for users of all Mesh features
that operate independently of Teams. The Office Apps Admin can assign
this policy. The Security Administrator role and Global Administrator
can also assign Cloud Policy.

We strongly encourage your org to permit the following feedback settings
for Mesh users but consult your company policies before making any
changes.

- Allow the user of connected experiences in Office

- Allow users to submit feedback to Microsoft

- Allow users to receive and respond to in-product surveys from
    Microsoft

- Allow users to include screenshots and attachments when they submit
    feedback to Microsoft

- Allow Microsoft to follow up on feedback submitted by users

- Allow users to include log files and content samples when feedback
    is submitted to Microsoft

For more information about managing feedback, see:
[Steps for create a policy configuration](/deployoffice/admincenter/overview-cloud-policy)

## Endpoint Managers

Make sure you know your organization's process for deploying apps. The Mesh app is available in the Microsoft Store and can be depoloyed from there using your MDM
(mobile device management) solution like Microsoft Intune to deploy the
app and make it show up in the users' Company Portal. If you block
access to the Microsoft Store, you can use WinGet instead. For more information about deploying apps with
Microsoft Intune, see:

[Add Microsoft Store apps to Microsoft Intune](/mem/intune/apps/store-apps-microsoft)

## Azure Administrators

If your developers plan to build custom Mesh environments that will use [Mesh cloud scripting](../../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts.md), they will require an Azure subscription to which they can deploy their cloud scripting service.  An Azure subscription is not required for environments that only use [Mesh visual scripting](../../develop/script-your-scene-logic/visual-scripting/visual-scripting-overview.md).

See [Set up Cloud Scripting infrastructure in Azure](../../develop/script-your-scene-logic/cloud-scripting/cloud-scripting-setup-infrastructure.md) for more details on these requirements.

## Work with your organization's security team

Before deploying any new app or service, you must consider the security
implications and work closely with your security team to make sure you
comply with all standard security policies. Discuss the following Mesh
requirements in advance with the appropriate Security owners.

### Ensure endpoints can be allowed for Mesh immersive spaces

To ensure the Mesh features work properly, the following endpoints must
be allowed through your firewall or proxy server.
All endpoints need to allow traffic on TCP ports 80 and 443:

- \*.microsoft.com

- \*.office.com

- \*.office.net

To learn more, see how to [Set up immersive spaces in Teams](/microsoftteams/meeting-immersive-spaces).

### Firewall Ports for Mesh immersive spaces

In addition to the endpoints above, Mesh also requires the following
outgoing ports to be opened in your firewall:

- TCP ports 80, 443

- TCP & UDP ports 30,000-30,499

- UDP ports 3478-3481

Mesh traffic will use IP addresses in the AzureCloud service tag.

For more information about service tags, see the [Azure service tags overview](/azure/virtual-network/service-tags-overview).

To learn more, see how to [Set up immersive spaces in Teams](/microsoftteams/meeting-immersive-spaces).

### Ensure endpoints can be allowed for Mesh avatars in Teams

To ensure avatars in Teams works properly, allow the following
endpoints:
*All endpoints need to allow traffic on TCP ports 80 and 443*:

- \*.microsoft.com
- \*.office.com
- \*.office.net

Follow this link to learn more about how to Set up avatars for Microsoft
Teams.
[Set up avatars in Microsoft Teams](/microsoftteams/meeting-avatars)

### Ensure endpoints can be allowed for the Mesh app

To ensure Mesh works properly, allow the following endpoints.
All endpoints need to allow traffic on TCP ports 80 and 443:

- \*.officeapps.live.com

- \*.microsoft.com

- \*.office365.com

- \*.office.com

- \*.office.net

### Firewall Ports for the Mesh app

In addition to the endpoints listed above, Mesh also requires the
following outgoing ports to be opened in your firewall:

- TCP ports 80, 443, 8089, and 8989

- TCP & UDP ports 30,000-30,499

- UDP ports 3478-3481

### Conditional Access

Conditional access is an important part of a zero-trust approach to
helping secure your network and resources. As part of zero trust, many
companies use conditional access features with Azure Active Directory
and Microsoft Intune to restrict the types of devices that are permitted
to access company resources, and even the operating system version and
configuration on those devices; devices that meet the defined profile
are allowed in, and any other device that is not specified is denied
access. Meta has released a beta version MDM support for Quest. Each
company using Mesh in pre-release will have to work with their security
and endpoint management teams to decide if a policy can be constructed
that is acceptable to the company's risk profile while still permitting
access to Quest devices. For more information about Conditional Access,
see:

[Common ways to use Conditional Access with Intune](/mem/intune/protect/conditional-access-intune-common-ways-use)

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
> [Get started with Avatars in Teams](https://support.microsoft.com/topic/5384e7b7-30c7-4bcb-8065-0c9e830cc8ad)

> [!div class="nextstepaction"]
> [Prepare your organization for Immersive spaces (coming soon)](/microsoftteams/public-preview-doc-updates)
