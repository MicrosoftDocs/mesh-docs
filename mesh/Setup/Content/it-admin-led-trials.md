---
title: IT admin-led trials
ms.author: tmilligan
author: typride
manager: tyadams
audience: Admin
ms.date: 02/01/2024
f1.keywords:
- NOCSH
ms.topic: article
ms.service: mesh
search.appverid:
- MET150
description: "Learn how to start a trial with Microsoft Mesh as an admin."
---

# IT admin-led trials for Microsoft Mesh

This article describes how to set up and run an IT Admin-led trial pilot program to deploy Microsoft Mesh in your organization.

## Prerequisites

There are [licensing requirements](../../Resources/mesh-troubleshooting.md#what-are-the-license-requirements-for-immersive-spaces-in-mesh) and [configuration steps](preparing-your-organization.md#preparing-your-organization-for-mesh) needed prior to beginning your Microsoft Mesh trial.

> [!IMPORTANT]
> Once the trial is activated, the six-month trial starts. Please ensure your organization is configured to run Microsoft Mesh prior to activating the trial.

- [Preparing your organization for Microsoft Mesh](preparing-your-organization.md) by assigning the suggested functional roles that may be involved in the rollout of Microsoft Mesh, and consider the various required configuration tasks.
- To use Microsoft Mesh, all users (including developers, event organizers, and event attendees/users) are required to have a M365 Office subscription with access to SharePoint, OneDrive, and M365 Calendar. Ensure your organization has a M365 Business Basic/Standard/Premium, Office 365 E1/E3/E5, or Microsoft 365 E3/E5 subscription and users have licenses assigned.
- Review the [roles needed to start the Microsoft Mesh trial](#roles-needed-to-start-trial-and-assign-licenses) and assign licenses.

### Roles needed to start trial and assign licenses

| **Role**                 | **Description**                                                                                                                                                                                       | **Permissions**                               |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| [Global Administrator](/entra/identity/role-based-access-control/permissions-reference#global-administrator)     | This role has access to all administrative features in Microsoft 365. Global administrators can manage administrative roles and access all administrative features in the Microsoft 365 admin center. | **Activate trial & Assign licenses to users** |
| [Billing Administrator](/entra/identity/role-based-access-control/permissions-reference#billing-administrator)    | This role has access to the billing-related functions in the Microsoft 365 admin center. Billing administrators can make purchases, manage subscriptions, and manage support tickets.                 | **Activate trial**                            |
| [User Administrator](/entra/identity/role-based-access-control/permissions-reference#user-administrator) | This role has access to user management tasks in the Microsoft 365 admin center. User management administrators can create and manage user accounts, reset passwords, and manage user licenses.       | **Assign licenses to users**                  |
| [License Administrator](/entra/identity/role-based-access-control/permissions-reference#license-administrator)    | This role has access to manage subscriptions and licenses for Microsoft 365. License administrators can assign licenses to users, remove licenses, and manage license assignments                     | **Assign licenses to users**                  |

Learn more about [Role based access control | Microsoft Entra](/entra/identity/role-based-access-control/delegate-by-task#licenses).

## Sign up for a trial

This offer is applicable with an active Microsoft 365 or Teams plans for business or enterprise. A Teams Premium license is required upon expiration of the Mesh trial. These IT Admin trials offer customers access to Microsoft Mesh for 6 months.

> [!IMPORTANT]
> In order to access the trial and assign licenses to users, you must have an [adequate role and privileges](#roles-needed-to-start-trial-and-assign-licenses).

> [!NOTE]
> These admin-led trials are not available worldwide. Specifically, they aren't available for Government customers or customers with EDU or FLW SKUs. See the [Mesh Troubleshooting and FAQs](../../Resources/mesh-troubleshooting.md) for full licensing requirements.

There are two entrypoints for the trial that are detailed below:

### Direct link to trial

- Visit the [Microsoft Mesh Trial - Admin link](https://go.microsoft.com/fwlink/?linkid=2258400) from the [Microsoft Mesh Homepage](https://www.microsoft.com/mesh)

    :::image type="content" source="../../media/admin-led-trial/Start-trial-link.png" alt-text="Screenshot of start trial page with Try now highlighted.":::

### Navigate to trial in M365 Admin Center

- Go to the [M365 Admin Center](https://admin.microsoft.com/) and follow the steps below:
    1. Sign in to [https://admin.microsoft.com/](https://admin.microsoft.com/).
    1. Go to **Marketplace** > **Billing** > **Purchase Services**.

        :::image type="content" source="../../media/admin-led-trial/Sign-up-trial-2.png" alt-text="Screenshot of Admin center showing purchase services highlighted.":::

    1. Search for **Microsoft Mesh** or **Purchase services** or scroll down to the **Other Services** section of **Purchase services**.
        > [!NOTE]
        > Based on customer tenant configuration, some customers may be unable to see the Microsoft Mesh trial if searching directly in Microsoft 365 admin center. Following the [Microsoft Mesh trial](https://go.microsoft.com/fwlink/?linkid=2258400) from the [Microsoft Mesh Homepage](https://www.microsoft.com/mesh) will take those customers directly to the trial location.
    1. On the **Microsoft Mesh Trial** title, select **Details**.

        :::image type="content" source="../../media/admin-led-trial/Sign-up-trial-3.png" alt-text="Screenshot of Mesh details button showing highlighted.":::

    1. Select **Start free trial**.

        :::image type="content" source="../../media/admin-led-trial/Sign-up-trial-4.png" alt-text="Screenshot of Start free trial button showing highlighted.":::

    1. Follow the remaining wizard steps to confirm the trial.

    1. Once complete, you should see a confirmation page.

        :::image type="content" source="../../media/admin-led-trial/Trial-redeemed-confirmation.png" alt-text="Screenshot of confirmation page for trial redemption."::: 

> [!IMPORTANT]
> The expiration date appears in the trial subscription details page within the Microsoft 365 admin center. Upon expiration of the trial, the user won't be able to access their content in Microsoft Mesh and will have to reach out to their IT Admin to purchase a paid license for themselves and their business groups.

## Assign licenses to users

Upon redemption of the trial, the **Microsoft Mesh Trial** will show in your **Billing** > **Your products** page.

:::image type="content" source="../../media/admin-led-trial/Microsoft-Mesh-Product.png" alt-text="Screenshot of microsoft Mesh trial product in admin center.":::

Select the **Microsoft Mesh Trial** product and **Assign licenses**.

Once licenses are assigned, users should be able to [download Microsoft Mesh](../../download-mesh-app-tools.md) and [join or host events in Mesh](../../events-guide/events-overview.md).

## During a Trial

It's time to get started with Mesh! Start by [creating your first event](../../events-guide/events-overview.md) and inviting the users you just assigned licenses to!

- **Host Mesh events** in the ready-made immersive spaces or customize your own space by adding visual elements like banners featuring your organization’s logo, videos showcasing your product, or presentation content with the no-code editor.

    :::image type="content" source="../../user-guide/media/Events-customization.gif" alt-text="Event customization gif":::

For more adoption and deployment resources, visit our Mesh Adoption page found at [Mesh Adoption - Home](https://aka.ms/MeshAdoptionPage)

## After the Trial

Based on the outcome of the trial, you can decide whether to proceed to purchase licenses of Teams Premium to access Microsoft Mesh.
To ensure continuity of service, you must purchase the required number of licenses and assign those licenses to users. Trial users who don't have a full license at the end of the trial period won't be able to access any Microsoft Mesh experiences.

If you don't purchase licenses following the trial:

- Users will no longer be able to access Microsoft Mesh.
- Users will continue to have access to the Mesh toolkit in Unity but will be unable to access the Microsoft Mesh application to publish and experience your environments in Mesh.

Give us feedback about your trial experience! Tell us what you think using the feedback form in Microsoft Mesh or using the feedback button below.

## Microsoft Mesh Trial FAQs

### How many licenses come with the Microsoft Mesh trial?

The trial allocates 1,000,000 licenses for users.

### How long does the trial last?

The duration of the trial is six months, starting from the activation date/time.

### What are the subscription and license requirements for Microsoft Mesh?

To use Microsoft Mesh, all users (including developers, event organizers, and event attendees/users) are required to have a M365 Office subscription with access to SharePoint, OneDrive, and M365 Calendar. Ensure your organization has a M365 Business Basic/Standard/Premium, Office 365 E1/E3/E5, or Microsoft 365 E3/E5 subscription and users have licenses assigned.

### What M365 admin roles are necessary for deployment?

Please refer to the table listed above, [Roles needed to start trial and assign licenses](#roles-needed-to-start-trial-and-assign-licenses).

## Troubleshooting

Based on customer tenant configuration, some customers may be unable to see the Microsoft Mesh trial if searching directly in Microsoft 365 admin center. Following the [Microsoft Mesh Trial - Admin link](https://go.microsoft.com/fwlink/?linkid=2258400) from the [Microsoft Mesh Homepage](https://www.microsoft.com/mesh) will take you directly to the trial location.

### Trial link is not working

There are several scenarios where the trial link may not allow you to sign in and start the Mesh trial:

1. **Trial has already been redeemed, it's expired, or it's not supported in your region**

    In this case, the page will say "The offer that you want is unavailable..."

    :::image type="content" source="../../media/admin-led-trial/Trial-redeemed-page.png" alt-text="Page on a browser showing that your Mesh trial is not valid.":::
1. **You have incorrect permissions.**

    In this case, the page will say "Switch to an account that has permission."
1. **You do not have access to Microsoft Entra. Your account must be associated with or managed through Microsoft Entra.**

    In this case, the page may say "Hmm... can't reach that page. The connection was reset."

    To see a list of your role assignments, see the [List Microsoft Entra role assignments - Microsoft Entra ID | Microsoft Learn ](/entra/identity/role-based-access-control/view-assignments).
