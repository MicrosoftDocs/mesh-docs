---
title: Configure Microsoft Mesh
description: Configure user access and usage for Microsoft Mesh on PC, Mesh on Quest, or Mesh on the web with M365 for your enterprise.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 06/13/2024
ms.topic: install-set-up-deploy
search.appverid: MET150
audience: admin
keywords: Microsoft Mesh, M365, OCPS, Immersive spaces in Mesh, Mesh experiences, getting started, documentation, features
---

# Configure Microsoft Mesh

This article covers how to setup and deploy the Microsoft Mesh from an IT perspective for the Mesh app on PC, Mesh app on Quest 2, and Mesh on the web. Before setting up Microsoft Mesh, we recommend reading the [Preparing your organization for Mesh](preparing-your-organization.md) to ensure your enterprise is prepared to set up and deploy Mesh. If you're looking to manage the Avatars app or Mesh app in Teams, please refer to [Manage the avatars app in Microsoft Teams](/microsoftteams/meeting-avatars) or [Manage the Mesh app in Microsoft Teams](/microsoftteams/meeting-immersive-spaces).

## Prerequisites

Before deploying  Mesh, ensure that the following endpoints and firewall ports are allowed:

[!INCLUDE [Include file for the immersive spaces in Mesh article](../../Includes/license-requirements-for-Mesh.md)]

For help, see the [immersive spaces in mesh licensing Troubleshooting and FAQs](../../Resources/mesh-troubleshooting.md#what-are-the-license-requirements-for-immersive-spaces-in-mesh).

[!INCLUDE [Include file for the custom immersive spaces ports and firewall requirements in Mesh article](../../Includes/custom-immersive-spaces-ports-firewall.md)]

## Configure access to Mesh using service plans

The Mesh app is by default available to all users in the M365 Admin Center. Admins can block the app for specific users or user groups by turning off the Microsoft Mesh service plan.

This covers access to the following experiences:

- Mesh app on PC
- Mesh app on Quest 2
- Mesh on the web

By default, these Mesh experiences will be available to all users if a service plan or policy does not restrict access. Follow the [Configure access to Mesh using service plans](#configure-access-to-mesh-using-service-plans) or [Configure access to Mesh using policies](#configure-access-to-mesh-using-service-plans) steps below to block specific groups or people.

To configure access to Mesh in your tenant, you must have one of the following roles in Azure Active Directory:

- Global Administrator
- Security Administrator
- Office Apps Admin

> [!IMPORTANT]
> In order to streamline the admin experience, admins will no longer need to configure Mesh in M365 Apps Admin Center. If you had previously restricted Mesh access to users or groups in your organization via the Mesh policy found in the M365 Apps Admin Center, you will need to switch to restricting access via the Mesh service plan instead in the M365 Admin Center (MAC) by the end of February, 2024.

1. Sign into [M365 Admin Center](https://admin.microsoft.com/) with an admin account with at least Global, License, or User level permissions and open the left navigation panel to the Users section.

    :::image type="content" source="../../media/m365-setup-guide/Left-nav-panel.png" alt-text="Screenshot of left nav panel in M365 admin center.":::

1. Select a user or group and select **Licenses and apps** to manage the user's or group's active licenses and service plans.

    :::image type="content" source="../../media/m365-setup-guide/licenses-apps-selection.png" alt-text="Screenshot of licenses and apps section in M365 Admin Center.":::

1. Ensure that you have enabled the appropriate licenses for Microsoft Mesh in order for the service plan to show up in the **Apps** section.

    :::image type="content" source="../../media/m365-setup-guide/Select-appropriate-apps-Microsoft-Mesh.png" alt-text="Screenshot of apps dropdown showing Microsoft Teams Premium.":::

1. Toggle the Microsoft Mesh service plan off to disable Mesh for the selected user or group.

For additional guidance for assigning licenses in M365, see:

[Assign or unassign licenses for users in the Microsoft 365 admin center - Microsoft 365 admin | Microsoft Learn](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide&preserve-view=true)

For more complex and larger group license management, you can do so in Entra ID:

[Assign licenses to a group - Microsoft Entra ID | Microsoft Learn](/entra/identity/users/licensing-groups-assign)

   > [!div class="nextstepaction"]
   > [Manage Environment collections](manage-mesh-on-web.md)
