---
title: Mesh 101 Overview and setup
description: Learn about the prerequsites and setup process for the Mesh 101 tutorial project.
author: typride
ms.author: vinnietieto
ms.date: 9/8/2023
ms.topic: Tutorial
keywords: Microsoft Mesh, getting started, Mesh 101, tutorial
---

# Mesh 101 Tutorial Chapter 1: Overview and Setup

The Mesh 101 tutorial is a great way to learn about adding Mesh features
to a Unity project to create an interactive learning experience. Created
for intermediate to advanced Unity developers, the tutorial will give
you a solid understanding of the power of Mesh, spanning Mesh Physics,
Scripting, and more. You'll start with a pre-built Unity project, add
custom interactivity and other Mesh features, and then deploy the
project as a metaverse *Environment* to Microsoft Mesh. Customers can
attend an Event based on your Environment where they'll learn about wind
turbines by visiting a series of interactive stations and experience
multi-user interaction and communication.

The tutorial project is named *Mesh101.Unity* and is included in the
Mesh Toolkit.

The tutorial is structured as follows:

This article: Overview and setup

[Chapter 2: Prepare the tutorial project](mesh-101-02-prepare-the-project.md)

[Chapter 3: Add interactivity with Mesh Visual Scripting](mesh-101-03-visual-scripting.md)

- Station 3.1: Create an Interactable Button
- Station 3.2: Trigger an info dialog
- Station 3.3: Teleport to the turbine generator

[Chapter 4: Move objects and trigger animations with Mesh Physics](mesh-101-04-physics.md)

- Station 4.1: Grab and Release
- Station: 4.2 Animation Trigger
- Station 4.3: Constraining Bodies

[Chapter 5: Make your Environment available for Events](mesh-101-05-make-environment-available.md)

[Chapter 6: Create an Event and invite others](mesh-101-06-create-an-event-and-invite-others.md)

## Terminology

In Mesh terms, the project you create in Unity and then upload to the
Azure Portal is called an *Environment*.

## Prerequisites

### Hardware requirements

Minimum PC requirements: 4 CPU cores, 8Gb RAM

### Unity version 2022.3.7f1

Unity version 2022.3.7f1 is required for this tutorial.

[Get help installing Unity](https://docs.unity3d.com/hub/manual/InstallEditors.html)

Your installation should include modules for Android and Windows.

Unity supports three IDEs: VS, VS Code, and JetBrains Rider. We
recommend Visual Studio, but other supported IDEs will work. You'll be
using this for Mesh Scripting.

**IMPORTANT**: Mesh Scripting requires Visual Studio *2022*, but certain versions of Unity install with Visual Studio *2019* by default. If you're
using Visual Studio, make sure you have version 2022 installed. To learn
more, see the [Unity documentation](https://learn.unity.com/tutorial/get-started-with-visual-studio-and-unity).

### Previous Unity experience

This tutorial assumes that you have intermediate to advanced Unity
skills.

### Azure portal access

You'll need a username and password for the Azure Portal so you can
upload your work.

#### Content Contributor permissions

To upload an Environment to a Mesh world, there are two things that must
be enabled for your work account:

1. **Mesh world already created.** There must be a Mesh world to upload
    to from Unity. If there isn't one, your Azure Admin or Mesh world
    resource owner should make one for you.

2. **Content Contributor role.** Your Azure Admin or Mesh world owner
    must add your work account as a Content Contributor for each Mesh
    world you want to upload an Environment to.

For more information, see our IT Admin Guide*.

## Set things up for Mesh

### Download the Mesh desktop app

To download the app (codenamed **Project Napili**), you can visit the link below.

![Project Napili - Microsoft Store Apps](../../../media/sample-mesh-101/image003.png)
> [Project Napili - Microsoft Store Apps](https://apps.microsoft.com/store/detail/project-napili/9P0B5VMS9RTQ?hl=en-us&gl=us)

**If the app isn't available, talk to your IT** **admin about making the
app visible to you.**

### Download the Mesh Toolkit

The Mesh Toolkit contains the *Mesh 101* tutorial project.

1. In your browser, navigate to the **Microsoft Mesh TAP Onboarding
    Resources** website
    [Microsoft Mesh TAP Onboarding Resources - Home (sharepoint.com)](https://microsoft.sharepoint.com/teams/MicrosoftMeshEAPOnboardingResources/?OR=Teams-HL&CT=1660599435162&clickparams=eyJBcHBOYW1lIjoiVGVhbXMtRGVza3RvcCIsIkFwcFZlcnNpb24iOiIyNy8yMjA4MDcwMTAwMCIsIkhhc0ZlZGVyYXRlZFVzZXIiOmZhbHNlfQ%3D%3D)
2. On the main page, scroll down to the **Mesh Resources and Developer
    Tools** section, and then, under **Get the Files and Packages**,
    select the **Go** button.

    ![Screenshot of Mesh Resources and Developer Tools](../../../media/sample-mesh-101/image004.jpg)
3. On the **Files and Packages** page, download the latest version of
    the Mesh Toolkit (it may be more recent than what you see here). Select the three-dot button and then select
    **Download**.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image005.jpg)

    > [!NOTE]
    > The downloaded zip file's name may vary depending on your
    > computer setup.
4. On your C: drive, create a folder with a one-word name (for example,"Mesh101") and then move or copy the downloaded Mesh Toolkit Zip file to that folder. This is done to avoid running into a problem with the Windows path length limit which is 256 characters. **IMPORTANT**: *Don't* place the Zip file on the Windows desktop. Behind the scenes, this creates a very long path name.
   In the example below, the user created a folder on their C: drive named *Mesh101.* Next, they moved the downloaded Mesh Toolkit Zip file, which their system renamed *OneDrive_2023-07-24.zip*, to the *Mesh101* folder

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image006.jpg)
5. In the new folder you created, unzip the Toolkit file, and then
    navigate through the unzipped folder hierarchy until you see folders
    named **Packages** and **Samples**.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image007.png)

6. Open the **Samples** folder. The tutorial project, named
    **Mesh101.Unity**, is located there and is packaged as a Zip file.

7. Unzip the **Mesh101.Unity.zip** file into the **Samples** folder.
    This creates a **Mesh101.Unity** project folder which you'll open in
    Unity.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image008.png)

> [!IMPORTANT]
> Don't move the **Mesh101.Unity** project folder or the
> **Packages** folder after you unzip!

To ensure that the manifest file for the project (or any of the sample projects) configures project settings and loads the required packages correctly, you must maintain  this folder and file structure:

```bash
Mesh Toolkit 23.x

├──Packages
├──Samples
    ├──DartRoom
    ├──Mesh101.Unity
    ├──HelloWorld-Unity
    ├──ScienceBuilding
    ├──ScriptedWorlds
```

> [!TIP]
> One sign that packages weren't loaded properly is pink surfaces
> in your scene. Pink indicates that a material didn't load correctly. If
> this happens, check to ensure that the folder structure described above
> is correct.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image009.jpg)

### The Packages

For this tutorial, you don't need to install any packages---they're
already pre-loaded into the tutorial project. If you were creating your
own project from scratch, you would need to install the Mesh Toolkit
package. To learn more about this, see our article titled *Download the Mesh Toolkit*.

## Next steps

> [!div class="nextstepaction"]
> [Chapter 2: Prepare the project](mesh-101-02-prepare-the-project)
