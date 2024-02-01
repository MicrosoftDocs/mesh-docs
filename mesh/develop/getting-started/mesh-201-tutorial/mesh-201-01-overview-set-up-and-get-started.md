---
title: Mesh 201 Overview, set up and get started
description: Learn about the prerequsites, set up, and then get started with the Mesh 201 tutorial project.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 1/31/2024
ms.topic: Tutorial
keywords: Microsoft Mesh, getting started, Mesh 201, tutorial, GitHub, WebSlates, web
---

# Mesh 201 Tutorial Chapter 1: Overview, set up and get started

If you completed the [Mesh 101 tutorial](../mesh-101-tutorial/mesh-101-01-overview-and-setup.md), you got up and running with creating a Mesh experience and gaining a solid understanding of Interactables, Physics, Visual Scripting, and more. In this tutorial, you build on that knowledge and learn how to use WebSlates to display web content in your experience. The tutorial includes an interactive globe; when an event attendee clicks on the globe, the coordinates (latitude and longitude) of the location they clicked are captured and added to a Bing Maps URL as parameters. An HTTP request is then made using that URL, and a map of the selected area is downloaded from Bing Maps to a nearby WebSlate. 

![A screenshot of a computer Description ](../../../media/mesh-201/066-attendees-at-globe.png)

The tutorial project is named *Mesh201* and is included in the Mesh toolkit.

> [!IMPORTANT]
> The tutorial project is governed by the MIT license as shown in the [LICENSE.txt](https://github.com/microsoft/Mesh-Toolkit-Unity/blob/main/LICENSE.txt) file in the *Mesh-Toolkit-Unity* repository. However, the samples functionality is dependent on the Mesh toolkit, which is governed by a separate license, and contains 3rd party software. A Teams Premium license is required for using the Mesh application for custom immersive spaces in Mesh on PC and Quest. A license isn't required to develop with the Mesh toolkit, but you'll be blocked from building and publishing Environments to Mesh and organizing or joining events in Mesh if you and your users don't have Teams Premium licenses. For more information, see [Set up M365 for Microsoft Mesh](../../../Setup/Content/setup-m365-mesh.md).

The tutorial is structured as follows:

- Chapter 1: Overview and setup *(this article)*

- [Chapter 2: Prepare the project.](./mesh-201-02-prepare-the-project.md)

- [Chapter 3: Load a local HTML file that's *not* shared.](./mesh-201-03-webslate-1.md)

- [Chapter 4: Load a local HTML file that *is* shared.](./mesh-201-04-webslate-2.md)

- [Chapter 5: Load a URL from a 3D asset.](<link>)

## Prerequisites

### Previous Unity experience

This tutorial assumes that you have the intermediate to advanced Unity skills needed to create an Environment. We also recommend that you have some familiarity with Unity Visual Scripting. A good place to learn Visual Scripting basics is through [Unity's Visual Scripting tutorial](https://learn.unity.com/project/introduction-to-visual-scripting). This teaches you most if not all of the concepts you need to get started with Mesh Visual Scripting. 

### Previous Mesh development with Visual Scripting *or* completion of the Mesh 101 tutorial

If you've been developing Mesh experiences for a while and are familiar not only with Unity Visual Scripting in general but also with some of the more common Mesh-specific Visual Scripting nodes, you can probably complete this tutorial successfully without first having gone through the Mesh 101 tutorial. If you have any doubt, we highly recommend that you complete the Mesh 101 tutorial. The following features were covered in the Mesh 101 documentation and are also included in this tutorial project but won't be covered again in the documentation. If you feel a need to understand these better, click the links.

[Turn object icons off for a clearer view](./mesh-201-02-prepare-the-project.md#turn-object-icons-off-for-a-clearer-view)

[Choose the right layer for objects with walkable or teleportable surfaces.](./mesh-201-02-prepare-the-project.md#choose-the-groundcollision-layer).

[Mesh Emulation Mode](./mesh-201-02-prepare-the-project.md#mesh-emulation-mode-capability)

[Mesh Thumbnail Camera](./mesh-201-02-prepare-the-project.md#add-the-mesh-thumbnail-camera)

### Hardware requirements

Minimum PC requirements: 4 CPU cores, 8GB RAM

### Unity version 2022.3.7f1

Unity version 2022.3.7f1 is required for this tutorial.

[Review system requirements for Unity](https://docs.unity3d.com/2022.3/Documentation/Manual/system-requirements.html)

[Get help installing Unity](https://docs.unity3d.com/hub/manual/InstallEditors.html)

Your installation should include modules for Android and Windows. The Mesh app works for PC and the Meta Quest 2, and Android is the operating system for the Quest.

## Set things up for Mesh

### Download the Mesh desktop app

Download Microsoft Mesh on PC
 
> [!div class="nextstepaction"]
> [Microsoft Mesh - Microsoft Store Apps](https://apps.microsoft.com/store/detail/microsoft-mesh/9NLXZJ1FDBD7)

![______](../../../media/mesh-201/067-get-started-developing-mesh.png)

### Download the Mesh Toolkit samples

1. In your browser, go to the [*Mesh-Toolkit-Unity* repository](https://github.com/microsoft/Mesh-Toolkit-Unity).

    ![______](../../../media/mesh-201/001A-toolkit-in-github.png)

    You can either clone the repo or download a Zip file of the Mesh Toolkit samples. Cloning the repo will probably take longer, but in the future, you can get the latest changes by updating the repo instead of downloading another Zip file. Note that we're not currently accepting code contributions to our samples. If you have any feedback or if you run into any issues with the samples or the Mesh toolkit, do the following: in a Unity project that has the Mesh toolkit package installed, select **Mesh Toolkit** > **Give feedback to Microsoft** and then use the feedback link in the Mesh toolkit to let us know.

**To download the Zip file**:

1. Select the **Code** button, and then select **Download ZIP**.

    ![______](../../../media/mesh-201/001B-code-and-download-zip.png)

1. We recommend that you create a folder on your C: drive named "Mesh Samples" and then move or copy the downloaded Mesh toolkit Zip file to that folder. This is a good name for two reasons: it's short, so it avoids running into a problem with the Windows path length limit, which is 256 characters. Also, the Zip file contains other Mesh samples in addition to the Mesh 201 tutorial, so all your samples are saved in one place.

    **IMPORTANT**: *Don't* place the Zip file on the Windows desktop. Behind the scenes, this creates a very long path name.

    In the example below, the user created a folder on their C: drive named *Mesh Samples.* Next, they moved the downloaded Mesh toolkit Zip file to the *Mesh Samples* folder.

    ![A screenshot of the downloaded samples zip file in the Mesh 201 folder.](../../../media/mesh-201/002-toolkit-folder.png)

1. Unzip the samples Zip file into the same folder, and then navigate through the unzipped folder hierarchy until you see the **Mesh201** folder. This contains the tutorial project which you'll open in the next chapter.

    ![A screenshot of a computer Description automatically generated](../../../media/mesh-201/003-mesh201-in-folder.png)

**To clone the repo**:

**Important**: If you plan to clone, you should have [Git LFS installed](https://git-lfs.com/).

1. Select the **Code** button, and then click the "Copy url to clipboard" button.

    ![A screenshot of a computer Description automatically generated](../../../media/mesh-201/068-copy-url.png)

1. We recommend that you create a folder on your C: drive named "Mesh Samples" and then clone the repo to that folder. This is a good name for two reasons: it's short, so it avoids running into a problem with the Windows path length limit, which is 256 characters. Also, there are other Mesh samples in addition to the Mesh 201 tutorial, so all your samples are located in one place.
1. In the newly created folder, create a Git repo and then clone the repo by pasting the copied URL after the *git clone* command in Git Bash and then pressing the Enter key.

    ![A screenshot of a computer Description automatically generated](../../../media/mesh-201/069-git-bash-with-clone-command.png)

### Mesh toolkit package

For this tutorial, the only package you need is the Mesh toolkit package, and it's already pre-loaded into the tutorial project. If you were creating your own project from scratch, you would need to [import the Mesh toolkit package](../../build-your-basic-environment/add-the-mesh-toolkit-package.md).

## Scenes in the project

1. Open the **Mesh201** project in Unity. If you have more than  one version of Unity installed, be sure to open the project with `Unity 2022.3.7f1` which is required for this tutorial.

    **WARNING**: The project could take 15 minutes or slightly longer to load due to large asset sizes. If you need to, change your Sleep mode setting so that the computer doesn't go to sleep while the project is loading. If this happens, it could cause the project to not load properly.
    
1. In the **Assets** folder, note that there are two scenes available: **Starting Point** and **Finished Project**.

    ![A screenshot of a computer Description ](../../../media/mesh-201/004-tutorial-scenes.png)

    **StartingPoint**: This is the scene you'll do the tutorial in. It
    contains a pre-built setting that includes the WebSlates and interative globe you'll be visiting and adding Mesh features to.

    **FinishedProject**: As the title implies, this scene contains an
    accurate completed version of the tutorial. You can refer to this at any
    time to confirm that you've completed tutorial steps in the
    *StartingPoint* scene correctly. Always save your work in the
    *StartingPoint* scene before switching scenes.

1. Open the **StartingPoint** scene.

## Explore the *StartingPoint* scene

Feel free to move around in the **Scene** window to get familiar with
the scene's contents. If we zoom out a little, we can see that the WebSlates we'll be updating are located on a GameObject called a *Sphere Terrace*. It contains a series of stations where you'll learn how to implement Mesh features for the WebSlates.

![A screenshot of a computer Description ](../../../media/mesh-201/008-sphere-terrace-wide-view.png)

## Next steps

> [!div class="nextstepaction"]
> [Chapter 2: Load a local non-shared HTML file into a WebSlate](./mesh-201-02-webslate-1.md)
