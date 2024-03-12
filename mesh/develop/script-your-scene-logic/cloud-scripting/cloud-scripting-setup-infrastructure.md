---
title: Cloud Scripting infrastructure and management
description: Learn about setting up Mesh Cloud Scripting in Azure.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 3/12/2024
ms.topic: Tutorial
keywords: Microsoft Mesh, Azure, admin, Mesh Cloud Scripting, scripting, cloud scripting
---

# Set up Mesh Cloud Scripting in Azure

## Overview

In this article, you'll learn about various aspects of Mesh Clouding infrastructure and management, including the services that get deployed to your Azure Subscription when you build and publish your Cloud Scripting project.

### Resources deployed

Mesh Cloud Scripting Services are .NET-based apps that run in the Cloud. The Mesh Cloud Scripting cloud infrastructure deployed to the customer's Azure Subscription contains the following Azure resources:

1. **[App Service plan](/azure/app-service/overview-hosting-plans)**: Represents a compute cluster where web apps can run. It can also run one or more different web apps.

1. **[Azure VNet](/azure/virtual-network/virtual-networks-overview)**: This is the virtual network resource that the app service instances are deployed in and allows them to communicate with each other.

1. **Azure Web App Instance**: Represents an instance of the web app running on a specific VM.
1. **[Azure Storage account](/azure/storage/common/storage-account-overview)**: Holds the published content and information about the Azure web app instances. It's subdivided into three components:
    1. **[The Mesh Cloud Scripting Service Blob Storage](/azure/storage/blobs/storage-blobs-introduction)**: Holds the Mesh Cloud Scripting Service blob uploaded by the Mesh Uploader.
    2. **[The Orleans Membership Table](/dotnet/orleans/overview)**: Holds information about the liveness of the Orleans Silo instances.
1. **[Log Analytics Workspace](/azure/azure-monitor/logs/quick-create-workspace?tabs=azure-portal)**: Holds the logs emitted from the Mesh Cloud Scripting Service running on App Service.
1. **[Application Insights](/azure/azure-monitor/app/app-insights-overview?tabs=net)**: Provides application performance monitoring (APM) features. APM tools are useful to monitor applications from development, through test, and into production.

#### App Service Plan

An App Service plan defines a set of compute resources that enable a web app to run.

When you create an App Service plan in a certain region (for example, West Europe), a set of compute resources is created for that plan in that region. Whatever apps you put into this App Service plan run on these compute resources as defined by your App Service plan. Each App Service plan defines:

- Operating System (Windows, Linux)
- Region (West US, East US, and so on)
- Number of VM instances
- Size of VM instances (Small, Medium, Large)
- Pricing tier (Free, Shared, Basic, Standard, Premium, PremiumV2, PremiumV3, Isolated, IsolatedV2)

For more info, refer to the [App Service Plan Docs](/azure/app-service/overview-hosting-plans).

**Mesh toolkit default resource settings for App Service Plan**

- **SKU Name**: P1v2
- **SKU Tier**: PremiumV2
- **SKU Capacity**: 1
- **Kind**: Linux
- **Reserved**: True

In the context of Mesh Cloud Scripting Services, the App Service plan is the compute component. It can scale automatically, and handle how the different instances communicate with each other (networking). The CloudHost, which is the application that runs and manages Mesh Cloud Scripting Services, is currently offered as a Docker image and as such, we use a Linux based plan. The Premium plans are more suited for production workloads.

For more information on the defaults, refer to the [Bicep & ARM template reference](/azure/templates/microsoft.web/serverfarms?pivots=deployment-language-bicep) for the App Service plan resource.

#### App Service

Azure App Service is an HTTP-based service for hosting web applications, REST APIs, and mobile back ends. App Service adds the power of Microsoft Azure to your application, such as security, load balancing, autoscaling, and automated management. With App Service, you pay for the Azure compute resources you use. The compute resources you use are determined by the **App Service plan** that you run your apps on.

For more information, refer to the [App Service Docs](/azure/app-service/overview).

**Mesh toolkit default resource settings -  App Service**

- **httpsOnly**: True
- **alwaysOn**: True
- **vnetPrivatePorts Count**: 2
- **vnetRouteAllEnabled**: True
- **vnetName**: Default Virtual Network Name

For more information on the defaults, refer to the [Bicep & ARM template reference](/azure/templates/microsoft.web/sites?pivots=deployment-language-bicep) for the App Service Plan resource.

#### Virtual Network

Azure Virtual Network is the fundamental building block for your private network in Azure. A virtual network enables many types of Azure resources, such as Azure Virtual Machines (VM), to securely communicate with each other, the internet, and on-premises networks. A virtual network is similar to a traditional network that you'd operate in your own data center. An Azure Virtual Network brings with it extra benefits of Azure's infrastructure such as scale, availability, and isolation.

For more information, refer to the [Virtual Network Docs](/azure/virtual-network/virtual-networks-overview).

**Mesh toolkit default resource settings - Virtual Network**

- **AddressSpace addressPrefixes**: 10.0.0.0/16
- **Subnet addressPrefix**: 10.0.0.0/24
- **Subnet Delegations name**: delegation
- **Subnet Delegations serviceName**: Microsoft.Web/serverFarms

For more information on the defaults, refer to the [Bicep & ARM template reference](/azure/templates/Microsoft.Network/virtualNetworks?pivots=deployment-language-bicep) for the Virtual Network resource.

#### Storage Account

An Azure storage account contains all of your Azure Storage data objects: blobs, files, queues, and tables. The storage account provides a unique namespace for your Azure Storage data that's accessible from anywhere in the world over HTTP or HTTPS. Data in your storage account is durable and highly available, secure, and massively scalable.

For more information, refer to the [Storage Account Docs](/azure/storage/common/storage-account-overview).

**Mesh toolkit default resource settings - Storage Account**

- **SKU Name**: Standard_LRS
- **Kind**: StorageV2

For more information on the defaults, refer to the [Bicep & ARM template reference](/azure/templates/microsoft.storage/storageaccounts?pivots=deployment-language-bicep) for the Storage Account resource.

#### Log Analytics Workspace

A Log Analytics workspace is a unique environment for log data from Azure Monitor and other Azure services, such as Microsoft Sentinel and Microsoft Defender for Cloud. It's a tool in the Azure portal that's used to edit and run log queries against data in the Azure Monitor Logs store.

For more information, refer to the [Log Analytics Workspace Docs](/azure/azure-monitor/logs/log-analytics-workspace-overview).

**Mesh toolkit default resource settings - Log Analytics Workspace**

- **forceCmkForQuery**: false
- **retentionInDays**: 30
- **SKU name**: PerGB2018
- **dailyQuotaGb**: 2GB

For more information on the defaults, refer to the [Bicep & ARM template reference](/azure/templates/microsoft.operationalinsights/workspaces?pivots=deployment-language-bicep) for the Workspace resource.

#### Application Insights

Application Insights is an extension of [Azure Monitor](/azure/azure-monitor/overview) and provides application performance monitoring (APM) features. APM tools are useful to monitor applications from development, through test, and into production in the following ways:

Proactively understand how an application is performing.
Reactively review application execution data to determine the cause of an incident.
Along with collecting [metrics](/azure/azure-monitor/app/standard-metrics) and application [telemetry](/azure/azure-monitor/app/data-model-complete) data, which describe application activities and health, you can use Application Insights to collect and store application [trace logging data](/azure/azure-monitor/app/asp-net-trace-logs).

For more information, refer to the [Application Insights Docs](/azure/azure-monitor/app/app-insights-overview?tabs=net).

**Mesh toolkit default resource settings - Application Insights**

- **Kind**: web
- **Request_Source**: rest
- **WorkspaceResourceId**: Default Log Analytics Workspace Id.

For more information on the defaults, refer to the [Bicep & ARM template reference](/azure/templates/microsoft.insights/components?pivots=deployment-language-bicep)
 for the Virtual Network resource.

### Mesh Cloud Scripting Services cloud infrastructure diagram

:::image type="content" source="../../../media/cloud-scripting-infrastructure-guide/image016.png" alt-text="Mesh Cloud Scripting Service infrastructure diagram":::

### Resource provider registrations

The services to register are:

1. Microsoft.Web
1. Microsoft.Storage
1. Microsoft.Network
1. Microsoft.Insights
1. Microsoft.OperationalInsights

**Notes**

- If you need help with errors, see [Resource provider registration errors](/azure/azure-resource-manager/troubleshooting/error-register-resource-provider?tabs=azure-portal).

- As explained in the Azure documentation, registering services is done at a subscription level. In other words, there's no need to register the services for different resource groups.

### Access control for the Mesh Cloud Scripting Service deployment

1. Developers must have an email acccount that can be used for the deployment. This can be a new or pre-existing account.
1. If you're managing access control through an Azure Security Group, create this group (for example, "Mesh Cloud Scripting Services Developers"). For more information on Azure Security Group compared to Microsoft 365 group types, see [Learn about groups and group membership](/entra/fundamentals/concept-learn-about-groups). 
1. Decide how you'd like developers to access your Azure subscription. This is determined by whether the developer is a native member of the directory or a guest user.
    1. You can add native members to the Azure Security Group you created in step #2 above if you'd like to easily manage access controls.
    2. You can add guest users to your Azure subscription or add them to the Azure Security Group (see step #2 above).

    For more information on guest users, see [Add B2B collaboration users in the Azure portal](/azure/active-directory/external-identities/add-users-administrator) .

#### Our recommendations for access control

Here are a few recommendations for how to grant developers access to provision the Mesh Cloud Scripting Services cloud infrastructure in Azure. These vary depending on how restrictive you'd like your access control policies to be.

1. Grant developers the [Contributor role](/azure/role-based-access-control/built-in-roles) on the entire Subscription that's provisioned for your Mesh Cloud Scripting Services.

1. Create a dedicated resource group for Mesh Cloud Scripting Services cloud infrastructure deployment and grant developers the Contributor role in this resource group. You can do this through the Azure Security Group you created in the second prerequisite--in other words, "Mesh Cloud Scripting Services Developers". This grants them full access to manage all resources but doesn't allow them to assign roles in Azure RBAC, manage assignments in Azure Blueprints, or share image galleries.

1. Create a [Custom Role in Azure](/azure/role-based-access-control/custom-roles) that has the least permissions needed to create and manage the Mesh Cloud Scripting Services cloud infrastructure.

    [You can assign this role directly on the Azure Security Group you created in the second prerequisite i.e](/azure/role-based-access-control/quickstart-assign-role-user-portal)., "Mesh Cloud Scripting Services Developers".

    Here are our recommended permissions for the Custom roles you create:

    :::image type="content" source="../../../media/cloud-scripting-infrastructure-guide/image017.png" alt-text="Mesh Cloud Scripting Service infrastructure diagram":::

    The JSON file you would upload should be similar to this**:

    ```dotnetcli
    {
    "id": "88888-8888-8888-888-8888888",
        "properties": {
            "roleName": "MeshCloudScriptingServiceDeployer",
            "description": "Grants access to Mesh Cloud Scripting Services resources",
            "assignableScopes": [
                "/subscriptions/{subscriptionID}"
            ],
            "permissions": [
                {
                    "actions": [
                        "*/read",
                        "Microsoft.Authorization/*/read",
                        "Microsoft.ClassicCompute/virtualMachines/extensions/*",
                        "Microsoft.ClassicStorage/storageAccounts/listKeys/action",
                        "Microsoft.Compute/virtualMachines/extensions/*",
                        "Microsoft.HybridCompute/machines/extensions/write",
                        "Microsoft.Insights/alertRules/*",
                        "Microsoft.Insights/autoscalesettings/*",
                        "Microsoft.Insights/components/*",
                        "Microsoft.Insights/diagnosticSettings/*",
                        "Microsoft.Insights/generateLiveToken/read",
                        "Microsoft.Insights/metricAlerts/*",
                        "Microsoft.Insights/scheduledqueryrules/*",
                        "Microsoft.Insights/topology/read",
                        "Microsoft.Insights/transactions/read",
                        "Microsoft.Insights/webtests/*",
                        "Microsoft.Network/*",
                        "Microsoft.OperationalInsights/*",
                        "Microsoft.OperationsManagement/*",
                        "Microsoft.ResourceHealth/availabilityStatuses/read",
                        "Microsoft.Resources/deployments/*",
                        "Microsoft.Resources/subscriptions/resourcegroups/deployments/*",
                        "Microsoft.Resources/subscriptions/resourceGroups/read",
                        "Microsoft.Storage/storageAccounts/*",
                        "Microsoft.Support/*",
                        "Microsoft.Web/certificates/*",
                        "Microsoft.Web/hostingEnvironments/Join/Action",
                        "Microsoft.Web/listSitesAssignedToHostName/read",
                        "Microsoft.Web/serverFarms/join/action",
                        "Microsoft.Web/serverFarms/*",
                        "Microsoft.Web/sites/*"
                    ],
                    "notActions": [],
                    "dataActions": [],
                    "notDataActions": []
                }
            ]
        }
    }
    ```

    > [!NOTE]
    > The MeshCloudScriptingServiceDeployer custom role doesn't allow users to create resource groups. If we want users to create a resource group, they need the **Microsoft.Resources/subscriptions/resourcegroups/write permissions** as well.

### Quota limitations for Mesh Cloud Scripting Services

The Mesh Cloud Scripting Services infrastructure utilizes the Premium App Service Linux plan (P1V2). These are the App Service limits that you might encounter while deploying Mesh Cloud Scripting Service:

|Resource |Premium (P1V2)  |
|---------|---------|
|[Web, mobile, or API apps](https://azure.microsoft.com/services/app-service/) per [Azure App Service plan](/azure/app-service/overview-hosting-plans)  |   Unlimited      |
|[App Service plan](/azure/app-service/overview-hosting-plans)     |   100 per resource group      |

> [!NOTE]
> Apps and storage quotas are per App Service plan unless noted otherwise.

> [!NOTE]
> The actual number of apps that you can host on these machines depends on the activity of the apps, the size of the machine instances, and the corresponding resource utilization.

If you receive the following error: "This region has quota of 0 PremiumV2 instances for your subscription. Try selecting a different region or SKU," see [Azure subscription limits and quotas](/azure/azure-resource-manager/management/azure-subscription-service-limits).

### Clean up stale Mesh Cloud Scripting services

If you have stale or unused Mesh Cloud Scripting services, follow these steps to find your Mesh Cloud Scripting resources and remove them.

1. Log in to Azure Portal.

1. Navigate to the "All Resources" tab.

    :::image type="content" source="../../../media/cloud-scripting-infrastructure-guide/Stale-cleanup-all-resources.png" alt-text="Select all resources in Azure portal":::

1. On the "All Resources" page:

    a. Select the appropriate Subscription.

    :::image type="content" source="../../../media/cloud-scripting-infrastructure-guide/Stale-cleanup-subscription.png" alt-text="Select subscription in Azure":::

    b. Add a filter with the tag **EnvironmentName**.

    :::image type="content" source="../../../media/cloud-scripting-infrastructure-guide/Stale-cleanup-first-filter.png" alt-text="EnvironmentName filter in azure":::

    c. Find the resources that match the environments you wish to delete.

    :::image type="content" source="../../../media/cloud-scripting-infrastructure-guide/Stale-cleanup-second-filter.png" alt-text="Resource filter in azure":::

1. Clean up the stale Mesh Cloud Scripting services by clicking the ellipsis next to the name of each resource found in step 3C and then clicking Delete in the dropdown. Alternatively, you can use the Azure CLI as described in this [Delete resource](/azure/azure-resource-manager/management/delete-resource-group?tabs=azure-cli#delete-resource) article to delete the resources by name.

## Next steps

   > [!div class="nextstepaction"]
   > [Cloud scripting troubleshooting](./cloud-scripting-troubleshooting.md)
