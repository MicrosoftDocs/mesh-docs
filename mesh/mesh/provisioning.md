---
title: Set up Microsoft Mesh (Preview) for your organization
description: How to set up Microsoft Mesh (Preview) for your organization
ms.prod: mixed-reality
author: anatarnousk
ms.author: antarnou
ms.date: 3/1/2021
ms.topic: article
keywords: mixed reality, getting started, documentation, guides, features, holograms
---
# Set up Microsoft Mesh (Preview) for your organization

To sign in to Mesh-enabled apps for work with your Azure Active Directory (Azure AD) identity, the Mesh service needs to have the required permissions to be used in your organization. How this happens depends on how your organization has set up user consent settings for services like Mesh.

For more information about configuring user consent, see [Configure how end-users consent to applications](/azure/active-directory/manage-apps/configure-user-consent).

## If user consent is enabled

If your organization lets a user grant an application permissions to access your organization's data, you will be able to sign in with your Azure AD account and start using Mesh. The first time you sign in, you will need to grant the app permissions to access your data and accept the Microsoft Mesh Terms of Service and Privacy agreements.

<img src=./media/mesh-consent-dialog.png alt="UI to grant permissions to apps" width="350">

> _UI to grant permissions for Mesh and Mesh App on HoloLens_

## If user consent is disabled

If your tenant administrator has disabled user consent to apps, they will need to follow the instructions below to manually provision the Mesh service and Mesh-enabled experiences such as [Mesh App on HoloLens](../mesh-app/index.md), to be used in your tenant.

### Mesh App on HoloLens (Preview)

To manually enable Microsoft Mesh (Preview) and Mesh App on HoloLens in your organization:

- Install the [AzureAD PowerShell module](https://www.powershellgallery.com/packages/AzureAD).

    ```powershell
    Install-Module -Name AzureAD
    ```

- Run these commands as a tenant or application admin.

    ```powershell
    # Replace your-tenant-id with your tenant ID.
    Connect-AzureAD -TenantId 'your-tenant-id'
    # Mesh
    New-AzureADServicePrincipal -AppId '98e6160b-4308-432a-b82d-ed6fce38dfbf'
    # Mesh App on HoloLens
    New-AzureADServicePrincipal -AppId '63b8670b-4b03-4c76-8e4f-0e2fb4be6a63'
    ```

- After running these PowerShell commands, the tenant admin needs to visit the following URLs to provide tenant-wide consent to the app:
  - [Authorize Microsoft Mesh (Preview)](https://login.microsoftonline.com/common/oauth2/authorize?client_id=98e6160b-4308-432a-b82d-ed6fce38dfbf&response_type=code&prompt=admin_consent)
  - [Authorize Microsoft Mesh App on HoloLens (Preview)](https://login.microsoftonline.com/common/oauth2/authorize?client_id=63b8670b-4b03-4c76-8e4f-0e2fb4be6a63&response_type=code&prompt=admin_consent)
