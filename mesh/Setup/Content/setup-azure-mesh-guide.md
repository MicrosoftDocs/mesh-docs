v

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

:::image type="content" source="../../media/admin-azure-mesh-guide/image002.png" alt-text="Azure portal Tenant ID":::

**More information**

[https://learn.microsoft.com/en-us/partner-center/find-ids-and-domain-names](/partner-center/find-ids-and-domain-names)

### Subscription ID for your Azure storage subscription

When you create worlds and upload environments and Unity items, they will go into your Azure Storage subscription. Microsoft needs to associate your Azure Storage subscription ID with the Mesh on the back end. 

#### Who can do this?

The Owner of the Azure Storage Subscription will be able to view the subscription ID. The Global Administrator does not automatically have access to all your Azure subscriptions. If the owner of the Storage subscription is not known, the Global Administrator can elevate access to all subscriptions. To do that, go to [aad.portal.azure](https://aad.portal.azure.com).com and manage the Properties of the domain.

:::image type="content" source="../../media/admin-azure-mesh-guide/image003.png" alt-text="Storage ID":::

#### Where?

Go to portal.azure.com, open Subscriptions, locate the subscription you want to use. The subscription ID is displayed in the default column view.

:::image type="content" source="../../media/admin-azure-mesh-guide/image004.png" alt-text="Storage ID location in Azure":::

**More information**

- [Elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin)

- [Assign a user as an administrator of an Azure subscription](/azure/role-based-access-control/role-assignments-portal-subscription-admin)

## Azure portal setup

Azure portal is the main hub for Mesh world creation and management, and identity access management (IAM).

### Resource group & Storage account selection for Mesh worlds

For creating Mesh world resources, you must use a **Resource group** and **Storage account** in the West US Central region. Otherwise, you will not be able to create Mesh worlds.

### Provision tenant

To begin using Mesh, an IT admin or Azure Admin will need to provision an Azure Active Directory Tenant or use an existing tenant then **provide your tenant ID and subscription ID to Microsoft partner managers**.

**Share the following information with your Microsoft partner managers:**

- **Tenant ID** – Microsoft Partners with enable access to Mesh Resources.
- **Subscription ID** – To access Mesh world resources.

**Having issues?**

Please ensure that the storage account and resource group does not have any security measures or policies that may restrict the creation and use of Mesh world resources.

We recommend you try creating a resource group without any tags in the West Central US region:

``
az group create --name meshVerificationResourceGroup --location westcentralus
``

Then deploy a template that creates a storage account in the West Central US region.

This should help avoid some issues or errors.

## Creating Mesh worlds in the Azure portal

Azure portal is the place to create and manage Mesh worlds. Within each Mesh world, you can add custom environments that have been uploaded from the Mesh Toolkit Uploader and add them to events for access through the Mesh standalone app or Mesh for Quest 2.

[Link to Azure portal (Preview)](https://portal.azure.com/?microsoft_azure_metaverseExtension_assettypeoptions=%7B%22metaverse%22%3A%7B%22options%22%3A%22%22%7D%7D&microsoft_azure_metaverseExtension=true&feature.canmodifyextensions=true#home)

### Create a Mesh world in Azure portal



> [!IMPORTANT]
> Ensure that you’re logged into the account under the tenant that was shared with Microsoft for use with Mesh.
> [!IMPORTANT]
> Ensure that the Azure portal says Microsoft Azure (Preview).

1. Use this Azure portal (Preview) Link and log in with the email address associated with your tenant.

    [Link to Azure portal (Preview)](https://portal.azure.com/?microsoft_azure_metaverseExtension_assettypeoptions=%7B%22metaverse%22%3A%7B%22options%22%3A%22%22%7D%7D&microsoft_azure_metaverseExtension=true&feature.canmodifyextensions=true#home)

1. Type Mesh worlds into the search bar and then select Mesh worlds in the dropdown list. Or select Mesh worlds in the available resources list at the top of the Azure portal Home.
1. Click **Create**.
    :::image type="content" source="../../media/admin-azure-mesh-guide/image005.png" alt-text="Create":::
1. Select your Subscription.
    > [!IMPORTANT]
    > Ensure that you’ve selected a subscription that has been shared with Microsoft for use with Mesh.
1. Select your Resource Group or press Create New.
1. Select your Region.
1. Enter a Resource Name. This is the identifier for the resource in Azure.
1. Note: Resource name must be alphanumeric (letters & numbers), 1-30 characters long, no spaces.
1. Enter the Display Name. This is the name that will be shown in the Mesh Browser.
1. Enter a Description.
1. Press Review + Create.
    :::image type="content" source="../../media/admin-azure-mesh-guide/image006.png" alt-text="Next: Review and Create":::
1. Review and confirm details.
1. Press **Create**.

    Wait around two minutes while deployment is in progress.
    :::image type="content" source="../../media/admin-azure-mesh-guide/image007.png" alt-text="Next: Review and Create":::
1. Select **Go to resource**.
    :::image type="content" source="../../media/admin-azure-mesh-guide/image008.png" alt-text="Go to resource":::
1. Click Mesh world Images on the left-side menu. 
1. Upload a Mesh world icon image and Mesh world background image. Click Save.
1. Note that the Mesh world Icon is the one that shows up on the left-side bar in the Mesh Dashboard.
    :::image type="content" source="../../media/admin-azure-mesh-guide/image009.png" alt-text="Mesh world location ":::

#### Issues with world creation?

See the troubleshooting section for help with world creation errors. (HEADERLINK)

## Identity and Access Management (IAM)

First, it’s important to understand the difference between Azure access and Mesh access.

### Azure Access control

Azure has typical IAM controls that you may be familiar with. You can assign owner, contributor, or read only privileges at any level of the resource management tree.

**Access to Azure portal (Azure portal users)**


|Permissions granted  | Example users  |
|---------|---------|
|Resource management (Create/edit Mesh worlds, events, etc.)    |   IT admins, Mesh world managers      |



### Mesh access control

For general access to Mesh worlds for Mesh users, you only must add them to an Event for the Mesh world to show up in Mesh experiences.

> [!NOTE]
> Any users you want to provide access to will need to be within your tenant.

**Access to Mesh (Mesh users)**

|Permissions granted  | Example users  |
|---------|---------|
|Join Mesh experiences at Mesh endpoints (Mesh browser, Mesh on Quest, etc.). Granted per event.   |   Mesh users     |

### Content contributors

At the Mesh world resource level, you can assign the Content contributor role. The Content contributor role allows someone to do two things: **upload custom environments to Mesh worlds** and/or **be an event producer**.

This means, for each Mesh world, you should add the AAD accounts of Technical Artists or Event Producers as content contributors.

**Content contributor access (Technical 3D artist/Event Producers)**


|Permissions granted  | Example users  |
|---------|---------|
|Upload custom environments for Mesh world(s). Granted per Mesh world.     | Technical 3D artists       |
|Create, manage, or customize events. Granted per Mesh world.    |  Event producers       |

### Access management overview schamatic

The graphic below illustrates the Azure access management schema with typical roles and role permissions enumerated.

:::image type="content" source="../../media/admin-azure-mesh-guide/image010.png" alt-text="IAM overview schematic":::

### Access for an Event

In general, you should use the in-experience controls to create and manage events. See the [Mesh event production guide](../../Use/mesh-events-guide.md) to learn more.

The two access policies you can apply are People and Groups, or Tenant wide, as detailed here:

:::image type="content" source="../../media/admin-azure-mesh-guide/image011.png" alt-text="Event access schematic":::

## Azure resource group access control

Access in Azure is hierarchical, meaning if a user has access to a resource group, they will have access to all resources nested within that resource group. Among other access policies that are typical to Azure, there are three major roles that you can assign as the Azure portal admin at the resource group level:

1. **Owner.** Allows users to manage all resources (Mesh worlds) in your resource group.
1. **Contributor.** Allows users to see and manage resources (Mesh worlds) in your resource group, create/delete events, select environments, add users, and share events.
1. **Read permissions.** Allows users to see the resources in the resource group (Mesh worlds in the resource group), but not manage or edit them.

### Managing Access control for a resource group
To manage access for a resource group, go to the resource group in Azure portal, select Access control (IAM), then click Add.

:::image type="content" source="../../media/admin-azure-mesh-guide/image012.png" alt-text="Event access schematic":::

### Managing Access control for a specific resource (Mesh world)

To enable a user to manage specific Mesh worlds, you should assign them to the Mesh world that you want them to manage. There are two major forms of access you can manage at the Mesh world resource level.

1.Access controls: Allows control over the Mesh world that they have access to based on the permissions set: Owner, contributor, or Read.

1. Content contributor. Allows users to upload through the Mesh Toolkit Uploader to Mesh worlds they have access to or be an Event Producer.
    :::image type="content" source="../../media/admin-azure-mesh-guide/image013.png" alt-text="Event access schematic":::

### Content contributors

Content contributor privileges are assigned at the Mesh world level. A user with Content contributor privileges will be able to:

- Upload environments
- Create, manage, or customize events in Mesh
- Deploy a MeshApp using the Mesh scripting guide

#### How to add a Content contributor

To upload to a specific Mesh world from the Mesh Toolkit Uploader, deploy a MeshApp in Unity, or have Event Producer privileges, the user must be added as a Content contributor for this Mesh world. This is done in the Mesh worlds resource page in the **Content contributor** section.

:::image type="content" source="../../media/admin-azure-mesh-guide/image014.png" alt-text="Event access schematic":::

#### Content contributors working on MeshApp deployment

Content contributors will need a subscription ID and resource group when deploying MeshApps within Unity using the Mesh Toolkit.

Now, a user with Content contributor privileges will be able to create, manage, or customize events in Mesh, and use the Mesh Toolkit Uploader to upload environment to each Mesh world they are a Content contributor in.

For more detail, see the MeshApp Infrastructure section. (HEADERLINK)

### Mesh users

Normal Mesh users without any extra permissions just need to be added to a specific Event using the access controls in the Azure portal for that event. By doing this, the Mesh user will see that Event show up in the Microsoft Mesh apps.

:::image type="content" source="../../media/admin-azure-mesh-guide/image015.png" alt-text="Event access schematic":::

## Common IAM scenarios for Mesh

### Giving Azure access to a Mesh world

#### User needs to create a Mesh world

|Action  | Description  |
|---------|---------|
|*Go to resource group** > **Access control** > **Add user as Owner or Contributor*    |  Add the user to a resource group, which in effect gives them permission to use a subscription. The person adding others to resource groups needs to be an admin for the whole tenant.       |

#### User needs access to a specific Mesh world in Azure portal

|Action  | Description  |
|---------|---------|
|*Go to a specific Mesh world > Access control > Add user as Owner or Contributor*    |  Add the user in the Access control tab for the specific Mesh world. The Owner role allows for full management, including edits to the Mesh world Access policy. The Contributor role allows for management of events, excluding edits of the Mesh world Access control.      |

### Giving Azure access to edit events

#### User needs to create events/spaces for all Mesh worlds in resource group

|Action  | Description  |
|---------|---------|
|*Go to resource group > Access control > Add the user > choose role (Owner/Contributor)*   |  Add the user in the Access control tab for the specific Mesh world. The Owner role allows for full management, including edits to the Mesh world Access policy. The Contributor role allows for management of events, excluding edits of the Mesh world Access control.      |

#### User needs to create events for specific Mesh world(s)

|Action  | Description  |
|---------|---------|
|*Go to resource > Access control > Add the user > choose role (Owner/contributor)*   |  Add the user at the resource level i.e., a specific Mesh world. This will enable them to create events and invite users for a specific Mesh world.      |

### Giving Event Producer privileges to create, manage, or customize events

#### User needs to create, manage, and customize events in Mesh (collaboration session)

|Action  | 
|---------|
|*Go to the Mesh world you want a user to be able to upload to> in left nav, select Content contributors > Add Identities*   |

### Giving access to upload environments from the Mesh toolkit uploader

#### User needs to upload but not see or manage worlds in Azure

|Action  | 
|---------|
|*Go to the Mesh world you want a user to be able to upload to> in left nav, select Content contributors > Add Identities*   |

### Giving access to upload environments from the Mesh toolkit uploader or deploy MeshApps

#### User needs to upload but not see or manage worlds in Azure

|Action  | 
|---------|
|*Go to the Mesh world you want a user to be able to upload to> in left nav, select Content contributors > Add Identities*   |

## MeshApps cloud infrastucture deployment

Mesh Apps are dotnet based apps that are run in the Cloud. The Mesh Toolkit Uploader helps developers provision their azure resources and deploy their web app. These are the steps involved in deploying the Mesh Apps cloud infrastructure today.

To learn about MeshApps cloud infrastructure deployment, see the [Set cloud scripting infrastructure in Azure](setup-cloud-scripting-infrastructure.md) article.


## Troubleshooting Azure set up

### World creation errors

#### Consider any Azure policies that may affect Mesh world creation

Azure configurations are unique to each corporate environment. As such, there may be Azure policies that affect deployment and provisioning of Mesh worlds.

**For reference, Mesh must be able to create:**

- Resources or resource groups are required to contain certain tags
- Storage account creation is controllable via that Multi-region storage account toggle when creating a Mesh world. These regions are West Central US, East Asia or UK West.
- Storage account replication across regions is not allowed


#### How to diagnose the cause a world deployment failure

1. When you receive an error upon deployment, it may be hard to read and take action from it:
    :::image type="content" source="../../media/admin-azure-mesh-guide/image038.jpg" alt-text="world deployment error":::
1. In the **Status** column, select **Error details**.
    :::image type="content" source="../../media/admin-azure-mesh-guide/image039.png" alt-text="world deployment error":::
1. By doing this, you should see the **Errors** > **Summary** page open:\
    :::image type="content" source="../../media/admin-azure-mesh-guide/image040.png" alt-text="world deployment error":::
1. Alternatively, in the **Operation details** column, select **Operation details** to see the Status message. You may need to scroll down to see the Error message:
    :::image type="content" source="../../media/admin-azure-mesh-guide/image041.jpg" alt-text="world deployment error":::

    **Fix deployment failure**

1. In this example of deployment failure, the cause of the failure is that there’s a policy called "Storage accounts should disable public network access" which conflicts with the current storage account creation. Talk to your Azure policy administrators about any policies that are blocking Mesh world deployment and see if you can negotiate a policy that satisfies everyone's requirements.  As an option, you can ask for an additional "sandbox" subscription to be provisioned for Mesh, or even create a separate test tenant with less restrictive policies to do initial testing.

**Further detail on deployment failures**

See the [Find error codes - Azure Resource Manager | Microsoft Learn](/azure/azure-resource-manager/troubleshooting/find-error-code?tabs=azure-portal) guide to diagnose deployment failures deeper.

### Multi-region storage when creating Mesh world

**Multi-region storage for a Mesh world**. In some cases, toggling Multi-region storage to ON for a Mesh world can create some delay or bugginess when the world is created due to complexities of this configuration.

- What does multi-region storage toggle do?

    **Multi-region storage > OFF** : 1 storage account is created in the West Central US.

    **Multi-region storage > ON** : 3 storage accounts are created in West Central US, UK West, and East Asia (as stated in the UI tooltip in Azure portal).

- Solutions

    *Potential solution*: In general, it’s best to wait at least 15 minutes between creating Mesh world to ensure that all deployment is properly propagated between services. In theory, the deployment should be relatively instantaneous, but try waiting a bit after creating a new Mesh world before testing to see if that helps.

    *Potential solution*: Try creating a new Mesh world and toggle the Multi-region storage to **OFF**.

### World creation fails after attempting all above troubleshooting steps

If world creation still fails and there isn't enough information in the operation details try this: 
In the same tenant, create an empty, tagless resource group in the West Central US region by running this command in Azure CloudShell (Bash) to see which policies were responsible and work with your Azure admins to see if you can find a resolution.


```dotnetcli
az group create --name meshVerificationResourceGroup --location westcentralus
```

If you have multiple subscriptions in the same tenant, you can set the subscription you want with the above command:

```dotnetcli
az account set --subscription [subId]
```


**World creation succeeds with tagless group, but world provisioning still fails?**

Please use the Microsoft Teams channel for Mesh Early Adopters Onboarding and report the correlation ID for the failed world creation attempt.