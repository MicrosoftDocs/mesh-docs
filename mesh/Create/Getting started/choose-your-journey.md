---
title: Choose your journey
description: Determine the best path for you in our documentation.
author: typride
ms.author: tmilligan
ms.date: 7/31/2023
ms.topic: overview
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

It's easiest to start with a sample file to ensure all packages are configured in your Unity project. We recommend this option if you haven't already created a Mesh project in Unity. 

There are several samples to choose from:

- **Hello World.** A simple yet elegant small room with various
paintings (powered by WebView) and objects that will set your Unity
project up for basic Mesh development.

- **Scripted Worlds.** A simple Environment where you can see the
power of scripted worlds and begin scripting in Mesh.

- **Dartroom.** A saloon-style room with a dart game to showcase
interactive Mesh Physics features.

- **Science Building.** An expansive museum exhibiting the power of
Mesh Physics to create dynamic, engaging experiences.

## Open and build upon an existing sample

The easiest way to set up your Unity project for Mesh development is to start with a sample. There are various samples that display an array of Mesh features.

1. If you haven't done so already, [download and unzip the Mesh toolkit as explained in the previous section.](#_Download_the_Mesh)

    To ensure the manifest files in each sample properly configure their
    project settings and access the packages, you'll want to maintain this
    file structure:
    
    Mesh Toolkit 23.x
    
    - Packages
    
    - Samples
    
      - DartRoom
    
      - Mesh101-Unity
    
      - HelloWorld-Unity
    
      - ScienceBuilding
    
      - ScriptedWorlds

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

You can upgrade the packages in your existing project and then continue developing. Make sure your project uses the 3D (URP) project template, and then import the Mesh Toolkit package. Note that you may encounter some configuration notifications with upgrading and replacing older packages.

## Start from scratch

If you'd like to start from scratch and build from the ground up, create a simple 3D URP (Core) project and then import the necessary packages.

For a much more details explanation of how to set up a project for Mesh development, see the article named [Create a new Unity project](create-new-mesh-project.md).

## Add more features to your Environment

Once you've created an Environment through the paths mentioned above, you can add features including:

- [WebViews to display Web pages](../Developing%20for%20Mesh/Building%20your%20environment/webcontent.md)

- [Cloud scripting](../Developing%20for%20Mesh/Scripting%20your%20scene%20logic/cloud-scripting-overview.md), [visual scripting](../Developing%20for%20Mesh/Scripting%20your%20scene%20logic/visual-scripting-overview.md), and [Mesh Physics](../Developing%20for%20Mesh/Building%20your%20environment/physics-interactions.md) to add interactivity

- And more!

## Next steps
Now's the time to choose your journey:

- [Open and build upon an existing sample](start-with-sample.md).

- [Upgrade packages in a pre-existing Mesh project in Unity.](install-tools-upgrade.md)

- [Start a new project from scratch.](create-new-mesh-project.md)


