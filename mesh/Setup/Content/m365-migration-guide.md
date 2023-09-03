---
title: Microsoft 365 migration guide
description: Prepare your organization to adopt Mesh and its features. Organize a team to manage setup and distribution.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, Immersive spaces, Avatars, getting started, documentation, features
---

# Microsoft 365 migration guide

The Microsoft Mesh setup experience is moving from Azure to M365. With this migration, the admin management of Mesh will be done primarily in the Mesh Portal.

This migration should make the admin experience, event management, and event creation more unified and lead to a better experience using Mesh.

For now, we are migrating customers carefully. If you are migrating to M365 from Azure and beginning to use the Mesh Portal, continue reading to see how.

## Mesh Portal

In the Mesh Portal, admins will be able to manage:

- Mesh worlds
- Events
- Environments and templates

:::image type="content" source="../../media/m365-migration-guide/Homepage.png" alt-text="Mesh portal homepage":::

## Prerequisities

In order to use the mesh portal, you should 

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

With the transition to M365 and the Mesh Portal, events are handled slightly differently. Now events can be created without being made in a Mesh world.


## 