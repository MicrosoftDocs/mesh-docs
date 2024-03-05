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

## Getting started

There are a few steps to take before initiating your Microsoft Mesh trial to ensure your organization is set up for Microsoft Mesh:

- Visit the [Preparing your organization for Microsoft Mesh](preparing-your-organization.md) page to accomplish the required tasks and assign the suggested functional roles that may be involved a rollout.

- Complete the prerequisite steps and ensure you have prerequisite licenses, as described in [Guide to set up Microsoft Mesh with M365](setup-m365-mesh.md#prerequisites).

There are [licensing requirements](../../Resources/mesh-troubleshooting.md#what-are-the-license-requirements-for-immersive-spaces-in-mesh) and [configuration steps](preparing-your-organization.md#preparing-your-organization-for-mesh) needed prior to beginning your Microsoft Mesh trial. The trial start date initiates from the date the trial licenses are activated in Microsoft 365 Admin Center so please ensure your organization is configured to run Microsoft Mesh prior to initiating the trial.

## Sign up for a trial

This offer is applicable with an active Microsoft 365 or Teams plan for business or enterprise. A Teams Premium license is required upon expiration of the Mesh trial.

Trials are publicly available from one of the following sources. These IT Admin trials offer customers access to Microsoft Mesh for 6 months.

To sign up for a trial, please visit:

- The [Microsoft Mesh Trial - Admin link](https://go.microsoft.com/fwlink/?linkid=2258400) from the [Microsoft Mesh Homepage](https://www.microsoft.com/mesh)
- The [M365 Admin Center](https://admin.microsoft.com/) and follow the steps below:
    1. Sign in to [https://admin.microsoft.com/](https://admin.microsoft.com/).
    1. Go to **Marketplace** > **Billing** > **Purchase Services**.
    1. Search for **Microsoft Mesh** or **Purchase services** or scroll down to the **Other Services** section of **Purchase services**.
    1. On the **Microsoft Mesh Trial** title, select **Details**.
    1. Select **Start free trial**.
    1. Follow the remaining wizard steps to confirm the trial.

These admin-led trials are not available worldwide. They aren't available for Government customers or customers with EDU or FLW SKUs. See the [Mesh Troubleshooting and FAQs](../../Resources/mesh-troubleshooting.md) for full licensing requirements.

Based on customer tenant configuration, some customers may be unable to see the Microsoft Mesh trial if searching directly in Microsoft 365 admin center. Following the [Microsoft Mesh trial](https://go.microsoft.com/fwlink/?linkid=2258400) from the [Microsoft Mesh Homepage](https://www.microsoft.com/mesh) will take those customers directly to the trial location.

The expiration date appears in the trial subscription details page within the Microsoft 365 admin center. Upon expiration of the trial, the user won't be able to access their content in Microsoft Mesh and will have to reach out to their IT Admin to purchase a paid license for themselves and their business groups.

## Who should be involved in a trial

| **Role**                                                                                    | **Activity**                                                              | **Mesh licensed user** |
|---------------------------------------------------------------------------------------------|---------------------------------------------------------------------------|------------------------|
| Microsoft 365 global administrator (or an admin with Billing and License and/or User roles) | Activate the trial and assign licenses                                    | **Yes**                |
| Mesh Host                                                                                   | Schedule and host Mesh immersive experiences and provide feedback         | **Yes**                |
| Mesh Attendee                                                                               | Attend and participate in Mesh immersive experiences and provide feedback | **Yes**                |

To see a list of your role assignments, see the [List Microsoft Entra role assignments - Microsoft Entra ID | Microsoft Learn ](/entra/identity/role-based-access-control/view-assignments).

## Activate a trial

When you initiate a trial, you need to:

- Ensure your organization is configured to run Microsoft Mesh
- Assign licenses to the relevant users
- Educate organizational stakeholders how to get started hosting Mesh events

For more information on preparing your organization for Microsoft Mesh, please see [Preparing your organization](preparing-your-organization.md)

For more information on setting up Mesh events, please see our Events overview page at [Mesh events overview](../../events-guide/events-overview.md).

## During a Trial

During the Mesh trial, we suggest you evaluate the following:

- Host Mesh events in the ready-made immersive spaces or customize your own space by adding visual elements like banners featuring your organization’s logo, videos showcasing your product, or presentation content with the no-code editor.

- Explore and deploy customized 3D experiences in Microsoft Mesh using the Mesh toolkit available for Unity.

For more adoption and deployment resources, visit our Mesh Adoption page found at [Mesh Adoption - Home](https://aka.ms/MeshAdoptionPage)

For more information on setting up Mesh events, please see our Events overview page at [Mesh events overview](../../events-guide/events-overview.md).

## After a Trial

Based on the outcome of the trial, you can decide whether to proceed to purchase licenses of Teams Premium to access Microsoft Mesh.
To ensure continuity of service, you must purchase the required number of licenses and assign those licenses to users. Trial users who don't have a full license at the end of the trial period won't be able to access any Microsoft Mesh experiences.

If you don't purchase licenses following the trial:

- Users will no longer be able to access Microsoft Mesh.
- Users will continue to have access to the Mesh toolkit in Unity but will be unable to access the Microsoft Mesh application to publish and experience your environments in Mesh.

Give us feedback about your trial experience! Tell us what you think in the feedback below.

## Troubleshooting

Based on customer tenant configuration, some customers may be unable to see the Microsoft Mesh trial if searching directly in Microsoft 365 admin center. Following the [Microsoft Mesh Trial - Admin link](https://go.microsoft.com/fwlink/?linkid=2258400) from the [Microsoft Mesh Homepage](https://www.microsoft.com/mesh) will take you directly to the trial location.

### Trial link is not working

There are several scenarios where the trial link may not allow you to sign in and start the Mesh trial:

1. **Trial has already been redeemed, it's expired, not supported in your region, or you already have access via a Team Premium license or Teams Premium Trial**

    In this case, the page will say "The offer that you want is unavailable..."

    :::image type="content" source="../../media/admin-led-trial/Trial-redeemed-page.png" alt-text="Page on a browser showing that your Mesh trial is not valid.":::
1. **You have incorrect permissions.**

    In this case, the page will say "Switch to an account that has permission."
1. **You do not have access to Microsoft Entra. Your account must be associated with or managed through Microsoft Entra.**

    In this case, the page may say "Hmm... can't reach that page. The connection was reset."

    To see a list of your role assignments, see the [List Microsoft Entra role assignments - Microsoft Entra ID | Microsoft Learn ](/entra/identity/role-based-access-control/view-assignments).
