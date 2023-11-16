---
title: Publish multiple environments from one Unity project
description: Learn how to publish multiple environments from one Unity project using the Mesh Toolkit
ms.service: mesh
author: typride
ms.author: iankudinova
ms.date: 11/15/2023
ms.topic: Guide
keywords: Microsoft Mesh, environment, Unity, build, publish, build and publish, uploader, Mesh uploader, filter, multiple
---

# Publish multiple Environments from one Unity project

## Overview

There might be times when you can benefit by having a single Unity project that can generate multiple Experiences. Here's one example: Let's say you want to build a series of gaming Experiences that'll reuse a lot of the same assets. You can create a single Unity project that contains all your assets, then create each individual game room as a Scene, and then use the Mesh Uploader to turn the Scenes into Experiences and upload them to a World in Mesh on the Web.

Using the scenario above as an example, here's what you would do:

1. Create a new Unity project named "GameRooms."
1. Create an individual Scene for each game room. Name each Scene as follows:

    DartsRoom  
    BilliardsRoom  
    ChessRoom  
 
## Mesh Uploader versions

As explained in the article named [Add the Mesh Toolkit package](../build-your-basic-environment/add-the-mesh-toolkit-package.md), there are two versions of the Mesh Toolkit: the stable build and the preview build. At the time of this writing (mid-November 2023), the preview build of the Uploader contains a few updates that make it slightly different from the stable build:

1. The preview version has a new Mesh logo.
1. *Mesh Worlds* in the stable version are now called *Mesh Environment Collections* in the preview version.

    ![Screenshots of the current stable and preview versions of the Mesh Uploader with the differences highlighted.](../../../media/sample-mesh-101/506-uploader-stable-preview-comparison.png)

For this article, we'll assume you're using the stable build, with **Mesh Worlds** displayed, but keep these differences in mind if you're using the preview version.

## Create your Environments

1. Follow the instructions detailed in the [Build and publish your Environment](./build-and-publish-your-environment.md) article to open the Mesh Uploader and then create your first Asset, named "DartsRoom":

    ![A screenshot of the Mesh Uploader window in the Create Environment tab with information for the DartsRoom Environment.](../../media/make-your-environment-available/011-create-dartsroom-asset.png)

1. Select **Create Asset**.
1. In the **Create Results** window, select **Success** and then close the window.

    The Uploader automatically takes you to the **Update Environment** tab. If you were creating a single Environment, this would be the right place to continue the process. However, in this example, we're creating multiple Environments, which means we have more work to do in the **Create Environment** tab.

1. Select **Create Environment** to return to that tab. 
1. Replace the current information displayed in that tab with the information that applies to the *BilliardsRoom* Experience.

    ![A screenshot of the Mesh Uploader window in the Create Environment tab with information for the BilliardsRoom Environment.](../../media/make-your-environment-available/012-create-billiardsroom-asset.png)

1. Select **Create Asset**.
1. In the **Create Results** window, select **Success** and then close the window.
1. Select **Create Environment** to return to that tab.
1. Replace the current information displayed in that tab with the information that applies to the *ChessRoom* Experience.

    ![A screenshot of the Mesh Uploader window in the Create Environment tab with information for the ChessRoom Environment.](../../media/make-your-environment-available/013-create-chessroom-asset.png)

    You've now created three Experiences--one for each game room. This finishes our work in the **Create Environment** tab. The Uploader moves us to the **Update Environment** tab; we can stay there because this is where we select the correct Scene for each Experience.

1. In the first **Environment Configuration** (the one that displays *(New) Dart Room*), click the field that displays **Select a Scene** and then, in the **Select** **SceneAsset** window, double-click **Dartrooms**.
1. Repeat the step above for the other two Environment Configurations, selecting **BilliardsRoom** for #2 and **Chessroom** for #3.

    ![A screenshot of the Mesh Uploader window in the Create Environment tab with information for the ChessRoom Environment.](../../media/make-your-environment-available/014-three-scenes.png)

You're now set up to generate the three different Environments. For instructions on completing the build and publish process, see the [Build and publish your Environment](./build-and-publish-your-environment.md) article.


