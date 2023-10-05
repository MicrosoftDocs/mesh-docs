---
title: Create worlds and events in Mesh (Preview)
description: Setup Mesh portal.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, Mesh Portal, Immersive spaces, Avatars, getting started, documentation, features
---

# Create worlds and events in Mesh (Preview)

The Mesh portal is where you can create Mesh events, invite co-organizers or attendees, create Mesh worlds to hold your custom environments, and manage your uploaded environments.

:::image type="content" source="../../media/m365-migration-guide/Homepage.png" alt-text="Mesh portal homepage":::

> [!NOTE]
> Azure management of Mesh is solely required for Mesh cloud scripting resources. For more info on Mesh cloud scripting and Azure, see the [set up cloud scripting infrastructure in Azure](setup-cloud-scripting-infrastructure.md).

## Prerequisites

Microsoft 365 Admins should use the M365 Apps Admin Center to enable the Mesh access policy for users to make the Mesh Portal accessible. If the Mesh Portal is not accessible to you, you may need to ask your IT Admin or wait for the policy to be available for your organization.

[See how to set up Mesh experiences in M365](setup-m365-mesh.md).

## Set up Mesh worlds

Mesh worlds are the home for your custom environments that you upload through the Mesh Toolkit Uploader in Unity.

You can assign:

- **Owners**: Can manage membership and change settings for the world.
- **Members**: Can access and manage event templates and use the customization session to customize environments in the Mesh App.

### Create a Mesh world

1. Open the [Mesh Portal](https://portal.mesh.microsoft.com/).
1. In the Home page, select **Worlds** in the left nav.
    :::image type="content" source="../../media/m365-migration-guide/Select-world.png" alt-text="Select worlds in left nav home page":::
1. Select **Create World** in the top right.
1. Fill out the **World name**, **Description**, and add **Owners**, and **Members**.
    - **Owners**: Can manage membership and change settings for the world.
    - **Members**: Can access and manage event templates and use the customization session to customize environments in the Mesh App.
1. Select **Create world**.

Now your Mesh world is created. You can now upload environments from the Mesh Toolkit Uploader to your Mesh world and create events.

## Events

With the transition to M365 and the Mesh Portal, events are handled slightly differently. Now events can be created without being made in a Mesh world. Mesh events will also show up in your Outlook or Teams calendar with a direct link that people can use to join events, making inviting and joining events quicker.

### Create an event

1. Open the [Mesh Portal](https://portal.mesh.microsoft.com/).

1. Log in with your corporate account.

1. In the Home page, select **Events** in the left nav.

    :::image type="content" source="../../media/m365-migration-guide/Select-events.png" alt-text="Events button in Mesh portal":::

1. Select **Create event** at the top right.

1. Add the event name, time duration, description, upload a thumbnail image, and adjust the room capacity settings.

    :::image type="content" source="../../media/m365-migration-guide/Event-details.png" alt-text="Event details page in Mesh portal":::

1. Select **Next** when complete.

1. Choose an environment or select an event template that you may have created before. Select **Next** when finished.

    [Learn more about event templates](../../events-guide/create-template.md)

1. Add your Co-organizers (who will be able to edit the event) and your Attendees (who will be able to join the event) and select **Create event** when finished.

    :::image type="content" source="../../media/m365-migration-guide/Invite-attendees-co-organizers.png" alt-text="Invite page in the Mesh portal":::

Great job! You've now created your event. Co-organizers and invitees will now see the event in their Outlook and Teams calendars.

## Next steps

Now that you've set up Microsoft Mesh, dive in to organize your first Mesh event:

   > [!div class="nextstepaction"]
   > [Organize your event in the Mesh app](../../events-guide/events-overview.md)

If you have skills using Unity, get started building your own custom environments:

   > [!div class="nextstepaction"]
   > [Develop Mesh environments](../../Create/development-overview.md)