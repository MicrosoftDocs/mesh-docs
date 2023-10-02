---
title: Cloud scripting getting started
description: Get started with Cloud Scripting for Mesh.
author: typride
ms.author: vinnietieto
ms.date: 8/28/2023
ms.topic: Guide
keywords: Microsoft Mesh, scripting, cloud scripting, visual scripting, coding
---

# Mesh Cloud Scripting Getting Started Guide

This article will help you configure your development environment and start iterating on your project. We’ll also cover how to upload your environment, publish your app to Azure, and prepare for testing. Finally, we’ll go over testing and troubleshooting. We recommend that you familiarize yourself with the current list of [known issues](cloud-scripting-known-issues.md) before starting development with Mesh Cloud Scripting.

## Prerequisites

- Advanced Unity skills.
- A username and password for the Azure Portal so you can upload your work.

## Software dependencies

1. [.NET 6.0 SDK Windows](https://dotnet.microsoft.com/en-us/download)
1. [Unity 2022.3.7f1+](https://unity.com/releases/editor/whats-new/2022.3.7)
1. [Azure CLI 2.40.0](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

## Create a Scene with a C# MeshApp application

The following instructions show how to create a simple app with a cube that rotates when a user clicks on it. We'll use the app to show local development workflow, deployment and testing.

1. Create a new scene and choose the **Standard (URP)** template.
1. Save the scene and name it. For this example, we'll use the name **MyFirstMeshApp**.

    > [!NOTE]
    > Renaming of Unity scenes isn't supported, and space characters aren't allowed in project and folder names.

1. On the menu bar, select **GameObject** > **Mesh Toolkit** > **Set-up Cloud Scripting**.

   ![Screen shot of the Create Mesh App menu item.](../../../media/mesh-scripting/getting-started/002-create-mesh-app.png)

   Note that a game object named **Mesh Cloud Scripting** appears in the **Hierarchy** and is selected. This also creates a new C# application project under `Assets/.MeshCloudScripting/MyFirstMeshApp`.

   ![img](../../../media/mesh-scripting/getting-started/003-mesh-app-files.png)

1. You can use the **Open application folder** button to navigate to the project folder.

   ![img](../../../media/mesh-scripting/getting-started/MeshAppCmpInspectorDefaultView.png)

### Modify the scene

1. On the menu bar, select **GameObject** > **Mesh Toolkit** > **PlaymodeSetup** to add simulation support.
1. On the menu bar, select **GameObject** > **3D Object** > **Plane** to create a floor.
1. In the **Hierarchy**, select the **Plane** object and, in the **Inspector**, change the **Layer** to **NavMesh**.
1. On the menu bar, select **GameObject** > **3D object** > **Cube**.
1. In the **Hierarchy**, drag the cube to the **Mesh Cloud Scripting** object to make the cube a child of that object.

   ![A screen shot of the Cube placed as a child to MeshApp.](../../../media/mesh-scripting/getting-started/004-cube.png)

1. With the cube selected, in the **Inspector**, click **Add Component** and then select **Touch Sensor**.

   ![img](../../../media/mesh-scripting/getting-started/SimpleInteractionUnityAddTouchSensor.png)

1. In the **Transform** component, set the Cube's **Position** values to 0, 1, 3.
1. Save the scene.

### Modify the C# project

1. In the **Hierarchy**, select the **Mesh Cloud Scripting** object.
1. In the **Inspector**, navigate to the **Mesh Cloud Scripting** component and then click the **Open application folder** button. This opens File Explorer and shows you a view of your project contents.

   ![img](../../../media/mesh-scripting/getting-started/MeshAppCmpInspectorDefaultView.png)

1. Open the `App.cs` script in your code editor.
1. Note that in the App class, there are two variables:

   ```c#
   private readonly ILogger<App> _logger;
   private readonly ICloudApplication _app;
   ```

   Add the following as a third variable:

   ```c#
   private float _angle = 0;
   ```

1. The **StartAsync** method contains a single comment: "Add your app startup code here." Replace that with the code below so that the **StartAsync** method looks like the following:

   ```c#
   public Task StartAsync(CancellationToken token)
   {
       // First we find the TransformNode that corresponds to our Cube gameobject
       var transform = _app.Scene.FindFirstChild<TransformNode>();

       // Then we find the InteractableNode child of that TransformNode
       var sensor = transform.FindFirstChild<InteractableNode>();

       // Handle a button click
       sensor.Selected += (_, _) =>
       {
           // Update the angle on each click
           _angle += MathF.PI / 8;
           transform.Rotation = new Rotation { X = 1, Y = 0, Z = 0, Angle = _angle };
       };

       return Task.CompletedTask;
   }
   ```

### Run your application locally

1. Click the Play button.
1. Navigate around the scene and click on the cube.
1. Exit play mode.

### Debug your application with Visual Studio (optional)

1. In the **Hierarchy**, ensure that you have the **Mesh Cloud Scripting** object selected.

1. In the **Inspector**, navigate to the **Mesh Cloud Scripting** component and then select **Enable Application Debugging**.

   ![img](../../../media/mesh-scripting/getting-started/MeshAppCmpInspectorEnableDebugging.png)

1. Enter Play mode and select debugger.

   ![img](../../../media/mesh-scripting/getting-started/JITWindow.png)

1. Open the **App.cs** file, then add a break point, and then continue execution.

   ![img](../../../media/mesh-scripting/getting-started/JITSetBreakpoint.png)

1. In Unity, click the cube.

   ![img](../../../media/mesh-scripting/getting-started/JITHitBreakpoint.png)


## Upload the Environment

The MeshApp infrastructure deployment and publishing is integrated as part of the Mesh Toolkit Uploader. 
You can use the specific settings UI in MeshUploader to define your Azure subscription ID that the meshapp will be deployed to.

1. Add your deployment configurations such as Azure subscription ID to the environment from the MeshUploader UI. You could do this when you create an environment: setup the configs in the **Mesh Environments** window, **Create Environment** tab, **Setup Mesh Script Configuration** block shown in the following images. Alternatively, you could set up and update the setting for an existing environment in the **Update Environment** steps.

   ![img](../../../media/mesh-scripting/getting-started/UploaderCreateUIProjectSettings.png)

1. In the **Mesh Environments** window, **Update Environment** tab, select your environment and scene to upload. If the scene has a Mesh Script component, the deployment configurations will be shown along with the select scene. Select the **Modify Deployment Configs** tickbox to add or change the configs associated with the current environment and scene. Unselect the tickbox to save and update the settings and you should see the updated configs, as illustrated in the following images.

   ![img](../../../media/mesh-scripting/getting-started/UploaderUpdateUIProjectSettings.png)

1. In the **Mesh Environments** window, on the **Update Environment** tab, select **Build & Publish**. (To learn more about the Mesh Environments window, see our document titled *Get Started with Mesh Environments*.) TBD

   ![img](../../../media/mesh-scripting/getting-started/001-update-environment-tab.png)

1. As the Uploader builds and publishes your Environment, the application's infrastructure will be deployed to Azure and the application will be published.

   > [!TIP]
   > If this process doesn't complete successfully, see below on how to use **[Mesh APP CLI Tool](#appendix%3A-mesh-app-cli-tool)** to deploy manually.
   
   ![img](../../../media/mesh-scripting/getting-started/UploaderIntegrationDeployingMeshapp.png)

   ![img](../../../media/mesh-scripting/getting-started/UploaderIntegrationPublishingMeshapp.png)

1. When the Uploader has finished, you should see the MeshApp deployment and publishing operation results in the results window

> [!NOTE]
> If you're publishing an Environment for both PC and Android, it's normal to see  multiple entries for *MeshApp Metadata* in the results window.

   ![img](../../../media/mesh-scripting/getting-started/UploaderIntegrationUploaderResults.png)

### Connect to the deployed application from Unity

1. In the **Hierarchy**, ensure that the **Mesh Cloud Scripting** object is selected.
1. In the **Inspector**, navigate to the **Mesh Cloud Scripting** component, and then open the **Developer Settings** drop-down.
1. Unselect **Run Local Cloud Scripting Server**.
1. Click the Play button.

> [!NOTE]
> Since auth is now enabled on the Cloud Scripting server by default, it expects you to send an auth token from whichever client you're connecting from. You can set the auth mode in the Mesh Uploader Settings located in your Unity project's settings. The **Dev** option is recommended for MeshApps in active development.

### Create an event and join it from the Mesh app

1. Create an event using the Environment **MyFirstMeshApp**. If you need guidance, follow the _Event management_ section in the document named *Mesh IT Admins Guide*.TBD
1. Join the event in the Mesh app.

### Show MeshApps errors in the Mesh app (optional)

1. The error messages from MeshApps are by default not shown in the Mesh app in order to minimize user disruption. If you need to show these messages for debug purposes, use the following steps:

2. Go to the main menu of the Mesh app.

   ![img](../../../media/mesh-scripting/getting-started/MeshScriptingShowErrors_000.png)

2. Select "Settings" in the main menu.

   ![img](../../../media/mesh-scripting/getting-started/MeshScriptingShowErrors_001.png)

2. Go to the "Troubleshooting" tab in "Settings" and toggle the "Show Mesh scripting error" button.

   ![img](../../../media/mesh-scripting/getting-started/MeshScriptingShowErrors_002.png)

## Next steps

   > [!div class="nextstepaction"]
   > [Cloud scripting basic concepts](cloud-scripting-basic-concepts.md)

   > [!div class="nextstepaction"]
   > [Cloud Scripting Troubleshooting](cloud-scripting-troubleshooting.md)

   ## Next steps

> [!div class="nextstepaction"]
> [Cloud scripting programmer's guide](cloud-scripting-programmers-guide).md)