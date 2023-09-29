---
title: Set up Microsoft Mesh
description: Set up Microsoft Mesh with M365.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: Tutorial
keywords: Microsoft Mesh, M365, OCPS, Immersive spaces, Avatars, getting started, documentation, features
---

# Set up Microsoft Mesh

In the Microsoft 365 Apps Admin Center (MAC) admins can enable access to Mesh experiences. This covers access to the following experiences:

- Mesh app on PC
- Mesh app on Quest 2
- Mesh Portal

> [!NOTE]
> All Mesh experiences are enabled via one policy in the Microsoft 365 Admin Center.
> 
> If a user has this policy enabled, they will be able to access all Mesh experiences including the Mesh app on PC, the Mesh app on Quest 2, and the Mesh portal.

To enable access, please visit the M365 Admin Center and enable the policy via the Overview of Cloud Policy services (OCPS).

   > [!div class="nextstepaction"]
   > [M365 Apps Admin Center](https://config.office.com/officeSettings/)


## Prerequisites

To enable Mesh in your managed tenant, you must have one of the following roles in Azure AD:
- Global Administrator
- Security Administrator
- Office Apps Admin

### Licensing requirements

For Microsoft Mesh, you will need the following:

- Teams premium license for Commercial use.

> [!NOTE]
> We don't support tenants with worldwide public sector, EDU, or GCC licenses.

- A pre-requisite license for Teams Premium, as outlined in [Microsoft Teams Premium Licensing - Microsoft Teams | Microsoft Learn](/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

Learn more about [Teams for enterprise](https://www.microsoft.com/en-us/microsoft-teams/enterprise#pricing).

## Enable Mesh in M365 Apps Admin Center

1. Sign into [M365 Apps Admin Center](https://config.office.com/officeSettings/) with your Azure Active Directory account with admin privileges for the Microsoft 365 Admin Center.
    > [!div class="nextstepaction"]
   > [M365 Apps Admin Center](https://config.office.com/officeSettings/)

1. Navigate to the **Customization** > **Policy Management** in the left nav.

    :::image type="content" source="../../media/m365-setup-guide/M365-policy-management.png" alt-text="Customization then policy management window in the M365 Admin Center":::

1. Create or identify an existing policy that applies to the users that should have access to Mesh with the Mesh policy **enabled**. 

    Create a new policy by selecting **+ Create** then name the policy.
1. Adjust the scope for this policy to determine who or what groups can access **all Mesh experiences**.

    To be clear, if this policy is a applied to a user, they will be able to access Mesh on Meta Quest 2, the Mesh app on PC, and the Mesh Portal.

1. In the **Configure Settings** page, search for **Control user access to Microsoft Mesh experiences.** 
    :::image type="content" source="../../media/m365-setup-guide/M365-configure-settings-policy-name.png" alt-text="Policy name for enabling Mesh experiences is Control user access to Microsoft Mesh experiences.":::

1. Select the policy and **Enable** it.
    :::image type="content" source="../../media/m365-setup-guide/OCPS-Enabled-policy.png" alt-text="Mesh access policy enabled":::
1. In the Review and publish page, review the policy that was created then select **Create** to publish.

    :::image type="content" source="../../media/m365-setup-guide/m365-create-policy.png" alt-text="Create policy page in the MAC":::
1. If successful, you should see the Policy configuration show up in the Policy Management page.

    :::image type="content" source="../../media/m365-setup-guide/m365-mesh-policy-enabled-successful.png" alt-text="Policy configuration for Mesh policy is successful created and visible in the Policy Management page":::


## End user dialogue referenced in policy can be seen below

Users will see a new license agreement dialogue in the upcoming release for Mesh products and data gathered from spatial audio. See the image below for more info:

:::image type="content" source="../../media/m365-setup-guide/End-user-license-agreement.png" alt-text="End user license agreement for Mesh and spatial audio.":::

   > [!div class="nextstepaction"]
   > [Set up Mesh Portal (Preview)](setup-mesh-portal.md)
