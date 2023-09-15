---
title: Mesh 101 Make your Environment available for Events
description: Learn how to uploaded your Environment and make it available for Event.
author: typride
ms.author: vinnietieto
ms.date: 9/11/2023
ms.topic: Tutorial
keywords: Microsoft Mesh, getting started, Mesh 101, tutorial, environment, M365, Azure Portal, uploader, uploading
---

# Mesh 101 Tutorial Chapter 5: Make your Environment available for Events

You've completed adding all the features you need for your Mesh
experience using Mesh Physics and Scripting. So far, we've been working
in a Unity *project*; now you'll turn the *StartingPoint* scene into a
Mesh *Environment* and upload it to your Mesh World in the Azure Portal. At that point, it will be available for the create of Events.

**Configure your project settings and sign in**

1. On the menu bar, select **Mesh Toolkit** > **Configure** >
    **Project Settings**.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/001-project-settings.png)

2. Select **Yes** to configure project settings for Mesh.

    ![Graphical user interface, text, application Description automatically generated](../../../media/sample-mesh-101/image089.png)

3. On the menu bar, select **Mesh Toolkit** > **Environments**.

4. In the **Mesh Environments** window, select **Sign In**.

Sign in with your account. **Note**: As mentioned in the Prerequisites
section, the account must have Content *Contributor* access to the Mesh
World you're uploading the Environment to.

### Create your environment

1. Make sure you're in the **Create** **Environment** tab, and then, in
    the **Internal Name** field, type "Wind Turbine Tutorial."

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/037-upload-create.png)

2. In the **Description** field, type "An interactive Mesh experience
    that teaches you about wind turbines."

    > [!NOTE]
    > For future projects, keep in mind that the **Internal Name** field has a maximum of 40 characters, and the **Description** field has a maximum of 70 characters.

3. To ensure you have the latest worlds that are available in the Azure
    Portal, select the **Refresh List of Mesh Worlds** button.

4. Select the **Mesh World** drop down, and then select the world you
    want to upload your Environment to if it's not already selected.

5. In the **Capacity** field, enter the capacity for your Environment.
    The maximum is 16.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/038-upload-capacity.png)

6. Select **Create Asset** to create the Environment that you'll be
    uploading to the Azure Portal.

7. You'll receive a confirmation dialogue as shown below. Select
    **Close**.

    ![A screenshot of a computer Description ](../../../media/sample-mesh-101/039-create-results.png)

### Build and publish your environment

You should now be in the **Update Environment** tab of the **Mesh
Environments** window.

![A screenshot of a computer Description ](../../../media/sample-mesh-101/040-upload-update.png)

> [!NOTE]
> In the **Environment Configurations** section, a new Environment configuration has been created that displays the name you  added in the **Create Environment** tab: *Wind Turbine Tutorial*. If you see any other Environment configurations, close them.

- Select **Include Thumbnails**. Leave the setting as **Generate
    Thumbnails**.

    ![](../../../media/sample-mesh-101/image094.jpg)

### Building for single and multiple platforms

It's good to keep in mind that Mesh events can be experienced on two
different platforms: desktop PC and Android, which powers the Meta Quest
headset. Since desktop PCs typically have far more power than mobile
devices using Android, when you're creating your own project, there are
several potential scenarios to consider: build and publish your scene
for PC only, Android only, or both PC and Android. This tutorial follows
option #3: build and publish for PC and Android. To learn more about
building for single and multiple platforms, see our document titled *Get
Started with Mesh Environments*.

### Create the Environment

1. In the **Update Environment** tab, click the **Select a scene**
    field, and then, in the **Select SceneAsset** dialog, select
    **StartingPoint**.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image095.jpg)

In the **Build for Platforms** section, you choose which platforms to
build for. Note that when a button background is gray, the button is
"on"; when the background is black, the button is "off." We're building
for both PC and Android, so make sure that both buttons are "on."

![A screen shot of a computer Description automatically generated with low confidence](../../../media/sample-mesh-101/image096.jpg)

### Build and publish your Environment

1. In the **Publish** section, provide some information in the **Upload
    notes** box if you wish.

- Select the **Build and Publish** button.

    ![A screen shot of a computer Description ](../../../media/sample-mesh-101/041-build-and-publish.png)

- If the Environment builds and uploads successfully, the **Build and
    Upload Results** dialog appears and confirms the results.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/042-results.png)

- If the build and upload process fails, this is confirmed in the **Build and Upload** **Results** dialog.

### View your Environment in Azure

If you navigate to the **Environments** page for your World in the Azure
Portal, you'll see that your Environment has been saved there. Its type
will be listed as "Custom Environment."

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image100.jpg)

Your saved custom Environment will be available to anyone who creates a
new event in that Mesh world.

> [!NOTE]
> For viewing Worlds in the Mesh Portal, refer to the [M365 Migration Guide](../../../Setup/Content/m365-migration-guide.md). 

### Summary

In this chapter, you learned how to create an Environment based on your
scene and then build it and publish it to your World in the Azure
Portal.

## Next steps

> [!div class="nextstepaction"]
> [Chapter 6: Create an Event and invite others](mesh-101-6-create-an-event-and-invite-others.md)
