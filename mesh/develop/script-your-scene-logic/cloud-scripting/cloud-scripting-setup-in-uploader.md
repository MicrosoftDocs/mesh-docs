---
title: Cloud scripting setup in the Mesh Uploader
description: Learn about the settings needed in the Mesh Uploader for Cloud Scripting.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 2/28/2024
ms.topic: Guide
keywords: Microsoft Mesh, scripting, cloud scripting, visual scripting, coding
---

# Cloud scripting setup in the Mesh Uploader

Mesh Scripting setup information

When you use Mesh Cloud Scripting, you create and deploy a service called MeshApp. This service contains the C# code that supports multiplayer interactivity and is built and deployed automatically when you upload your Environment to Mesh. 



Make sure you have the following installed:

Azure CLI 2.40.0. 

.NET 6.0 SDK Windows

**To confirm that you have the Azure CLI installed**:

- Run the az --version command. (Learn about choosing the right Azure command-line tool.)

**To confirm that you're logged in to the subscription where you have permissions to deploy MeshApp's cloud infrastructure**:

- Run the az account show command. If you're not logged in to the correct subscription, run az logout and then az login to log in to the right account. If you have access to multiple Azure subscriptions in different tenants, it's easier to log in using the az login --use-device-code command.

**Note**: Switching Azure subscriptions/tenants using the Azure CLI resets your default subscription. To ensure that you update your default subscription if you switch tenants, use the az account set -n "<subscription-name>" command. Example: az account set -n "My Azure Subscription".

For MeshApp to function properly, you'll need to add the items listed below to your project. We recommend that you obtain them and have them handy before you start the tutorial.  If you're not sure how to obtain them, talk to your Azure Admin.

**Resource Group**

You'll need to select an Azure resource group for Mesh Scripting. This is the resource group you intend to use to deploy MeshApp. You can do one of the following:  
- If you have subscription access privileges, let the project create a default resource group for you.  
-or-  
- Get contributor-level access to a specific resource group from your subscription admin and make a note of the name of this resource group.  

**Subscription ID**

This is the subscription ID for your chosen resource group. 

    ![_________________________](../../../media/mesh-scripting/setup-in-uploader/001-subscription-id.png)

**Add MeshApp settings to your project**

As a reminder, MeshApp is an app service that you'll be adding to your project to support multiplayer interactivity.

< TBD >

... and then do the following:

- Copy the subscription ID that you obtained earlier for MeshApp (see the Prerequisites section named Mesh Scripting setup information) and then paste it into the Subscription ID field.  
- Enter a Resource Group or let the project choose one for you (details on this are also in the Prerequisites section).  
- You can accept the default Location or choose a different one.

- When you're finished, close the Project Settings window.

