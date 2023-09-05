---
title: Mesh Portal migration guide
description: Prepare your organization to adopt Mesh and its features. Organize a team to manage setup and distribution.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, Mesh Portal, Immersive spaces, Avatars, getting started, documentation, features
---

# Mesh Portal migration guide

The Microsoft Mesh setup experience is moving from Azure to M365. With this migration, the admin management of Mesh will be done primarily in the Mesh Portal.

This migration should make the admin experience, event management, and event creation more unified and lead to a better experience using Mesh.

> [!IMPORTANT]
> For now, select customers can migrate to M365 and onboard to the Mesh Portal. If you are migrating to M365 from Azure and beginning to use the Mesh Portal, continue reading to see how.

> [!NOTE]
> Azure management of Mesh is being removed with the exception of Mesh scripting resources. For more info on Mesh scripting and Azure, see the [Set up cloud scripting infrastructure in Azure](setup-cloud-scripting-infrastructure.md).

## Mesh Portal

In the Mesh Portal, admins will be able to manage:

- Mesh worlds
- Events
- Environments and templates

:::image type="content" source="../../media/m365-migration-guide/Homepage.png" alt-text="Mesh portal homepage":::

## Migrating notes

As we are moving to Microsoft M365, there will be a need to:

- Recreate all Mesh worlds
- Recreate all Events
- Reupload all environments

We are excited to move to M365 and appreciate your patience in this process.

## Mesh worlds

Mesh worlds are the home for your custom environments that you upload through the Mesh Toolkit Uploader in Unity.

You can assign:
- **Owners**: Can manage membership and change settings for the world.
- **Members**: Can access and manage event templates and use the collaboration session to customize environments in the Mesh App.

### Migrating worlds

You may have made Mesh world(s) previously using the Azure portal. In this case, you should create the Mesh world(s) again and reupload your environments to the Mesh world(s) using the Mesh Toolkit uploader.

### Create a Mesh world

1. Open the [Mesh Portal](https://portal-selfhost.mesh.microsoft.com/).
1. In the Home page, select **Worlds** in the left nav.
    :::image type="content" source="../../media/m365-migration-guide/Select-world.png" alt-text="Select worlds in left nav home page":::
1. Select **Create World** in the top right.
1. Fill out the **World name**, **Description**, and add **Owners**, and **Members**.
    - **Owners**: Can manage membership and change settings for the world.
    - **Members**: Can access and manage event templates and use the collaboration session to customize environments in the Mesh App.
1. Select **Create world**.

Now your Mesh world is created. You can now upload environments from the Mesh Toolkit Uploader to your Mesh world and create events.

## Events

With the transition to M365 and the Mesh Portal, events are handled slightly differently. Now events can be created without being made in a Mesh world. Mesh events will also show up in your Outlook or Teams calendar with a direct link that people can use to join events, making inviting and joining events quicker.

### Create an event

1. Open the [Mesh Portal](https://portal-selfhost.mesh.microsoft.com/).
1. Log in with your corporate account.
1. In the Home page, select **Events** in the left nav.
    :::image type="content" source="../../media/m365-migration-guide/Select-events.png" alt-text="Events button in Mesh portal":::
1. Select **Create event** at the top right.
1. Add the event name, time duration, description, upload a thumbnail image, and adjust the room capacity settings.
    :::image type="content" source="../../media/m365-migration-guide/Event-details.png" alt-text="Event details page in Mesh portal":::
1. Select **Next** when complete.
1. Choose an environment or select an event template that you may have created before. Select **Next** when finished.

    [Learn more about Event templates](../../Use/events-guide/customize-event.md#event-templates)

1. Add your Co-organizers (who will be able to edit the event) and your Attendees (who will be able to join the event) and select **Create event** when finished.
    :::image type="content" source="../../media/m365-migration-guide/Invite-attendees-co-organizers.png" alt-text="Invite page in the Mesh portal":::

Great job! You've now created your event. Co-organizers and invitees will now see the event in their Outlook and Teams calendars.

> [!NOTE]
> Please ensure that all participants have updated their Mesh app to the most recent version to ensure that they can use the link in their calendar invite and join the event you just created!
