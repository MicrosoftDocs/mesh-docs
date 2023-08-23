---
title: Start with a sample
description: Start developing for Mesh with sample.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, Unity, Immersive spaces, Avatars, getting started, documentation, features
---

# Start with a Mesh sample

It's easiest to start with a sample file to ensure all packages are
configured in your Unity project. We recommend this option if you
haven't already created a Mesh project in Unity.

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

## Prerequisites

Unity Editor version 2021.3.21f1+

## Open a Sample in Unity

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
