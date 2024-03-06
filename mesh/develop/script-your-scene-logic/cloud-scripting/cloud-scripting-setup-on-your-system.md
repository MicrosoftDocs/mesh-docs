---
title: Set up Mesh Cloud scripting on your system
description: Learn how to set up your system so you can use Mesh Cloud Script in your Unity project.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 2/28/2024
ms.topic: Guide
keywords: Microsoft Mesh, scripting, cloud scripting, visual scripting, coding
---

# Set up Mesh Cloud scripting on your system

## Overview

In order to use Mesh Cloud scripting in your Mesh experience, there are three things you must do:

1. Deploy the *Mesh Cloud Scripting Service* cloud infrastructure to Azure.
2. Set up your development environment.  
1. Provide cloud scripting details when you build and publish your experience.

In this article, you'll learn about Step #2: set up your development environment.

## Prerequisites

Make sure you have the following installed:

[Azure CLI 2.40.0.](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

[].NET 6.0 SDK Windows](https://dotnet.microsoft.com/en-us/download/dotnet/6.0)

**To confirm that you have the Azure CLI installed**:

- Run the az --version command. (Learn about [choosing the right Azure command-line tool](/cli/azure/choose-the-right-azure-command-line-tool).)

**To confirm that you're logged in to the subscription where you have permissions to deploy MeshApp's cloud infrastructure**:

- Run the **az account show** command. If you're not logged in to the correct subscription, run **az logout** and then **az login** to log in to the right account. If you have access to multiple Azure subscriptions in different tenants, it's easier to log in using the **az login --use-device-code** command.

**Note**: Switching Azure subscriptions/tenants using the Azure CLI resets your default subscription. To ensure that you update your default subscription if you switch tenants, use the **az account set -n "<subscription-name>"** command. Example: **az account set -n "My Azure Subscription"**.

## Record your resource group and Subscription ID for later use

For *Mesh Cloud Scripting Service* to function properly, you'll need to add the items listed below to your project. We recommend that you obtain them and have them handy before you're ready to build and publish your project; you'll need to specify them in the Mesh Uploader.  If you're not sure how to obtain them, talk to your Azure Admin.

### Resource Group

You'll need to select an Azure resource group for Mesh Cloud Scripting. This is the resource group you intend to use to deploy *MeshApp*. You can do one of the following:

- If you have subscription access privileges, let the project create a default resource group for you.  
-or-  
- Get contributor-level access to a specific resource group from your subscription admin and make a note of the name of this resource group.  

### Subscription ID

This is the subscription ID for your chosen resource group. 

    ![_________________________](../../../media/mesh-scripting/setup-in-uploader/001-subscription-id.png)

**IMPORTANT**: The configuration of a subscription and resource group for the Mesh World that you'll publish your Environment to may or may not be the same as the configuration of a subscription and resource group for MeshApp.

## Next steps

   > [!div class="nextstepaction"]
   > [Provide Cloud Scripting details in your project](./cloud-scripting-provide-details.md)
