---
title: Choose your journey
description: Determine the best path for you in our documentation.
author: typride
ms.author: vinnietieto
ms.date: 8/25/2023
ms.topic: overview
ms.prod: mesh
keywords: Microsoft Mesh, M365, Immersive spaces, Avatars, getting started, documentation, features
---

# Choose your journey

## Try our Mesh 101 tutorial

If you're new to Mesh and like the idea of learning through a step-by-step tutorial, we recommend that you try our Mesh 101 tutorial. It starts you off with a pre-built Unity project and then walks you through the process of creating an educational windfarm experience. You'll learn how to use Mesh scripting and physics to add interactivity, and then you'll deploy the project as a metaverse Environment to your Mesh World.

If you're ready to starting building Mesh experiences, you have several approaches to choose from:

- Open and build upon an existing sample.

- Upgrade packages in a pre-existing Mesh project in Unity.

- Start a new project from scratch.

## Start with a Mesh sample

It's easiest to start with a sample file to ensure all packages are configured in your Unity project. We recommend this option if you haven't already created a Mesh project in Unity. The available samples display an array of Mesh features.:

- **Hello World.** A simple yet elegant small room with various
paintings (powered by WebView) and objects that will set your Unity
project up for basic Mesh development.

- **Scripted Worlds.** A simple Environment where you can see the
power of scripted worlds and begin scripting in Mesh.

- **Dartroom.** A saloon-style room with a dart game to showcase
interactive Mesh Physics features.

- **Science Building.** An expansive museum exhibiting the power of
Mesh Physics to create dynamic, engaging experiences.

- **Mesh 101.** As mentioned above, Mesh 101 is a tutorial, but it also doubles as a sample. In the project, you can open the *StartingPoint* scene and begin walking through the tutorial. However, the project contains another scene named *FinishedProject* which is a completed version of the tutorial. You can view this scene as a sample and use it as starting point for your project just as you would with any of the other samples.

**To start with an existing sample**:

1. If you haven't done so already, [download and unzip the Mesh toolkit](download-the-mesh-toolkit.md).

    > [!IMPORTANT]
    > Make sure to follow the instructions in the Mesh Toolkit download article for maintaining the proper file structure. If you don't, packages might not load properly and this could result in things like missing materials.

2. Navigate to the **Samples** folder and then unzip each sample.

    **IMPORTANT**: When you unzip a sample Zip file, ensure that you're
    creating a new folder for the project to be extracted to. If you use
    File Explorer's **Extract All ...** menu item, the workflow lets you do
    this automatically:

    ![Graphical user interface, text, application, email Description
    automatically generated](../../media/get-started-developing-mesh/image006.jpg)

3. In the Unity Hub, select **Open** \**Add project from disk**, and
    then navigate to and open the sample project you want to use.

4. In Unity, navigate to **Assets** \**Scenes** and then open the
    scene you want---this will vary from sample to sample. For example,
    in the *Science Building* project, you would open the
    **ScienceBuilding** scene.

    Here's an example of what you'll find in that scene:![](../../media/get-started-developing-mesh/image007.png)

## Upgrade packages in a pre-existing Mesh project

You can upgrade the packages in your existing project and then continue developing.

1. Make sure your project uses the 3D (URP) project template.
1. [Download and unzip the Mesh toolkit](download-the-mesh-toolkit.md).
1. Import the Toolkit package into your project.

Note that you may encounter some configuration notifications with upgrading and replacing older packages.

## Start from scratch

If you'd like to start from scratch and build from the ground up, create a simple 3D URP (Core), then [download and unzip the Mesh toolkit](download-the-mesh-toolkit.md), and then import the Toolkit package into your project.

For a much more details explanation of how to set up a project for Mesh development, see the article named [Create a new Unity project](create-new-mesh-project.md).

## Add more features to your Environment

Once you've created an Environment through the paths mentioned above, you can add features including:

- [WebViews to display Web pages](../design-and-develop/enhance-your-environment/webcontent.md)

- [Cloud scripting](../design-and-develop/script-your-scene-logic/cloud-scripting-getting-started.md), [visual scripting](../design-and-develop/script-your-scene-logic/visual-scripting.md), and [Mesh Physics](../design-and-develop/enhance-your-environment/physics-interactions?branch=PuP-Mesh-Docs.md) to add interactivity

- And more!

## Next Steps

   > [!div class="nextstepaction"]
   > [Create a new project](../design-and-develop/build-your-basic-environment/create-a-new-project.md)
