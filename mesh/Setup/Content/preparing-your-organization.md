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

> [!IMPORTANT]
> For the 23.11 release, this document is in a draft form. Due to the nature of this release, there may be content that is out of date.
> 
> We thank you for your patience in this transition. In the coming weeks we will provide more up-to-date information regarging our transition to M365 and how to prepare your organization for that.

## Gather Your v-Team

This document will cover the required tasks and suggest functional roles
that may need to know about the rollout, but follow your organization's
standard rollout process, including change and configuration management.

You must have an executive-level sponsor, either an IT Director or
CIO-level executive. Sponsorship is advisable to help with any
cross-team blocking issues, and it is a requirement to participate in
the Teams TAP.

You will need access to several administration tools, so either get
access to those tools or get people on the v-team who can access the
tools.

- Administration for Mesh Teams features will be done in Microsoft
    Teams Admin Center (TAC) in the Microsoft 365 Admin Portal.

- Administration for Mesh features related to Worlds will be done in a
    Mesh resource in the Azure Portal.

- Other tasks like permitting URLs and firewall ports will be done in
    whatever administrative tools are used by your organization.

There are some setup tasks that may require cooperation from individuals
or departments outside of the individual or team that will be deploying
and running the Mesh preview, for example Licensing, Security, and
Endpoint Management. Other stakeholders like Help Desk and Human
Resources may also need to be consulted.

To participate in the TAP, you must have an existing Non-Disclosure
Agreement (NDA) or sign a new one if you do not have one or if your
current one expires in less than three months. You must also sign the
[Microsoft Teams Pre-Release Technologies
agreement](https://aka.ms/TAP100ProgramDocument). You should make sure
you engage your legal team to review both agreements as soon as
possible.

## Verify Your Licensing

All tenants that you use for Mesh for Teams must have Microsoft 365
Enterprise E3, Microsoft 365 Enterprise E5, Microsoft 365 Business
Standard, Microsoft 365 Business Premium or Teams Premium. including any
test tenants. You must also have an Azure subscription for Azure where
your Mesh resources can be uploaded. Organizations may enroll multiple
tenants to support preproduction or test tenants; each tenant must have
the required licenses and subscriptions.

If your organization plans to create custom worlds for Mesh standalone,
your world building team will need licenses for Unity.
 
## Which Tenant Should I Provision for Mesh TAP?

The two main factors to consider when choosing which tenant(s) to
provision for Mesh are:

1. Which users you want to participate in immersive experiences

2. The tradeoffs between having unlimited control of a domain and
    having ultimate responsibility for running the domain securely and
    effectively.

Mesh TAP will allow participants to provision multiple tenants.
Provisioning up your primary production tenant for Mesh is recommended
because it will give you the biggest scope to test with, but it may
create overhead work through internal procedures and approvals. You may
also want to provision tenants for test/dev/pre-production Because all
users who will be participating in immersive experiences together must
have accounts together in the same Azure Active Directory, and you may
want to consider using a separate tenant if you want to collaborate with
people outside your production tenant; guest accounts in AAD do not have
access to Mesh immersive experiences. There is no technical barrier to
creating user accounts in a production tenant for people who do not work
for that organization, but there may be strong business reasons against
doing so. However, creating additional tenants will increase complexity
for admins and users to manage accounts, may also incur additional
expenses for licensing and domain management, and may require additional
process within your organization.

If you expect to use Mesh for Immersive Meeting experiences for users in
your production version of Teams, you will definitely want to provision
your production tenant for Mesh TAP. While you can create other tenants
for testing, people who use Teams throughout the day are highly unlikely
to want to log out of their main Teams account to log into a different
account in a different AAD. A separate tenant is more practical for
standalone worlds, where it's simpler to flip between accounts. Teams
TAP gives you the option of enrolling all your users or a subset of
users in TAP.

Each tenant can have multiple Azure Storage subscriptions, but the Azure
Storage subscription used for Microsoft Mesh must be in the same AAD as
the users who will access storage to upload environments, run events,
and attend events. Access to Azure Storage is controlled by Azure
resource groups.

NOTE: For Mesh TAP, resource groups can be created only in the west
central US region.

## Provide Microsoft with Required Information

Microsoft requires certain information to provision tenants, users, and
subscriptions for pre-release features in Mesh.

To provision your tenant for using custom worlds, you need to tell the
TAP team the tenant name and ID of the tenant where your Azure Storage
subscription is located. You also need to provide the ID for that Azure
Storage Subscription. You should gather this information in advance, to
make sure you know how to access the subscription.

### Tenant ID and Primary Domain FQDN

Before your tenant can be onboarded, you must provide Microsoft with the
unique ID assigned to each Azure Active Directory tenant and the fully
qualified domain name of the primary domain, for example
contosodemo.onmicrosoft.com.

### Who Can Do This?

Any user in the domain can see the tenant ID and FQDN.

### Where

Go to [aad.portal.azure.com](https://aad.portal.azure.com) and look
under Overview

![Screen shot showing the Microsoft Entra Admin Center. In the Basic
Information sectino, it has the name, Tenant ID, and Primary domain
](../../media/preparing-organization-for-mesh/image002.png)

### More Information 

<https://learn.microsoft.com/en-us/partner-center/find-ids-and-domain-names>

## Subscription ID for your Azure Subscription

When you create worlds and upload templates and Unity items, they will
go into Storage in your Azure subscription. Microsoft needs to associate
your Azure subscription ID with the Mesh on the back end.

### Who Can Do This?

The Owner of the Azure Subscription will be able to view the
subscription ID. The Global Administrator does not automatically have
access to all your Azure subscriptions. If the owner of the Azure
subscription is not known, the Global Administrator can elevate access
to all subscriptions. To do that, go to
[aad.portal.azure.com](https://aad.portal.azure.com) and manage the
Properties of the domain.

![Access management for Azure resources -
screenshot](../../media/preparing-organization-for-mesh/image002.png)


### Where

Go to portal.azure.com, open Subscriptions, locate the subscription you
want to use. The subscription ID is displayed in the default column
view.

![Graphical user interface showing Subscriptions UI where you can add,
manage policies, view requests, view eligible subscriptions.
](../../media/preparing-organization-for-mesh/image004.png)

### More Information 

[Elevate access as a global admin](/azure/role-based-access-control/elevate-access-global-admin)

[Role assignments for portal subscription admin](/azure/role-based-access-control/role-assignments-portal-subscription-admin)

## Teams TAP for Mesh

Access to Teams immersive spaces is available only to tenants enrolled
in the Microsoft Teams TAP, which is administered by the Teams team. New
enrollments for companies wanting to use Mesh features in Teams are on
hold. After immersive spaces moves to public preview, public-facing
documentation will provide instructions on how to access it.

Companies that want to join Teams TAP all-up, not just for Mesh, may
apply if the program is currently accepting nominations. All
organizations in TAP must meet activity thresholds to remain in TAP. To
apply, go to <https://aka.ms/JoinTAP100>.

Mesh Avatars in Teams is generally available and does not require
participation in Teams TAP or Mesh TAP. For more information, see [Set
up avatars for Microsoft Teams - Microsoft Teams \| Microsoft
Learn](https://learn.microsoft.com/en-us/microsoftteams/meeting-avatars)

### Contact Owners of Supporting Teams

To complete the steps in the onboarding process, you will need to either
have various rights and permissions or be in contact with people in your
organization who can grant the rights and permissions you will need.
Depending on your company structure and policies, this process can be
time-consuming, so it helps to start the outreach while you are
completing the TAP paperwork. The following section lists organizational
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
<https://admin.microsoft.com/Adminportal/Home#/rbac/directory>. More
specific details about the apps and suggested permissions will be
available in the *All Users Guide for Mesh for Teams* doc, which you
will have access to **after** the paperwork is signed.

#### Teams Feedback Policies

Microsoft relies on feedback from users to make better products. The
Teams administrator can set whether users can send feedback about Teams
to Microsoft. Feedback can be permitted based on Azure Active Directory
group membership. If Teams feedback is disabled, users will not be able
to send feedback about Mesh features built into Teams. We strongly
encourage your org to permit this feedback for Mesh users but consult
your company policies before making any changes. For more information
about managing feedback, see
<https://learn.microsoft.com/en-us/microsoftteams/manage-feedback-policies-in-teams>.

## Office Apps Admin 

Cloud Policy service for Microsoft 365 lets you enforce policy settings
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

For more information about managing feedback, see
<https://learn.microsoft.com/en-us/deployoffice/admincenter/overview-cloud-policy#steps-for-creating-a-policy-configuration>.

## Endpoint Managers

Users accessing Mesh on PCs can use either the web portal or a Windows
app available (but hidden) in the Microsoft Store. You can use your MDM
(mobile device management) solution like Microsoft Intune to deploy the
app and make it show up in the users' Company Portal. If you block
access to the Microsoft Store, you can add it to the Microsoft Store for
Business instead. URLs will be provided in the onboarding documentation
but find out your organization's process for requesting apps to be added
to the Company Portal. For more information about deploying apps with
Microsoft Intune, see
<https://learn.microsoft.com/en-us/mem/intune/apps/store-apps-windows>

## Azure Administrators

Some management of Mesh will happen in the Azure portal, but it will be
limited to resources specific to Mesh. Anyone listed as the Owner of the
Storage subscription you provided when you enrolled will be able to see
the Mesh app after it is installed to your Azure tenant. The owner can
also assign additional access to the subscription. Note that by default
the Global Admin does not have access to subscriptions they do not own,
but you can [elevate access to manage all Azure
subscriptions](https://learn.microsoft.com/en-us/azure/role-based-access-control/elevate-access-global-admin).

The Storage subscription owner should create one or more resource
groups, which will serve as containers for custom Worlds. Owners can
assign additional owner, contributor, or read only access as needed.

- Owner: Allows users to manage all Mesh resources in your resource
    group.

- Contributor: Allows users to see and manage Mesh resources in your
    resource group, create/delete events/spaces, select templates, add
    users, and share events/spaces.

- Read permissions: Allows users to see the resources in the Mesh
    resource group, but not manage or edit them.

[]{#_Work_with_Your .anchor}Make sure you have access to an Owner of the
Storage subscription, so you will be able to get resource groups created
and access assigned as soon as the Mesh app is available to you.

### CLI Tool Installation

To deploy your Mesh Scripting to the cloud, someone with sufficient
rights will need to install the Mesh App Command Line Interface (CLI)
tool. You will need to be an owner of the resource group for the world
you're deploying to or be a contributor on the Azure subscription where
you're deploying.

## Work with Your Security Organization

Before deploying any new app or service, you must consider the security
implications and work closely with your security team to make sure you
comply with all standard security policies. Discuss the following Mesh
requirements in advance with the appropriate Security owners.

### Ensure endpoints can be allowed for Mesh immersive spaces

To ensure the Mesh features work properly, the following endpoints must
be allowed through your firewall or proxy server.

All endpoints need to allow traffic on TCP ports 80 and 443:

- \*.microsoft.com

- \*.meshxp.net

- \*.office.com

- \*.office.net

- js.monitor.azure.com

### Firewall Ports for Mesh immersive spaces

In addition to the endpoints above, Mesh also requires the following
outgoing ports to be opened in your firewall:

- TCP ports 80, 443

- TCP & UDP ports 30,000-31,000

- UDP ports 3478-3481

Mesh traffic will use IP addresses in the AzureCloud service tag.

For more information about service tags, see the Azure service tags
overview.

### Ensure endpoints can be allowed for Mesh avatars for Teams

To ensure avatars for Teams works properly, allow the following
endpoints:

*All endpoints need to allow traffic on TCP ports 80 and 443*:

- \*.microsoft.com

- \*.office.com

- \*.office.net

Follow this link to learn more about how to Set up avatars for Microsoft
Teams.

[Set up avatars for Microsoft Teams](/microsoftteams/meeting-avatars)

### Ensure endpoints can be allowed for the Mesh app

To ensure Mesh works properly, allow the following endpoints.

All endpoints need to allow traffic on TCP ports 80 and 443:

- \*.officeapps.live.com

- \*.microsoft.com

- \*.meshxp.net

- \*.office365.com

- \*.office.com

- \*.office.net

- \*.servicebus.windows.net

### Firewall Ports for the Mesh app

In addition to the endpoints listed above, Mesh also requires the
following outgoing ports to be opened in your firewall:

- TCP ports 80, 443, 8089, and 8989

- TCP & UDP ports 30,000-31,000

- UDP ports 3478-3481

Mesh traffic will use IP addresses in the AzureCloud service tag.

For more information about service tags, see the Azure service tags
overview.

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
see
<https://learn.microsoft.com/en-us/mem/intune/protect/conditional-access-intune-common-ways-use>.

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
Microsoft has published a blog on Avatar etiquette: How Microsoft
employees are using avatars for Microsoft Teams in their meetings. This
doc can help inform materials you might want to share with your users.

### Preparing Users for the Mesh App

Your users have access to the Mesh app for PC on the Windows store, and
the Mesh app for Quest in the Meta store. There are no barriers to any
user installing these apps, whether or not your organization is enrolled
in Mesh TAP, but users can't log into the Mesh app unless they are
logging in as a user in a tenant that has been onboarded for Mesh. After
your organization has been onboarded, users will be able to log into
Mesh but will not be able to create standalone events until granted
permissions in the Azure portal. Users will not be able to see Worlds or
attend events in those worlds unless they have been invited to those
events by the event creator.

#### Quest App

Users can go to the Meta App Lab on PC and "get" the app. The next time
the user logs into Quest, the app will download. Users will have to
authenticate when they start the app, which may involve security
policies like 2-factor authentication on the headset, which may require
additional training for users to understand and perform correctly. As
described above, Quest users can attend standalone Mesh events if
invited. After your tenant is onboarded for Teams immersive spaces,
Quest users can also access all meetings in Teams via headset.

## Summary

Microsoft Mesh offers many powerful features that enhance communication
and collaboration in remote and hybrid workplaces. Because this service
provides experiences that span services, make sure you plan for all
necessary stakeholders to provide input, both those mentioned here and
others specific to your organization. After you are onboarded to the
preview program, you will get access to detailed documentation on
setting up and using all available Mesh features.

## Checklist

The following tasks can be completed prior to your paperwork being
signed:

- Have your legal team review the [Microsoft Teams Pre-Release
    Technologies agreement](https://aka.ms/TAP100ProgramDocument)

- Enroll in the [Microsoft Teams TAP](http://aka.ms/JoinTAP100)

- Verify that the tenant you will use for Mesh is licensed for
    [Microsoft 365 E3 or E5](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?ef_id=f1e78938c11a11837d66ea4d52ed8289:G:s&OCID=AIDcmmwf9kwzdj_SEM_f1e78938c11a11837d66ea4d52ed8289:G:s&lnkd=Bing_O365SMB_Brand&msclkid=f1e78938c11a11837d66ea4d52ed8289)

- Verify that the tenant you will use for Mesh has a [Storage subscription for Azure](#Verify_Your_Licensing)

- Gather the following information:

  - [Azure Active Directory Tenant
        ID](#tenant-id-and-primary-domain-fqdn)

    - [Subscription ID for your Azure Storage
        Subscription](#subscription-id-for-your-azure-subscription)

- Get access to an [account with Teams App Manager
    role](#teams-apps-managers)

- Get your [Teams app policy approved](#teams-app-policy)

  - Allow only approved users access to run Mesh

- [Enable Teams feedback](#teams-feedback-policies) for Mesh users

- [Enable Cloud Policy feedback](#office-apps-admin) for Mesh users

- Coordinate with the endpoint management team to [deploy the Mesh app
    for PC](#endpoint-managers)

- Plan who your [Mesh administrators](#azure-administrators) will be
    in Azure

- Work with your [security or network access team](#_Work_with_Your)
    on the endpoint/firewall configurations.

- Discuss with your Security and Endpoint Management teams the risks and benefits of allowing Quest 2 devices to access your network and whether any changes should be made to [conditional access policies](#_Conditional_Access)

## Next steps with Mesh

> [!div class="nextstepaction"]
> [Get started with Avatars for Teams](https://support.microsoft.com/topic/5384e7b7-30c7-4bcb-8065-0c9e830cc8ad)

> [!div class="nextstepaction"]
> [Register your interest in Mesh TAP](https://aka.ms/JoinMeshTAP)

> [!div class="nextstepaction"]
> [Prepare your organization for Immersive spaces (coming soon)](/microsoftteams/public-preview-doc-updates)