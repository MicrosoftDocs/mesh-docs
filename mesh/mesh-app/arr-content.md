---
title: Azure Remote Rendering (ARR) content 
description: You can now load Azure Remote Rendering models to your space
ms.prod: mixed-reality
author: qianw211
ms.author: v-qianwen
ms.date: 05/19/2021
ms.topic: article
keywords: mixed reality, microsoft mesh, documentation, guides, features, holograms, spaces
---

# Azure Remote Rendering (ARR) content

[Azure Remote Rendering (ARR)](/azure/remote-rendering/) is powered by Azure cloud to render high quality and interactive 3D content, and streams it to your devices in real time. With ARR, you can interact and collaborate with 3D content in amazing detail.  

## Enable ARR in Mesh app

If you want to load new ARR objects into a space, you will need to enable the **ARR** option in **Experimental Features** by going through the following steps:  

1. Look at your hand to [bring up the menu](use-mesh.md#the-hand-menu), and press the **Main menu** button at the top.
1. Go to **Settings**, select **Experimental Features** under the **General** tab.

    ![Screenshot of the **Settings -> General** tab.](media\settings-general.jpg)

1. Select **Azure Remote Rendering**.

    ![Screenshot of the **Experimental Features** option under **Settings** tab.](media\experimental-features.jpg)

1. You can now see a tab for Azure Remote Rendering objects in your **Content** menu.

     ![Screenshot of the Mesh app **Content** menu.](media\mesh-app-content.jpg)

Any ARR objects that you place in a space will be visible to all users in that space.

## Import your own ARR content  

To import your own content for remote rendering, you will first need to upload and process your models, see [Quickstart: Convert a model for rendering](/azure/remote-rendering/quickstarts/convert-model).  To import your models into the Mesh app, see steps below:

1. Go into your OneDrive directory online, preferably on your PC.
1. Go to Apps > Microsoft Mesh app (Preview) > MyContent folder on your OneDrive.
1. If you’ve enabled **ARR** in the Mesh app, there should be a `.json` file called `remote_models.json`.
1. Edit this `.json` file to give your model a name and add the [URI token address generated for your ARR model](/azure/remote-rendering/quickstarts/convert-model#insert-new-model-into-quickstart-sample-app).

When loading multiple ARR models, you can simply add the following code in the `remote_models.json` file for each additional model:

```json
{
modelname="model name",
modelUri="modelURI"
}
```

## Additional resources

For other questions, see [Microsoft Mesh app troubleshooting and frequently asked questions](faq.md).

- [Microsoft Mesh overview](../overview.md)
- [Set up Microsoft Mesh for your organization](../provisioning.md)
- [HoloLens](/hololens/)
- [Get started with Mixed Reality](/windows/mixed-reality/discover/get-started-with-mr)
- [Use the Mesh app](use-mesh.md)
- [Import content](import-content.md)