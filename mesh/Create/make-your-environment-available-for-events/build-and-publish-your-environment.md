---
title: Build and publish your Environment
description: Learn how to turn your Environment into an Asset and then publish it in the Mesh or Azure Portals.
author: typride
ms.author: vinnietieto
ms.date: 9/12/2023
ms.topic: Guide
keywords: Microsoft Mesh, environment, build, publish, build and publish, uploader, Mesh uploader, thumbnail
---

# Build and publish your Environment

After you finish adding all your scene content, the next step is to build the scene as an *asset* and then upload it to your chosen World in the Mesh Portal (M365) or the Azure Portal, where it's saved as an *Environment.* This is achieved by using the Mesh Uploader. Event producers with access to that World can then create an Event based on your Environment and invite participants to come and share in a *Mesh experience*.

1. On the menu bar, select **Mesh Toolkit** > **Configure Project
    Settings**.

    ![A screenshot of a computer Description automatically generated](../../media/make-your-environment-available-for-events/001-project-settings.png)

1. Select **Yes** to configure project settings for Mesh.

    ![Graphical user interface, text, application Description automatically generated](../../media/make-your-environment-available-for-events/image015.png)

1.  On the menu bar, do one of the following:

**To build and publish to the Azure portal**:
- Select **Mesh Toolkit** > **Environments**.

**To build and publish to the Mesh Portal**:
- Select **Mesh Toolkit** > **Environments (M365)**.

1. In the **Mesh Environments** window, select **Sign In**.

1. Sign in with your account. The account must have *Content
    Contributor* access to the Mesh world you're uploading the
    Environment to. If you need help with Content Contributor
    privileges, see [*Become a Content
    Contributor*](#become-a-content-contributor).

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

## Configure the Environment for build and publish

1. Select the field that displays **Select a Scene** and then, in the
    **Select** **SceneAsset** window, double-click the scene in your
    project that you want as the Environment. In this example, we're
    using the Mesh sample project *Dartroom*, so our chosen scene will be the scene also named *DartRoom*.

    ![A screenshot of a computer Description automatically generated](../../media/make-your-environment-available-for-events/004-scene-select.png)

1.  Select **Include thumbnails** and then, in the popup menu, choose
    **Generate Thumbnails**.

    ![A screenshot of a computer Description automatically generated](../../media/make-your-environment-available-for-events/image020.png)

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

## Environment thumbnails

Adding a custom thumbnail image that will be
added to your Environment listings in the Mesh Portal or Mesh App comes in handy when you're selecting Environments in either place because it gives you a visual reminder of what the Environment looks like.

You can customize the thumbnails from your environment in two ways:

1. You can add a **MeshThumbnailCamera** to your scene which will ensure you always get the latest changes from your scene in the thumbnails.
2. You can specify a folder containing the images you want to use for the thumbnails.

### Option 1 - Adding the thumbnail camera

To add the thumbnail camera to the scene and sets its view:

1. In the **Scene** window, adjust the view so that it shows what you
    want to display in the thumbnail (the Thumbnail Camera's view will
    be based on the **Scene** view).

1. Select the "+" drop-down located below the **Hierarchy** tab, and
    then select **Mesh Toolkit > Thumbnail Camera**.

    ![A screenshot of a computer program Description automatically generated with medium confidence](../../media/make-your-environment-available-for-events/007-add-thumbnail-camera.png)

1. To confirm that the view in the Thumbnail Camera is what you want,
    in the **Hierarchy**, select **MeshThumbnailCamera**. The Camera's
    view appears in a small window in the lower right of the **Scene**
    view.

    ![A screenshot of a computer program Description automatically generated with medium confidence](../../media/make-your-environment-available-for-events/008-thumbnail-view.png)

    **Note**: If you decide you want a different view for the Thumbnail
    Camera, you can adjust it directly in the **Scene** view or change its
    **Position** and **Rotation** values in the **Inspector** prior to
    uploading your Environment to Mesh.

    There are no set rules for how your thumbnail should look---it's totally
    up to you. For the following example, we chose a close-up front view of
    the darts.

1. To upload the environment with your thumbnails open the **Mesh Uploader**, on the menu bar, select **Mesh Toolkit** > **Environments**.

1. On the **Update Environment** tab make sure you have the correct Environment and scene selected than check the **Custom Thumbnails** field and choose the **Generate from Thumbnail Camera** option.

    ![A screenshot of a computer program Description automatically generated with medium confidence](../../media/make-your-environment-available-for-events/009-select-custom-thumbnail.png)

1. Once you are ready to publish your Environment click on **Build & Publish** and the custom thumbnails will be uploaded together with your environment.

    **Note**: If you uncheck the **Custom Thumbnails** field the thumbnails from your Environment will be removed, so make sure this is always checked when you do **Build & Publish**

### Option 2 - Custom thumbnail folder

If you prefer to have static images as thumbnails you can choose to select the images from a folder:

1. Open the **Mesh Uploader**, on the menu bar, select **Mesh Toolkit** > **Environments**.

1. On the **Update Environment** tab make sure you have the correct Environment and Scene selected than check the **Custom Thumbnails** field and choose the **Take from folder** option. The default folder is shown and you can either add your images to this folder or choose a different folder.

    ![A screenshot of a computer program Description automatically generated with medium confidence](../../media/make-your-environment-available-for-events/010-thumbnail-from-folder.png)

    **Note**: To choose a new folder for your thumbnails click on the button highlighted in yellow.

1. The thumbnail images need to follow a specific name pattern, the easier way to follow that is to click on the button **Add provisional thumbnails** which will add three images to the folder selected with the correct names and sizes, you can then replace those images with the images you like, just remember to keep their names and try to follow their sizes for a better UI experience.

1. Once you are ready to publish your Environment click on **Build & Publish** and the custom thumbnails will be uploaded together with your environment.

## Next steps

> [!div class="nextstepaction"]
> [Get information about your Environment](get-information-about-your-environment.md)
