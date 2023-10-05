---
title: Build and publish your Environment
description: Learn how to turn your Environment into an Asset and then publish it in the Mesh Portal.
author: typride
ms.author: vinnietieto
ms.date: 10/05/2023
ms.topic: Guide
keywords: Microsoft Mesh, environment, build, publish, build and publish, uploader, Mesh uploader
---

# Build and publish your Environment

After you finish adding all your scene content, the next step is to build the scene as an *asset* and then upload it to your chosen World in the Mesh Portal (M365), where it's saved as an *Environment.* This is achieved by using the Mesh Uploader. Event producers with access to that World can then create an Event based on your Environment and invite participants to come and share in a *Mesh experience*.

1. On the menu bar, select **Mesh Toolkit** > **Configure Project Settings**.

    ![A screenshot of a computer Description automatically generated](../../media/make-your-environment-available-for-events/001-project-settings.png)

1. Select **Yes** to configure project settings for Mesh.

    ![Graphical user interface, text, application Description automatically generated](../../media/make-your-environment-available-for-events/image015.png)

1.  On the menu bar, select **Mesh Toolkit** > **Environments**.

1. In the **Mesh Environments** window, select **Sign In**.

1. Sign in with your account.

    Make sure you're in the **Create** **Environment** tab, and then fill
    in the **Internal Name** and **Description** fields. 
    
    > [!IMPORTANT]
    > The **Internal Name** field has a maximum of 40 characters, and the
    **Description** field has a maximum of 70 characters.

1. To ensure you have the latest worlds that are available, select the **Refresh List of Mesh Worlds** button.

1. Select the **Mesh World** drop down, and then select the world you
    want to upload your Environment to if it's not already selected.

1. In the **Capacity** field, enter the capacity for your Environment.
    The maximum is 16.

    ![A screenshot of a computer Description automatically generated](../../media/make-your-environment-available-for-events/002-uploader-create.png)

1.  Select **Create Asset** to create the Environment that you'll be
    uploading.

1. You'll receive a confirmation dialogue as shown below. Select
    **Close**.

    ![A screenshot of a computer screen Description automatically
    generated with medium
    confidence](../../media/make-your-environment-available-for-events/image017.jpg)

    You should now be in the **Update Environment** tab of the **Mesh
    Environments** window.

    ![A screenshot of a computer Description automatically
    generated](../../media/make-your-environment-available-for-events/003-uploader-update.png)

    Note that in the **Environment Configurations** section, you already
    have an Environment configuration created which displays the name you
    added in the **Create Environment** tab: *Vinnie's Dartroom*.

## Add more Environments for build and publish

If you want to Build & Publish more then one Environment, click on **Add Environment Configuration** button and follow the steps from [Select the Environment for build and publish](#select-the-environment-for-build-and-publish).

![A screenshot of adding new environment to configure](../../media/make-your-environment-available-for-events/uploader_add_environment_button.png)

![A screenshot of added new environment to configure](../../media/make-your-environment-available-for-events/uploader_add_environment_button_result.png)



## Select the Environment for build and publish

If you want to configure the Environment that you've just created, ignore this section and go to [Configure the Environment for build and publish](#configure-the-environment-for-build-and-publish).
If you want to pick one that already exists, select the field that displays **Select Environment**. Then pick your Environment and configuration that you want to update.

![A screenshot of available Environments](../../media/make-your-environment-available-for-events/uploader_list_of_avaliable_environments.png)

If you added one of the environments from the list already, it will be marked grey and you won't be able to select it

Sometimes the list of the available Environments can be big. Use these 2 filters to help sort environments:

![A screenshot of Environments filters](../../media/make-your-environment-available-for-events/uploader_environment_filters.png)


### Filter Environments by Worlds

By default you can see Environments from all the Worlds, that you have access too. However you can filter the list by specifying the World, which Environments you would like to update
![A screenshot of Environments World filter](../../media/make-your-environment-available-for-events/uploader_environment_world_filter.png)


### Filter Environment by Name

By default you can see Environments from all the Worlds, that you have access too. However you can filter the list by specifying text that Environment name should have.
![A screenshot of Environments Text filter](../../media/make-your-environment-available-for-events/uploader_environment_name_filter.png)


## Configure the Environment for build and publish

1. Select the field that displays **Select a Scene**. In the
    **Select** **SceneAsset** window, double-click the scene in your
    project that you want as the Environment. In this example, we're
    using the Mesh sample project *Dartroom*, so our chosen scene will be the scene also named *DartRoom*.

    ![A screenshot of a computer Description automatically generated](../../media/make-your-environment-available-for-events/004-select-scene.png)

1. In the **Build for Platforms** section, you choose which platforms
    to build for. Note that when a button background is gray, the button
    is "on"; when the background is black, the button is "off." Do one
    of the following:

    - To build for PC only, make sure that only the PC button ("Mesh
        app on PC", the button on the left) is "on."

        ![A screen shot of a computer Description automatically generated with low confidence](../../media/make-your-environment-available-for-events/image021.jpg)

    - To build for Android only, make sure that only the Android button ("Mesh app on Quest", the button on the right) is "on."

        ![A screen shot of a computer Description automatically generated with low confidence](../../media/make-your-environment-available-for-events/image022.jpg)

    - To build for both PC and Android, make sure that both buttons are "on."

        ![A screen shot of a computer Description automatically generated with low confidence](../../media/make-your-environment-available-for-events/image023.jpg)

## Build and publish the Environment

1. Select the **Build and Publish** button.

    ![A screen shot of a computer Description automatically generated with medium confidence](../../media/make-your-environment-available-for-events/image024.jpg)

1.  If the Environment builds and uploads successfully, the **Build and
    Upload Results** dialog appears and confirms the results.

    ![A screenshot of a computer Description automatically generated](../../media/make-your-environment-available-for-events/005-build-succeeded.png)

    If the build and upload process fails, this is confirmed in the **Build and Upload** Results dialog:

    ![A screenshot of a computer program Description automatically generated with medium confidence](../../media/make-your-environment-available-for-events/006-build-failed.png)

## Next steps

> [!div class="nextstepaction"]
> [Get information about your Environment](get-information-about-your-environment.md)

