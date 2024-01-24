---
title: Set up Microsoft Mesh
description: Set up Microsoft Mesh with M365.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: Tutorial
search.appverid: MET150
audience: admin
keywords: Microsoft Mesh, M365, OCPS, Immersive spaces, Avatars, getting started, documentation, features
---

# Configure Microsoft Mesh

> [!IMPORTANT]
> In order to streamline the admin experience, admins will no longer need to configure Mesh in M365 Apps Admin Center. If you had previously restricted Mesh access to users or groups in your organization via the Mesh policy found in the M365 Apps Admin Center, you will need to switch to restricting access via the Mesh service plan instead in the M365 Admin Center (MAC).

The Mesh app is by default available to all users in the M365 Admin Center. Admins can block the app for specific users or user groups by turning off the Microsoft Mesh service plan.

This covers access to the following experiences:

- Mesh app on PC
- Mesh app on Quest 2
- Mesh on the web

By default, these Mesh experiences will be available to all users if a service plan or policy does not restrict access. Follow the [Configure access to Mesh using service plans](#configure-access-to-mesh-using-service-plans) or [Configure access to Mesh using policies](#configure-access-to-mesh-using-policies) steps below to block specific groups or people.

## Prerequisites

To configure access to Mesh in your tenant, you must have one of the following roles in Azure Active Directory:

- Global Administrator
- Security Administrator
- Office Apps Admin

[!INCLUDE [Include file for the immersive spaces in Mesh article](../../Includes/license-requirements-for-Mesh.md)]

For help, see the [immersive spaces in mesh licensing Troubleshooting and FAQs](../../Resources/mesh-troubleshooting.md#what-are-the-license-requirements-for-immersive-spaces-in-mesh).

## Configure access to Mesh using service plans

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

[Assign or unassign licenses for users in the Microsoft 365 admin center - Microsoft 365 admin | Microsoft Learn](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide) 

For more complex and larger group license management, you can do so in Entra ID:

[Assign licenses to a group - Microsoft Entra ID | Microsoft Learn](/entra/identity/users/licensing-groups-assign)

## Configure access to Mesh using policies

> [!IMPORTANT]
> Mesh will be available to all users by default. Create a policy or update an existing one to block specific groups or people.

1. Sign into [M365 Apps Admin Center](https://config.office.com/officeSettings/) with your Azure Active Directory account with admin privileges for the Microsoft 365 Admin Center.
    > [!div class="nextstepaction"]
   > [M365 Apps Admin Center](https://config.office.com/officeSettings/)

1. Navigate to the **Customization** > **Policy Management** in the left nav.

    :::image type="content" source="../../media/m365-setup-guide/M365-policy-management.png" alt-text="Customization then policy management window in the M365 Apps Admin Center":::

1. Create or identify an existing policy for the users or groups of users that you would like to configure Mesh for. For more information on how to apply cloud policies to users and groups, see the [Overview of CLoud Policy service for Microsoft 365](/deployoffice/admincenter/overview-cloud-policy).

    Create a new policy by selecting **+ Create** then name the policy.
1. Adjust the scope for this policy to determine who or what groups can access **all Mesh experiences**.

    To be clear, if this policy is a applied to a user, they will be able to access Mesh on Meta Quest 2, the Mesh app on PC, and Mesh on the web. If you do not configure this policy, users will have access to all three Mesh experiences.

1. In the **Configure Settings** page, search for **Control user access to Microsoft Mesh experiences.**

    :::image type="content" source="../../media/m365-setup-guide/M365-configure-settings-policy-name.png" alt-text="Policy name for enabling Mesh experiences is Control user access to Microsoft Mesh experiences.":::

1. Select the policy and **Enable** or **Disable** it for users or groups of users in your organization.

    :::image type="content" source="../../media/m365-setup-guide/OCPS-Enabled-policy-small.png" alt-text="Mesh access policy enabled" lightbox="../../media/m365-setup-guide/OCPS-Enabled-policy.png":::
1. In the Review and publish page, review the policy that was created then select **Create** to publish.

    :::image type="content" source="../../media/m365-setup-guide/m365-create-policy.png" alt-text="Create policy page in the MAC":::

1. If successful, you should see the Policy configuration show up in the Policy Management page.

    :::image type="content" source="../../media/m365-setup-guide/m365-mesh-policy-enabled-successful.png" alt-text="Policy configuration for Mesh policy is successful created and visible in the Policy Management page":::

## End user dialogue referenced in policy can be seen below

Users will see an End User License Agreement dialogue in the upcoming release for Mesh products and data gathered from spatial audio as seen in the following image:

:::image type="content" source="../../media/m365-setup-guide/EULA-agreemnet-small.png" alt-text="Screenshot of end user license agreement for Mesh and spatial audio." lightbox="../../media/m365-setup-guide/EULA-agreemnet.png":::

   > [!div class="nextstepaction"]
   > [Manage Environment collections](manage-mesh-on-web.md)
