---
title: Set up M365 for Mesh
description: Prepare your organization to use M365 for Mesh.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: Tutorial
keywords: Microsoft Mesh, M365, OCPS, Immersive spaces, Avatars, getting started, documentation, features
---

# Set up Microsoft 365 for Mesh

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

Learn how to [Enable Mesh experiences in OCPS](#enable-mesh-apps-in-ocps).

## License requirements for Mesh

The table below covers the Mesh experiences, the licensing required, the default state of the policies for Mesh, and the action required by admins to enable access for their managed organization.


|                         | Mesh on Meta Quest 2        | Mesh app on PC    | Mesh Portal            |
|-------------------------|-----------------------------|-------------------|------------------------|
| **Licensing required**  | Teams Core or Teams Premium | Teams Premium     |Teams Premium           |
| **Default state**       | **OFF** by default          |**OFF** by default | **OFF** by default     |
| **Action required**     | Enable via OCPS             |Enable via OCPS    | Enable via OCPS        |

Learn more about [Microsoft Teams Premium](https://www.microsoft.com/en-us/microsoft-teams/premium)

> [!IMPORTANT]
> Mesh experiences rely on Calendar and Sharepoint. Your M365 license should include these.
## Enable Mesh apps in OCPS

1. Sign into [M365 Apps Admin Center](https://config.office.com/officeSettings/) with your Azure Active Directory account with admin privileges for the Microsoft 365 Admin Center.
    > [!div class="nextstepaction"]
   > [M365 Apps Admin Center](https://config.office.com/officeSettings/)

1. Navigate to the **Customization** > **Policy Management** in the left nav.

    :::image type="content" source="../../media/m365-setup-guide/M365-policy-management.png" alt-text="Customization then policy management window in the M365 Admin Center":::

1. Select **+ Create** and name the policy.
1. Adjust the scope for this policy to determine who or what groups can access **all Mesh experiences**.

    To be clear, if this policy is a applied to a user, they will be able to access Mesh on Meta Quest 2, the Mesh app on PC, and the Mesh Portal.

1. In the **Configure Settings** page, search for **Control user access to Microsoft Mesh experiences.** 
    :::image type="content" source="../../media/m365-setup-guide/M365-configure-settings-policy-name.png" alt-text="Policy name for enabling Mesh experiences is Control user access to Microsoft Mesh experiences.":::

1. Select the policy and **Enable** it.
1. In the Review and publish page, review the policy that was created and select **Create**.

    :::image type="content" source="../../media/m365-setup-guide/m365-create-policy.png" alt-text="Create policy page in the MAC":::
1. If successful, you should see the Policy configuration show up in the Policy Management page.

    :::image type="content" source="../../media/m365-setup-guide/m365-mesh-policy-enabled-successful.png" alt-text="Policy configuration for Mesh policy is successful created and visible in the Policy Management page":::

   > [!div class="nextstepaction"]
   > [Mesh Portal migration guide](m365-migration-guide.md)
