---
title: Set up cloud scripting infrastructure
description: Set up Azure to manage scripting deployment.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: Tutorial
keywords: Microsoft Mesh, Azure, admin, documentation, features, MeshApp, scripting
---

# Set cloud scripting infrastructure in Azure

## MeshApps cloud infrastructure deployment

Mesh Apps are dotnet based apps that are run in the Cloud. The Mesh Toolkit Uploader helps developers provision their azure resources and deploy their web app. These are the steps involved in deploying the Mesh Apps cloud infrastructure today.

## Resources deployed

The Mesh App Cloud Infrastructure deployed to the Customer's Azure Subscription contains the following Azure resources:
1. **[App Service Plan](/azure/app-service/overview-hosting-plans)**: They represent a compute cluster where web apps can run. (It can also run one or more different web apps).
1. **[Azure VNet](/azure/virtual-network/virtual-networks-overview)**: This is the virtual network resource that the app service instances are deployed in and allows them to communicate with each other.
1. **Azure Web App Instance**: This represents an instance of the Web App running on a specific VM.
1. **[Azure Storage account](/azure/storage/common/storage-account-overview)**: This holds the published content and information about the Azure Web App instances. It is sub-divided into three components:
    1. **[The Mesh App Blob Storage](/azure/storage/blobs/storage-blobs-introduction)**: This holds the Mesh App blob uploaded by the Mesh CLI tool (and in the future from the uploader)
    2. **[The Orleans Membership Table](/dotnet/orleans/overview)**: This holds information about the liveness of the Orleans Silo instances.
1. **[Log Analytics Workspace](/azure/azure-monitor/logs/quick-create-workspace?tabs=azure-portal)**: This holds the logs emitted from the Mesh App running on App Service.
1. **[Application Insights](/azure/azure-monitor/app/app-insights-overview?tabs=net)**: This provides application performance monitoring (APM) features. APM tools are useful to monitor applications from development, through test, and into production.

## MeshApps cloud infrastructure diagram

:::image type="content" source="../../../media/cloud-scripting-infrastructure-guide/image016.png" alt-text="MeshApps infrastructure diagram":::

## Resource provider registrations

The services to register are:

1. Microsoft.Web
1. Microsoft.Storage
1. Microsoft.Network
1. Microsoft.Insights
1. Microsoft.OperationalInsights

**Need help?** See how 

> [!NOTE]
> **Need help?** See how to register services [Resource provider registration errors - Azure Resource Manager | Microsoft Learn](/azure/azure-resource-manager/troubleshooting/error-register-resource-provider?tabs=azure-portal).

> [!NOTE]
> From the Azure docs, registering services is done at a subscription level i.e., there's no need to register the services for different resource groups.

## Access control for MeshApp deployment

1.	Developer must have an email that can be used for their deployment. This could be a new account or a pre-existing email used, such as Environment uploading.
1. If managing access control through an Azure Security Group, create this group (e.g “Mesh App Developers”). 
See Learn about groups and group membership - Microsoft Entra | Microsoft Learn for more Information on Azure Security Group versus Microsoft 365 group types.
1. Decide how you’d like developers to access your Azure subscription. This depends on if the developer is a native member of the directory, or a guest user.
    1. For native members, you can add them to the Azure Security Group you created in the previous step if you’d like to easily manage access controls.
    2. For guest users, you can add them to your Azure subscription, or add them to the Azure Security Group from the previous step.

    See [Add B2B collaboration users in the Azure portal - Microsoft Entra | Microsoft Learn](/azure/active-directory/external-identities/add-users-administrator) for more info on guest users.

### Our recommendations for access control

Depending on how restrictive you'd like your access control policies to be, there are a few recommendations on granting developers access to provision the Mesh Apps cloud infrastructure in Azure.

1.	Grant developers the [Contributor role](/azure/role-based-access-control/built-in-roles) on the entire Subscription that is provisioned for your Mesh Apps.

1. Create a dedicated resource group for Mesh Apps cloud infrastructure deployment and grant developers the Contributor role on this resource group. You can do this through the Azure Security Group you created in the second prerequisite i.e., "Mesh App Developers". This grants them full access to manage all resources but does not allow them to assign roles in Azure RBAC, manage assignments in Azure Blueprints, or share image galleries.

1. Create a [Custom Role in Azure](/azure/role-based-access-control/custom-roles) that has the least permissions needed to create and manage the Mesh Apps cloud infrastructure.

    [You can assign this role directly on the Azure Security Group you created in the second prerequisite i.e](/azure/role-based-access-control/quickstart-assign-role-user-portal)., "Mesh App Developers".

    Below you can see our recommended permissions for the Custom roles you create:
    :::image type="content" source="../../../media/cloud-scripting-infrastructure-guide/image017.png" alt-text="MeshApps infrastructure diagram":::

   **Then the JSON file you would upload should be similar to this**:

    ```dotnetcli
    {
    "id": "88888-8888-8888-888-8888888",
        "properties": {
            "roleName": "MeshAppDeployer",
            "description": "Grants access to Mesh App resources",
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
    > The MeshAppDeployer custom role doesn't allow user to create resource groups. If we want users to create a resource group, they need the **Microsoft.Resources/subscriptions/resourcegroups/write permissions** as well.

## Quota limitations for MeshApps

The Mesh Apps infrastructure utilizes the Premium App Service Linux plan (P1V2), and these are the App Service limits that you might encounter while deploying Mesh Apps:


|Resource |Premium (P1V2)  |
|---------|---------|
|[Web, mobile, or API apps](https://azure.microsoft.com/services/app-service/) per A[zure App Service plan ](/azure/app-service/overview-hosting-plans)  |   Unlimited      |
|[App Service plan](/azure/app-service/overview-hosting-plans)     |   100 per resource group      |

> [!NOTE]
> Apps and storage quotas are per App Service plan unless noted otherwise.

> [!NOTE]
> The actual number of apps that you can host on these machines depends on the activity of the apps, the size of the machine instances, and the corresponding resource utilization.

If you receive this error, “This region has quota of 0 PremiumV2 instances for your subscription. Try selecting a different region or SKU," please refer to [Azure subscription limits and quotas - Azure Resource Manager | Microsoft Learn](/azure/azure-resource-manager/management/azure-subscription-service-limits).

   > [!div class="nextstepaction"]
   > [Getting started with cloud scripting](cloud-scripting-getting-started.md)

   > [!div class="nextstepaction"]
   > [Mesh scripting overview](mesh-scripting-overview.md)
