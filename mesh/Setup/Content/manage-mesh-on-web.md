---
title: Manage Mesh collections
description: Manage Mesh on the web and create collections to hold custom environments made in Unity.
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, Mesh on the web, Immersive spaces, Avatars, getting started, documentation, features
---

# Manage Mesh collections

Use Mesh on the web to create events, invite co-organizers or attendees, manage environments and templates, and create collections to hold custom environments. For any custom environments to be uploaded using the Mesh toolkit in Unity, you'll need a collection to hold your uploads, making them accessible to any event organizer in your organization.

:::image type="content" source="../../media/mesh-on-web/Mesh-on-the-we-home-page.png" alt-text="Screenshot of Mesh on the web home page.":::

To provide context, Mesh on the web has the following pages:

- **Home:** See upcoming events and access some useful articles.
- **Events:** [Create or manage events](../../events-guide/create-event-mesh-portal.md) that are joined view the Microsoft Mesh application.
- **Environments:** View and manage the environments that are available from Microsoft or view the environments and Templates that were uploaded to your collections.

    Learn more about [how to create custom environments for Mesh](../../develop/development-overview.md).

- **Collections:** View, manage, and [create collections](#create-a-collection) to hold custom environments and templates.

## Prerequisites

Microsoft 365 Admins should use the M365 Apps Admin Center to ensure that Mesh is properly setup and access  to Mesh is allowed. If Mesh on the web is not accessible to you, you may need to ask your IT Admin or wait for the policy to be available for your organization.

Learn more about [how to set up Mesh experiences in M365](setup-m365-mesh.md).

## Overview of Collections

Collections are the home for your custom environments that are developed in Unity and uploaded using the Mesh toolkit uploader, as well as a place to review [Templates that you create](../../events-guide/create-template.md) to be reused in events.

Before you can [upload custom environments](../../develop/make-your-environment-available/build-and-publish-your-environment.md) and [create templates](../../events-guide/create-template.md), you'll need to create a Collection to hold them.

## Create a Collection

1. Open Mesh on the web at [https://portal.mesh.microsoft.com/](https://portal.mesh.microsoft.com/) or [https://mesh.cloud.microsoft/](https://mesh.cloud.microsoft/).

    > [!NOTE]
    > Mesh on the web is moving to cloud.microsoft [with all Microsoft 365 apps and services](https://techcommunity.microsoft.com/t5/microsoft-365-blog/introducing-cloud-microsoft-a-unified-domain-for-microsoft-365/ba-p/3804961). To help ease this transition, we are providing two links for Mesh on the web. To use the new cloud.microsoft endpoint, ensure you have allowed the proper endpoints allowed, as detailed in the [Preparing your organization article](preparing-your-organization.md#ensure-endpoints-can-be-allowed-for-immersive-spaces-in-teams).
    >
    > If you have any issues with the new Mesh on the web experience, you can continue to use *portal.mesh.microsoft.com*.

1. In the Home page, select **Collections** in the left nav.

    :::image type="content" source="../../media/mesh-on-web/Select-collections-mesh-on-web.png" alt-text="Screenshot of Mesh on the web showing collection button highlighted.":::

1. Select **Create collection** in the top right.
1. Fill out the **Collection name**, **Description**, adjust the **Sensitivity** and **Privacy**.

    :::image type="content" source="../../media/mesh-on-web/Enter-collection-details-and-select-sensitivity.png" alt-text="Screenshot of Mesh on the web showing collection details filled out.":::

    Learn more about [M365 group public and private settings](https://support.microsoft.com/en-us/office/make-microsoft-365-groups-public-or-private-c0a991b3-9c56-48b8-bf0f-05530f836b1b).

1. Add **Owners**, and **Members**.
    - **Owners**: Can change membership and settings for a collection.
    - **Members**: Can access and edit templates and upload environments in a collection.

    :::image type="content" source="../../media/mesh-on-web/Enter-collection-owners-members.png" alt-text="Screenshot of Mesh on web showing Owners and members filled out.":::

1. Select **Create collection**.

Now your Collection is created, you can now upload environments from the Mesh toolkit Uploader to your Collection and create events.

> [!NOTE]
> It can take up to 15 minutes for storage set up and you can upload environments and templates.

## Manage collection details

Select a collection to see the collection details for **Environments**, **Members**, and **Settings**.

:::image type="content" source="../../media/mesh-on-web/Collection-details-highlighted.png" alt-text="Screenshot of Mesh on the web showing a collection highlighted with Environments, Members.":::

### Manage environments and templates

In the Environments tab, you can see custom environments that were uploaded, and environments that have been used to create templates.

:::image type="content" source="../../media/mesh-on-web/Collection-environment-tab-selected.png" alt-text="Screenshot of Mesh on the web showing Environment tab selected.":::

## Next steps

Now that you've set up Microsoft Mesh, dive in to organize your first Mesh event:

   > [!div class="nextstepaction"]
   > [Organize your event in the Mesh app](../../events-guide/events-overview.md)

If you have skills using Unity, get started building your own custom environment for your new Collection:

   > [!div class="nextstepaction"]
   > [Develop Mesh environments](../../develop/development-overview.md)