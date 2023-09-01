---
title: Mesh 101 Tutorial
description: Mesh 101 Tutorial.
author: typride
ms.author: vinnietieto
ms.date: 8/31/2023
ms.topic: Tutorial
keywords: Microsoft Mesh, M365, Immersive spaces, Avatars, getting started, documentation, features
---

# Mesh 101 Tutorial

Microsoft Mesh 101 Tutorial

![Graphical user interface, text Description automatically generated](../../../media/sample-mesh-101/image001.png)
A basic tutorial journey for building a Mesh Environment

# Welcome to the Mesh 101 tutorial

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

**Chapter 1: Set things up for Mesh**

- Download the Mesh desktop app

- Download the Mesh Toolkit

**Chapter 2: Prepare the tutorial project**

- Understand the two scenes

- Add the PlayModeSetup prefab

- Choose the NavMesh layer

- Add a Thumbnail Camera

**Chapter 3: Add interactivity with Mesh Scripting**

Learn how to update a script to enable the following:

- a button that a participant can click to cause an educational video
    to play

- a trigger volume that opens a customizable dialog that can be viewed
    by Event participants

- a button that teleports a participant to a different location in
    your Mesh environment

**Chapter 4: Move objects and trigger animations with Mesh Physics**

Learn how to add physics components to objects to enable the following:

- Make an object have "grab and move" capabilities

- Trigger an animation that plays when an object enters a trigger
    volume

- Create a containment field so objects can only be dropped in a
    certain area

**Chapter 5: Create your Environment and Upload it to Mesh**

Learn how to create an Environment based on your scene and then build it
and publish it to your World in the Azure Portal.

**Chapter 6: Share your Mesh experience with others**

Learn how to create an Event that's based on your Environment.
Participants can join the Event and then use the Mesh features that you
enabled in Chapters 3 and 4 to learn about wind turbines.

We hope this tutorial inspires you to build a Mesh solution for the use
cases your business finds valuable, with immersive environments, rich
interactivity, and meaningful content.

Terminology

In Mesh terms, the project you create in Unity and then upload to the
Azure Portal is called an *Environment*.

## Prerequisites

### Hardware requirements

Minimum PC requirements: 4 CPU cores, 8Gb RAM

### Unity version 2021.3.21f1

Unity version 2021.3.21f1 is required for this tutorial.

[Get help installing Unity](https://docs.unity3d.com/hub/manual/InstallEditors.html)

Your installation should include modules for Android and Windows.

Unity supports three IDEs: VS, VS Code, and JetBrains Rider. We
recommend Visual Studio, but other supported IDEs will work. You'll be
using this for Mesh Scripting.

**IMPORTANT**: Mesh Scripting requires Visual Studio *2022*, but Unity
2021.3.21f1 installs with Visual Studio *2019* by default. If you're
using Visual Studio, make sure you have version 2022 installed. To learn
more, see the [Unity documentation](https://learn.unity.com/tutorial/get-started-with-visual-studio-and-unity).

### Previous Unity experience

This tutorial assumes that you have intermediate to advanced Unity
skills.

### Azure portal access

You'll need a username and password for the Azure Portal so you can
upload your work.

#### Content Contributor permissions**

To upload an Environment to a Mesh world, there are two things that must
be enabled for your work account:

1. **Mesh world already created.** There must be a Mesh world to upload
    to from Unity. If there isn't one, your Azure Admin or Mesh world
    resource owner should make one for you.

2. **Content Contributor role.** Your Azure Admin or Mesh world owner
    must add your work account as a content contributor for each Mesh
    world you want to upload a template to.

For more information, see our document titled *Custom Worlds \-- IT
Admin Guide*.

## Mesh Scripting setup information

In order to use Mesh Scripting, which you'll do throughout Chapter 3,
you'll be creating and deploying a service called *MeshApp*. This
service contains the C# code that supports multiplayer interactivity and
is built and deployed automatically when you upload your Environment to
Mesh.

Make sure you have the following installed:

**[Azure CLI 2.40.0](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli).**

[**.NET 6.0 SDK Windows**](https://dotnet.microsoft.com/en-us/download/dotnet/6.0)

**To confirm that you have the Azure CLI installed:**

- Run the **az \--version** command. (Learn about [choosing the right Azure command-line tool](https://learn.microsoft.com/en-us/cli/azure/choose-the-right-azure-command-line-tool)).

**To confirm that you're logged in to the subscription where you have
permissions to deploy MeshApp's cloud infrastructure:**

- Run the **az account show** command. If you're not logged in to the
    correct subscription, run **az logout** and then **az login** to log
    in to the right account. If you have access to multiple Azure
    subscriptions in different tenants, it's easier to log in using the
    **az login \--use-device-code** command.

    > [!NOTE]
    > Switching Azure subscriptions/tenants using the Azure CLI resets your default subscription. To ensure that you update your default subscription if you switch tenants, use the **az account set -n "\<subscription-name>"** command. Example **: az account set -n "My Azure Subscription"**.

**Resource Group**

You'll need to select an Azure resource group for Mesh Scripting. This
is the resource group you intend to use to deploy MeshApp. You can do
one of the following:

- If you have subscription access privileges, let the project create a
    default resource group for you.

-or-

- Get contributor-level access to a specific resource group from your
    subscription admin and make a note of the name of this resource
    group.

**Subscription ID**

This is the subscription ID for your chosen resource group.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image002.jpg)

> [!IMPORTANT]
> The configuration of a subscription and resource group
> for the Mesh World that you'll publish your Environment to may or may
> not be the same as the configuration of a subscription and resource
> group for MeshApp.

## Chapter 1: Set things up for Mesh

### Download the Mesh desktop app 

To download the app (codenamed **Project Napili**), you can visit the link below.![](../../../media/sample-mesh-101/image003.png)

[Project Napili - Microsoft Store Apps](https://apps.microsoft.com/store/detail/project-napili/9P0B5VMS9RTQ?hl=en-us&gl=us)

**If the app isn't available, talk to your IT** **admin about making the
app visible to you.**

### Download the Mesh Toolkit

The Mesh Toolkit contains the *Mesh 101* tutorial project.

1. In your browser, navigate to the **Microsoft Mesh TAP Onboarding
    Resources** website:

[Microsoft Mesh TAP Onboarding Resources - Home (sharepoint.com)](https://microsoft.sharepoint.com/teams/MicrosoftMeshEAPOnboardingResources/?OR=Teams-HL&CT=1660599435162&clickparams=eyJBcHBOYW1lIjoiVGVhbXMtRGVza3RvcCIsIkFwcFZlcnNpb24iOiIyNy8yMjA4MDcwMTAwMCIsIkhhc0ZlZGVyYXRlZFVzZXIiOmZhbHNlfQ%3D%3D)

2. On the main page, scroll down to the **Mesh Resources and Developer
    Tools** section, and then, under **Get the Files and Packages**,
    select the **Go** button.

    ![A screenshot of a video game Description automatically generated](../../../media/sample-mesh-101/image004.jpg)

3. On the **Files and Packages** page, download the latest version of
    the Mesh Toolkit (select the three-dot button and then select
    **Download**).

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

```csharp
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

**The Packages**

For this tutorial, you don't need to install any packages---they're
already pre-loaded into the tutorial project. If you were creating your
own project from scratch, you would need to install the Mesh Toolkit
package. To learn more about this, see our document titled *Get Started
with Mesh Environments*.

## Chapter 2: Prepare the tutorial project 

### Scenes in the tutorial project

1. Open the **Mesh101.unity** project in Unity. If you have more than
    one version of Unity installed, be sure to open the project with the
    version required for this tutorial: Unity 2021.3.21f1.

    > [!NOTE]
    > In the **Assets** folder, there are two scenes available: **Starting Point** and **Finished Project**.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image010.png)

2. Open the **StartingPoint** scene. You should see the **TMP Importer** window.

3. Select **Import TMP Essentials**, and then close the window.

    ![A screen shot of a computer Description automatically generated with low confidence](../../../media/sample-mesh-101/image011.png)

    In the **Scene** window, the letter "T" appears over every object that
    contains Text Mesh Pro. You can turn these off to achieve a less
    cluttered view. To do so:

4. In the toolbar above the upper right corner of the **Scene** window,
    select the Gizmos drop-down.

5. In the **Scripts** section, scroll down to **TextMeshPro**, and then
    select its **icon** toggle button. This turns off the display of
    "T"s in the **Scene** window.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image012.png)

**About the scenes**

**StartingPoint**: This is the scene you'll do the tutorial in. It
contains a pre-built setting that includes the wind turbines and
stations you'll be visiting and adding Mesh features to.

**FinishedProject**: As the title implies, this scene contains an
accurate completed version of the tutorial. You can refer to this at any
time to confirm that you've completed tutorial steps in the
*StartingPoint* scene correctly. Always save your work in the
*StartingPoint* scene before switching scenes.

### Exploring the StartingPoint scene

Feel free to move around in the **Scene** window to get familiar with
the scene's contents. If we zoom out a little, we can see that there are
a number of wind turbines in our wind farm. Those two white rounded
items at the bottom of the window are called *Sphere Terraces*.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image014.jpg)

If you navigate to the front of the Sphere Terraces and take a closer
look, you can see that each Sphere Terrace contains a space inside that
you'll soon be walking around in.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image015.jpg)

You'll be visiting the Sphere Terraces starting in the next
chapter---they each contain a series of stations where you'll learn how
to implement Mesh features. The first Sphere Terrace (covered in Chapter
3) is where you'll learn about Mesh Scripting ...

![A screenshot of a video game Description automatically generated with medium confidence](../../../media/sample-mesh-101/image016.jpg)

... and the other Sphere Terrace, covered in Chapter 4, is where you'll
learn about Mesh Physics.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image017.jpg)

### Add the PlayModeSetup prefab

Adding the PlayModeSetup prefab will allow you to run the project in
*Playmode*. This gives you a preview of what the content will look and
feel like when it runs in the *Mesh app*. A key feature of Playmode is
the ability to run multiple clients within the same process; this allows
you to easily get a first impression of a multi-user scenario.

1. Right-click inside the **Hierarchy** and then, in the context menu, select **Mesh Toolkit** \> **PlaymodeSetup**.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image018.jpg)

    Note that this adds the **PlaymodeSetup \[ NoUpload\]** prefab to the
    scene.

    ![A screenshot of a computer Description automatically generated with
    medium confidence](../../../media/sample-mesh-101/image019.jpg)

    This prefab provides you with a highly stylized avatar that has a camera attached, so now we can play the project and have a look around.

    ![A picture containing screenshot, pc game, video game software,3d modeling Description automatically generated](../../../media/sample-mesh-101/image020.jpg)

2. Select the Unity Editor Play button.

3. In the **Game** window, note that you now have a view from the
    avatar's position. Use the WASD keys to walk around inside the
    Sphere Terrace. You can also drag the right mouse button to pan in
    any direction. When you're done experimenting, click the Unity
    Editor Play button again to exit Play mode.

## Check the scale of your GameObjects

The tutorial project uses default Unity scale values: 1 unit = 1 meter.
The *PlaymodeSetup* avatar is the same height as an average human. When
you're creating your own Environment, you can compare its size to any
custom GameObjects you add to your project to ensure that those objects
are the size you want.

## Add the Mesh Thumbnail Camera

Adding the Mesh Thumbnail Camera provides a thumbnail image that will be
added to your Environment's listing in the Azure Portal and its
selection button in the Mesh app. This comes in handy when you're
selecting Environments in either place because it gives you a visual
reminder of what the Environment looks like.

**To add the thumbnail camera to the scene and set its view:**

1. In the **Scene** window, adjust the view so that it shows what you
    want to display in the thumbnail (the Thumbnail Camera's view will
    be based on the **Scene** window).

2. Select the "+" drop-down located below the **Hierarchy** tab, and
    then select **Mesh Toolkit** \> **Thumbnail Camera**.

3. To confirm that the view in the Thumbnail Camera is what you want,
    in the **Hierarchy**, select **MeshThumbnailCamera**. The Camera's
    view appears in a small window in the lower right of the **Scene**
    window.

> **Note**: If you decide you want a different view for the Thumbnail
> Camera, you can adjust the Camera GameObject directly in the **Scene**
> window or change its **Position** and **Rotation** values in the
> **Inspector** prior to uploading your Environment to Mesh.

There are no set rules for how your thumbnail should look---it's totally
up to you. For the example below, we chose a close-up front view of a
wind turbine.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/imag021.jpg)

## Chapter 3: Add interactivity with Mesh Scripting

Now that we've completed the setup phase, let's move on to making your GameObjects interactive! In this chapter, we'll dive into Mesh Visual Scripting, which you can use to add custom logic to your Environment. 

> [!NOTE]
> - There are two types of Mesh Scripting: Mesh Cloud Scripting, which uses C# code, and Mesh Visual Scripting, where you create a Script Graph and then add nodes (also called *units*) in a sequence to create your coding logic. This version of the Mesh 101 tutorial uses Mesh Visual Scripting; the previous version used Mesh Cloud Scripting. 

> - Mesh Scripting isn't required for every Environment, but you'll need it for the features we'll be adding here: making a button interactive, triggering an informational text popup, and teleporting around the scene.

### Choose the NavMesh layer 

For this project, we want our avatar to be able to walk around only on
the floors inside the *Sphere Terrace* objects and the floor of a
platform that's attached to one of the wind turbine generators. For
these areas to be walkable, they must be on the *NavMesh* layer. Let's
add the *Sphere Terrace* in Chapter 3 to the NavMesh layer.

1. In the **Hierarchy**, expand the **Chapter 3** GameObject.

2. Select the **Sphere Terrace** GameObject that's a child object to
    the **Chapter3** GameObject.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image025.png)

3. In the **Inspector**, select the **Layer** drop-down and then choose
    **NavMesh**.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image026.jpg)

You don't have to add the other walkable GameObjects to the NavMesh
layer---we've already done it for you.

### Station 1: Create an Interactable Button

For our first task, we want to create a button that will play a video
when it's pressed by a participant.

- In the **Scene** window, navigate to the Sphere Terrace that
    contains the stations for Chapter 3, and adjust the view so that
    you're looking at the first station, **3.1 -- Video Playback**, as
    shown below.

![A screenshot of a video playlist Description automatically generated with low confidence](../../../media/sample-mesh-101/image029.png)

We already have a backplate for the button in the correct location in
our scene, but we need to build up the button a little more and add a
label to it. As the text box for the station explains, we'll create a
Script Graph with some button logic so that the button can be used to toggle the VideoPlayer on
and off and change the button text.

**Add the button to the scene**

1. In Unity, make sure the GameObject named **Chapter3** is expanded.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image036.jpg)

2. Search for the **ButtonBase** prefab.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image037.png)

3. Drag **ButtonBase** from the **Project** window and then, in the
    **Hierarchy**, drop it on the GameObject named **3.1 -- Video** so
    that **ButtonBase** is placed as a child to **3.1 -- Video**.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image038.png)

    Make sure the **Transform** \> **Position** values for **ButtonBase** are 0, 0, 0.

**ButtonBase** is placed in the scene a little lower than where we want it.

![A picture containing text, screenshot, multimedia software, software Description automatically generated](../../../media/sample-mesh-101/image039.png)

Let's fix that.

1. Ensure that **ButtonBase** is selected in the **Hierarchy**.

2. In the **Inspector**, change the **Transform** \> **Position** \>
    **Y** value to "1".

Perfect! Now **ButtonBase** is correctly located just in front of the **BackplateBase** object.

![A screenshot of a video play Description automatically generated with medium confidence](../../../media/sample-mesh-101/image040.jpg)

**Rename the button**

- With **ButtonBase** selected, in the **Inspector**, change the name
    of **ButtonBase** to "PlayVideoButton".

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image042.png)

**Change the label of the button**

Right now, the text on the button says "Label." Let's change that to
"Play."

1. In the **Hierarchy**, expand the **PlayVideoButton** GameObject to
    display its child objects, and then select the **Label** child
    object.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image043.jpg)

2. In the **Inspector**, navigate to the **TextMeshPro -- Text**
    component, and then, in the **Text Input** box, change the text to
    "Play."

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image044.jpg)

## Create the Visual Script for the button

1. In the **Hierarchy**, select *VideoPlayer*.
1. In the **Inspector**, click **Add Component**, and then select **Script Machine**.

Note that two new components have been added in the **Inspector**: **Script Machine** component and **Variables.**

<image>

There's also a new window named *Mesh Visual Scripting Diagnostics* in the **Inspector**. This will give you feedback on your visual script and can be useful for troubleshooting.

<image>

1. In the **Script Machine** component, click the **New** button.

<image>

1. Navigate to the "StartingPointVisualScripts" folder.
1. In the **Save Graph** dialog, enter the name "SPVideoPlayerBehavior" and then click **Save**.





## Test your work

1. In your code editor, make sure *App.cs* is saved.

2. In Unity, save the project and then press the Unity Editor Play
    button.

3. In the **Game** window, click the **Play** button you just worked
    on. This causes a brief video about wind turbines to play on the
    screen above the button.

    ![A screenshot of a video playback Description automatically generated with medium confidence](../../../media/sample-mesh-101/image045.jpg)

4. When you've finished watching the video, press the button you've
    been editing again (it now has the label "Stop").

5. Press the Unity Editor Play button to exit Play mode.

## Station 3.2: Trigger an info dialog

For this task, we'll add some code to a script that causes an info dialog to appear when an avatar steps onto a platform. Note that the dialog is triggered when the user steps *into* a trigger volume located *above* the platform---the platform itself doesn't trigger anything. This is detailed further in step #3 below.

1. In the **Hierarchy**, collapse the **3.1 -- Video** GameObject.
   In the **Scene** window, note that the Info Dialog Trigger station is to the right of the **3.1 -- Video Playback** station. Adjust the view so that you can clearly see Station 3.2.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image046.jpg)

2. In the **Inspector**, expand the GameObject named **3.2 -- Info
    Dialog**.

3. Select the **Proximity Trigger** child object. As the name implies,
    this has been set up as a trigger volume located above the platform
    which avatars will be stepping on. We just need to add the code to
    make it work.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image047.jpg)

4. Copy the following code to the Windows Clipboard:


    ```csharp
    // Subscribe to trigger entered events. All code within the statement lambda will be executed when an avatar enters the trigger.
    trigger.Entered += (_, args) =>
    {
    _app.ShowMessageToUser("Did you know that the world's largest wind turbine has blades longer than a football field?", args.Avatar.User);
    };
    ```

5. In your code editor, open the *App.cs* file if it's not already
    open.

6. Navigate to the section named Chapter 3.2.

7. Replace the "Paste code here" comment with the code you copied and
    save the file.

    ![A close-up of a text Description automatically generated](../../../media/sample-mesh-101/image048.jpg)

    Take a moment to read the message that you expect to display: "Did you know that the world's largest wind turbine has blades longer than a football field?"

## Test your work

1. In the Unity Editor, save the project and then press the Unity
    Ewditor Play button.

2. Use the navigation keys to make your avatar walk onto the platform.
    **TIP**: You may want to tilt the view up a bit so you can keep the
    platform iwn view as you walk towards it.

    ![A screen shot of a video game Description automatically generated with low confidence](../../../media/sample-mesh-101/image049.jpg)
    
    Stepping onto the platform (which coincides with stepping *into* the trigger volume) causes an info dialog that displays a message to appear. The message is the one that you added to the script.
    
    > [!NOTE]
    > The info dialog in the image will look different in the Mesh app.
    
    ![A screenshot of a video game Description automatically generated](../../../media/sample-mesh-101/image050.jpg)

3. When you've finished viewing the message, click its **Okay** button.

4. Press the Unity Editor Play button to exit Play mode.

## Station 3.3: Teleport to the turbine generator

For this task, we'll add some code to a button that allows participants
in the scene to teleport. When a participant presses the button, they're
teleported from their current location at Station 3.3 to an elevated
platform that's attached to a wind turbine generator. They can then
examine the generator.

![A picture containing outdoor, text, screenshot, windmill Description automatically generated](../../../media/sample-mesh-101/image051.jpg)

**Update the script**

- In the **Scene** window, note that the **3.3 -** **Teleport to
    Turbine** station is to the right of the **3.2 -- Info Dialog
    Trigger** station. Adjust the view so that you can clearly see
    Station 3.3.

    ![A screen shot of a computer Description automatically generated with low confidence](../../../media/sample-mesh-101/image052.jpg)

The button is all set up for you---we just need to add the code that
gives it the teleport behavior.

1. Copy the following code to the Windows Clipboard.

// When the button is clicked teleport the user who pressed the button
to the destination node\'s position and orientation.

scene.GetAvatarForUser(e.User)?.TeleportTo(GetWorldPosition(destination),
GetWorldForward(destination));

2. In your code editor, go to the *App.cs* file and then navigate to
    the section named *Chapter 3.3*.

3. Paste the code you just copied into the if statement inside the
    first Try-Catch block, replacing the "Paste code here" comment, and
    then save the file.

![A computer code with red line Description automatically
generated](../../../media/sample-mesh-101/image53.png){width="6.75in"
height="1.9666666666666666in"}

4. In Unity, save the project and then press the Unity Editor Play
    button.

**Teleport up to the wind turbine generator**

1. Use the navigation keys to make your avatar walk up to the
    **Teleport** button, and then press the button.

    ![A screenshot of a video game Description automatically generated with medium confidence](../../../media/sample-mesh-101/image054.jpg)
    
    This teleports you up to the platform that's attached to the wind
    turbine's generator.
    
    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image055.jpg)
    
    Note the information box on the side of the generator that says **3.3 --
    Generator**.

2. Walk up to a position just to the right of information box. The box
    tells you that you can click the **Show/Hide Generator** button to
    show and hide the internals of the wind turbine by animating a
    ClippingSphere.

    ![A picture containing text, computer, screenshot, software Description automatically generated](../../../media/sample-mesh-101/image056.jpg)

3. Select the button. You're supposed to see a window open in the side
    of the turbine so you can look inside, but nothing happens. That's
    because we haven't yet added the code to our script that enables
    this functionality. Let's do that now.

4. Press the Unity Editor Play button to exit Play mode.

> **Add the code to show the generator**

1. Copy the following code to the Windows Clipboard:

    ```csharp
    // When the button is clicked find the ClippingSphereAnimator.
    
    var animator = scene.FindFirstChild\<ClippingSphereAnimator\>(true);
    
    if (animator != null)
    
    {
    
    // If the animator is currently idle or scaling out then start the scale
    in animation and update the button text.
    
    if (animator.CurrentBaseLayerState ==
    ClippingSphereAnimator.BaseLayerState.Idle \|\|
    
    animator.CurrentBaseLayerState ==
    ClippingSphereAnimator.BaseLayerState.ClippingSphereScaleOut)
    
    {
    
    animator.CurrentBaseLayerState =
    ClippingSphereAnimator.BaseLayerState.ClippingSphereScaleIn;
    
    showGeneratorButton.LabelText = \"Hide Generator\";
    
    }
    
    else // Else start the scale out animation and update the button text.
    
    {
    
    animator.CurrentBaseLayerState =
    ClippingSphereAnimator.BaseLayerState.ClippingSphereScaleOut;
    
    showGeneratorButton.LabelText = \"Show Generator\";
    
    }
    
    }
    ```


2. In your code editor, go to the *App.cs* file. You should already be at the section named *Chapter 3.3*.

3. Paste the code you just copied between the braces for the **ShowGeneratorButton.Clicked** statement lambda, replacing the
    "Paste code here" comment, and then save the file.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image057.jpg)

4. In the Unity Editor, save the project and then press the Unity Editor Play button.

5. Go to Station 3.3 and then teleport up to the wind turbine generator.

6. In the **3.3 -- Generator** information box, select the **Show/Hide
    Generator** button. This time, the ClippingSphere animation works,
    the window opens up, and you can see the wind turbine's generator.

    ![A computer screen shot of a machine Description automatically generated with medium confidence](../../../media/sample-mesh-101/image058.jpg)

    Feel free to step up close to the generator and have a look. It's pretty
    cool! When you've finished, navigate back out and then press the
    **Show/Hide Generator** button. This closes the window.

**Go to Chapter 4**

At this point, the participant in the experience would be ready to move
on to Chapter 4 and learn about wind turbine activities related to
physics. Just like with Chapter 3, there's a Sphere Terrace that
contains the stations for Chapter 4. To get there:

1. Rotate around in the opposite direction from the wind turbine
    generator and walk towards the **3.3 -- Go to Chapter 4**
    information box.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image059.jpg)

2. Press the **Teleport to Chapter 4** button.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image060.jpg)

    As advertised, this places the avatar in front of the stations for Chapter 4 and Mesh Physics.

    ![A picture containing text, screenshot, multimedia software, graphics software Description automatically generated](../../../media/sample-mesh-101/image061.jpg)

3. Press the Unity Editor Play button to exit play mode.

## Summary

In this chapter you added Mesh features that empower participants in
your experience to do the following:

1. Press a button that causes an educational video about wind turbines
    to play.

2. Step onto a platform that triggers the display of an info dialog
    about wind turbines.

3. Press a button that teleports the participant from the ground up to
    a platform attached to a wind turbine generator, where they can
    examine the generator up close.

# Chapter 4: Move objects and trigger animations with Mesh Physics

In Chapter 4, you'll work with a model of the wind farm. You'll learn
how to use Mesh Physics to grab and release Rigidbodies (in this case,
wind turbines) and set up an animation trigger. You'll wrap things up by
constraining the wind turbines so they can only be moved within a
specified area.

This chapter is a little more straightforward than what you did in
Chapter 3---there's no scripting, and all the networking is done for
you, which means that the physics will look the same to all avatars in
the session.

There are a couple of things we need to do before getting started with
the first station.

## Reconfigure the Hierarchy

- In the **Hierarchy**, collapse the **Chapter3** GameObject and then
    expand the **Chapter4** GameObject.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image062.jpg)

## Add the Physics Scene Setup component

1. In the **Hierarchy**, select the **Chapter4** GameObject.

2. In the **Inspector**, select the **Add Component** button, and then
    add the **Physics Scene Setup** component.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image063.jpg)

> This component ensures that all physics components contained in child
> objects of **Chapter4** are synchronized correctly.

## Change the view to display the Chapter 4 Sphere Terrace

In the experience in Mesh, the participant will move smoothly from the
end of Chapter 3 to the beginning of Chapter 4 and will be properly
located to begin the Chapter 4 learning activities. However, when you
exited Play mode at the end of Chapter 3, you were *not* automatically
placed with a view to the Chapter 4 model in the **Scene** window. Let's
set up that view.

1. In the **Hierarchy**, select the GameObject named **4.1 -- Grab and
    Release**.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image064.jpg)

2. Move the cursor over the **Scene** window and then press the F key
    on your keyboard.

> This centers the view on the **4.1 -- Grab and Release** object, but
> you'll most likely not be in quite the position we need.

3. Drag, rotate and/or zoom the view until you see the model in front
    of you, as shown below.

![A computer generated image of a model of a mountain Description automatically generated](../../../media/sample-mesh-101/image065.jpg)

## Station 4.1: Grab and Release

The goal for the participant in this chapter of the training is to move
wind turbines from the tabletop to the ocean. Once located there, the
turbines will catch the ocean wind, making their blades turn and
generating power.

1. In the **Hierarchy**, expand the **4.1 -- Grab and Release**
    GameObject. Note that it contains three Wind Turbine GameObjects
    that are located on the tabletop in the scene.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image066.jpg)

> Let's add "grab and release" capabilities to **WindTurbine1** so that
> participants will be able to move it around in Mesh.

1. In the **Hierarchy**, select **WindTurbine1** -- note in the
    **Scene** window that it's the one farthest in the back and has red
    blades.

2. In the **Inspector**, select the **Add Component** button and select
    **Force Tool Config**.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image067.jpg)

This component tags the object as something that can be picked up or
manipulated.

3. In the **Rigidbody** component, expand the **Constraints** option if
    needed, and then for the **Freeze Rotation** settings, select **X,**
    **Y**, and **Z**.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image068.jpg)

This will prevent the turbine moving tipping over if you place it on an
uneven surface.

## Test your work

1. Save the project and then select the Unity Editor Play button.

> Note that whenever you enter Play mode, your starting point in the
> **Game** window is the Chapter 3 Sphere Terrace. We want to be in the
> other Sphere Terrace---the one for the Chapter 4 features.
> Fortunately, there's an easy way to get there.

2. Rotate the view to the right until you see the **Go to Chapter 4**
    information box.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image069.jpg)

3. Walk up to the information box and then select the **Teleport to
    Chapter 4** button.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image070.jpg)

4. After you arrive at the Chapter 4 Sphere Terrace, move the cursor
    over **WindTurbine1** until the cursor's shape changes, and then
    drag the turbine around the scene and drop it in the ocean.

> The turbine will stay upright as a result of turning on its *Freeze
> Rotation* constraints. Notice that the wind is blowing, but the
> turbine's blades don't turn. This is because we haven't triggered the
> blade-turning animation yet. We'll do that at the next station.

![A picture containing text, screenshot, graphics software, multimedia
software Description automatically generated](../../../media/sample-mesh-101/image071.jpg)

5. Click the Unity Editor Play button to exit Play mode.

You don't need to update the other two wind turbines---we've already
done that for you.

## Station: 4.2 Animation Trigger

**Add the component**

- In the **Hierarchy**, expand the **4.2 -- Animation Trigger**
    GameObject, and then select its child object named **Animation
    Trigger**.

![A screenshot of a computer program Description automatically generated with medium confidence](../../../media/sample-mesh-101/image072.jpg)

As the name suggests, **Animation Trigger** is a trigger volume.

![A computer screen shot of a video game Description automatically generated](../../../media/sample-mesh-101/image073.jpg)

Our goal here is to set up **Animation Trigger** so that when a wind turbine enters it, an animation is triggered that causes the turbine's blades to spin in response to the ocean wind. To make this happen, the **Animation Trigger** GameObject must contain a component called **Trigger Sensor Events** for each of the three wind turbines. Note that, in the **Inspector**, there are already two **Trigger Events Sensor** components set up---these are for **WindTurbine2** and **WindTurbine3**. To see these, expand the **Body Filter** options.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image074.jpg)

Your task here will be to add and configure the **Trigger Events Sensor** component for **WindTurbine1**.

- In the **Inspector**, select the **Add Component** button and then
    choose **Trigger Events Sensor**.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image076.jpg)

**Choosing settings in the Trigger Events Sensor component**

In the **Trigger Events Sensor** component you just added, note its
**Body Filter** option. Any GameObject that enters a trigger volume in
its default state is eligible to trigger entry and exit events subject
to the **Trigger Type** setting. You can use the **Body Filters**
setting to make only GameObjects that meet certain conditions eligible
for triggering events. We want the **WindTurbine1** GameObject to
trigger an event here, so let's add that to the **Body Filter**.

1. Select the "+" button for **Body Filter** and then, in the popup
    menu, select **Root Game Object**.

![A screenshot of a computer Description automatically
generated](../../../media/sample-mesh-101/image077.jpg)

2. Drag the **WindTurbine1** GameObject from the **Hierarchy** to the
    **Trigger Events Sensor** component and then drop it in the **Root
    Game Object** box.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image078.jpg)
    
    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image079.jpg)
    
    You can also click the round button in the **Root Game Object** field and then search for and add **WindTurbine1** using the **Select GameObject** dialog.

3. Select the "+" button for the **On Trigger Enter** option, and then,
    in the popup menu, select **Toggle Component**.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image080.jpg)

4. In the **Hierarchy**, expand the **WindTurbine1** and
    **WindTurbineBody** GameObjects.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image81.jpg)

5. Drag the **Windmill_Turbine_001:Propellors10** GameObject from the
    **Hierarchy** to the **Trigger Events Sensor** component and then
    drop it in the **On Trigger Enter** \> **Toggle Component** \>
    **Game Object** field.

    ![A screenshot of a computer program Description automatically generated with medium confidence](../../../media/sample-mesh-101/image082.jpg)

6. Select the **On Trigger Enter** \> **Toggle Component** \>
    **Component** drop-down and then choose **Animator**.

7. Note that the **On Trigger Enter** \> **Enable or Disable** option
    is set to **Enable**. Leave it at that setting.

8. Select the "+" button for the **On Trigger Exit** option, and then,
    in the popup menu, select **Toggle Component**.

9. Drag the **Windmill_Turbine_001:Propellors10** GameObject from the
    **Hierarchy** to the **Trigger Events Sensor** component and then
    drop it in the **On Trigger Exit** \> **Game Object** field.

10. Select the **On Trigger Exit** \> **Toggle Component** \>
    **Component** drop-down and then choose **Animator**.

11. Select the **On Trigger Exit** \> **Enable or Disable** drop-down
    and then select **Disable**.

## Test your work

1. Save the project, and then press the Unity Editor Play button.

2. As noted earlier, entering Play mode places your avatar in the
    **Chapter3** Sphere Terrace. Rotate the scene to the right, and then
    walk over to the **Teleport to Chapter 4** button and press it.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image070.jpg)

3. Now in the **Chapter4** Sphere Terrace, drag **WindTurbine1**
    (reminder: it's the furthest one in the back) over the ocean. Note
    that the turbine's blades are now spinning. It looks like this is
    caused by the ocean wind, but, of course, the blades actually spin
    because as soon as the turbine enters the trigger volume which is
    located over the ocean, the blade-spinning animation is triggered.

    ![A picture containing screenshot, 3d modeling, pc game, video game software Description automatically generated](../../../media/sample-mesh-101/image083.jpg)

4. When you've finished observing the animation, press the Unity Editor
    Play button to exit Play mode.

As mentioned earlier, you don't have to update the other wind turbines---we've already done it for you.

## Station 4.3: Constraining Bodies

Right now, there's no constraint on where a participant can drop a wind
turbine. The goal is to place the turbines in the ocean so they catch
the wind, but a participant could, for example, accidentally drop a
turbine on the floor. We want to avoid this, so to ensure that the
turbines can only land on the tabletop or in the ocean, we can set up a
containment field. This is basically a transparent box---the turbines
will be restricted to the inside of the box.

![A screenshot of a video game Description automatically generated with
medium confidence](../../../media/sample-mesh-101/image084.png)

1. In the **Hierarchy**, expand the **4.3 -- Constraining Bodies**
    GameObject and select its child object named **Containment Field**.

![A screenshot of a computer Description automatically
generated](../../../media/sample-mesh-101/image085.jpg)

2. In the **Inspector**, select the **Add Component** button and then
    add the **Containment Field** component.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image086.jpg)

3. In the **Containment Field** component, select the "+" button to the
    right of the **Affected bodies** option, and then, in the popup
    menu, select the **Game Object Name** condition.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image087.png)

4. In the **Starts With** box, type "WindTurbine." Since all three wind
    turbines in our scene start with "WindTurbine," they'll all be
    restricted to the **Containment Field**.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image088.png)

5. Save the project, and then press the Unity Editor Play button.

6. As noted earlier, entering Play mode places your avatar in the
    **Chapter3** Sphere Terrace. Rotate the scene to the right, and then
    walk over to the **Teleport to Chapter 4** button and press it.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image070.jpg)

7. Now in the **Chapter4** Sphere Terrace, grab one of the wind
    turbines and drag it around in the scene. Try to drag it away from
    the tabletop and ocean and drop it on the floor. The containment
    field prevents you from doing so.

## Summary

In this chapter, you added Mesh features that empower participants in
your experience to do the following:

- Grab and move an object

- Trigger an animation when the participant drags an object into a
    trigger volume

- Drop an object only in a particular area that you specified

# Chapter 5: Create and upload your Environment 

You've completed adding all the features you need for your Mesh
experience using Mesh Physics and Scripting. So far, we've been working
in a Unity *project*; now you'll turn the *StartingPoint* scene into a
Mesh *Environment* and upload it to your Mesh World in the Azure Portal.

**Configure your project settings and sign in**

1. On the menu bar, select **Mesh Toolkit** \> **Configure** \>
    **Project Settings**.

    ![A screenshot of a computer Description automaticallygenerated](../../../media/sample-mesh-101/image089.png)

2. Select **Yes** to configure project settings for Mesh.

    ![Graphical user interface, text, application Description automatically generated](../../../media/sample-mesh-101/image090.png)

3. On the menu bar, select **Mesh Toolkit** \> **Environments**.

4. In the **Mesh Environments** window, select **Sign In**.

Sign in with your account. **Note**: As mentioned in the Prerequisites
section, the account must have Content *Contributor* access to the Mesh
World you're uploading the Environment to.

## Create your environment

1. Make sure you're in the **Create** **Environment** tab, and then, in
    the **Internal Name** field, type "Wind Turbine Tutorial."

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image091.png)

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

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image092.png)

6. Select **Create Asset** to create the Environment that you'll be
    uploading to the Azure Portal.

7. You'll receive a confirmation dialogue as shown below. Select
    **Close**.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image093.jpg)

## Build and publish your environment

You should now be in the **Update Environment** tab of the **Mesh
Environments** window.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image094.jpg)

> [!NOTE]
> > in the **Environment Configurations** section, a new
> > Environment configuration has been created that displays the name you
> > added in the **Create Environment** tab: *Wind Turbine Tutorial*. If
> > you see any other Environment configurations, close them.

- Select **Include Thumbnails**. Leave the setting as **Generate
    Thumbnails**.

    ![](../../../media/sample-mesh-101/image095.jpg)

## Building for single and multiple platforms

It's good to keep in mind that Mesh events can be experienced on two
different platforms: desktop PC and Android, which powers the Meta Quest
headset. Since desktop PCs typically have far more power than mobile
devices using Android, when you're creating your own project, there are
several potential scenarios to consider: build and publish your scene
for PC only, Android only, or both PC and Android. This tutorial follows
option #3: build and publish for PC and Android. To learn more about
building for single and multiple platforms, see our document titled *Get
Started with Mesh Environments*.

## Create the Environment 

1. In the **Update Environment** tab, click the **Select a scene**
    field, and then, in the **Select SceneAsset** dialog, select
    **StartingPoint**.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image096.jpg)

In the **Build for Platforms** section, you choose which platforms to
build for. Note that when a button background is gray, the button is
"on"; when the background is black, the button is "off." We're building
for both PC and Android, so make sure that both buttons are "on."

![A screen shot of a computer Description automatically generated with low confidence](../../../media/sample-mesh-101/image097.jpg)

## Build and publish your Environment

1. In the **Publish** section, provide some information in the **Upload
    notes** box if you wish.

- Select the **Build and Publish** button.

![A screen shot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image098.png)

- If the Environment builds and uploads successfully, the **Build and
    Upload Results** dialog appears and confirms the results.

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image099.png)

    If the build and upload process fails, this is confirmed in the **Build and Upload** **Results** dialog.

## Test the PC version of your Environment

In the **Build and Upload Results** dialog, select the left button under
**Published Asset**. This opens the Environment in the Mesh App.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image100.jpg)

## View your Environment in Azure

If you navigate to the **Environments** page for your World in the Azure
Portal, you'll see that your Environment has been saved there. Its type
will be listed as "Custom Environment."

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image101.png)

Your saved custom Environment will be available to anyone who creates a
new event in that Mesh world.

## Summary

In this chapter, you learned how to create an Environment based on your
scene and then build it and publish it to your World in the Azure
Portal.

# Chapter 6: Share your Mesh experience with others 

Now that you\'ve uploaded your Mesh101 Environment to Mesh, you can
create and produce an Event based on that Environment that participants
can experience through the Mesh app for PC or Quest. 

See our document titled *Mesh Event Producer Guide* to create an Event
via the in-app event producer experience.  

## Create an event 

1. Open the Mesh app and then log in.

2. In the left-side vertical button bar, click the icon for your World,
    or click the ["All Worlds" button](#_Mesh_dashboard_overview) at the
    bottom left, and then select the world you want.

    ![A blue square with white text Description automatically generated](../../../media/sample-mesh-101/image102.png)

> **Notes**:

- You may have to scroll to view all the worlds.

- You can pin worlds to the left nav bar for easy access.

![A picture containing text, screenshot, line, font Description
automatically generated](../../../media/sample-mesh-101/image103.png)

3. In your Mesh World, select the **Manage** button.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/sample-mesh-101/image104.jpg)

    > [!NOTE]
    > If you don't see the **Manage** button, then you aren't a [Content contributor](#_Content_contributor_permissions) for this World.

4. Select the **Create** button, and then, in the drop-down menu,
    select **Create event**.

5. Add your event details (**Name**, **Date**, **Time**,
    **Description**, etc.).

    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image105.jpg)

6. When you're finished, click **Next**.

7. On the **Template** page, press **Skip**.

8. On the **Environment** page, select the **Custom** tab.

9. Find the **Wind Turbine Tutorial** Environment, then select it, and
    then click **Next**.\
    \
    ![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image106.jpg)

10. On the **Review** page, review your event details. Click **Back** if
    you need to go back and change anything.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image107.jpg)

11. When you're ready to move forward, select **Create Event**. This
    saves your event and takes you to the **My Events** page.

![A screenshot of a computer Description automatically generated](../../../media/sample-mesh-101/image108.jpg)

## Summary

In this chapter, you learned how to create an Event that's based on your
Environment. Participants can join the Event and then use the Mesh
features that you enabled in Chapters 3 and 4 to learn about wind
turbines.

![A person looking at a group of people Description automatically generated](../../../media/sample-mesh-101/image109.png)

# Conclusion

Congratulations! Now that you've learned some of the basics of Mesh, you
can create a Unity project using your own 3D assets and build a
collaborative Mesh experience that best fits your business goals.
