---
title: Mesh Emulation Mode testing in Unity
description: Test your Mesh environment using Mesh Emulation Mode in Unity.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 1/19/2024
ms.topic: Guide
keywords: Microsoft Mesh, testing, troubleshooting, Mesh emulator, emulator, troubleshooting, debugging, Mesh Emulation Mode, emulation
---

# Mesh Emulation Mode testing in Unity

If you add the *Mesh Emulator* prefab (or, simply, the "Emulator") to your Unity project, you gain the ability to run the project in *Mesh Emulation Mode*. In this mode, when you press the Unity editor Play button, you get an approximate preview of what the content will look and feel like when it
runs in the Mesh app. This greatly speeds up the iteration cycle during
content development and allows developers of advanced interactive
content to deeply debug the logic with all the powerful tools that Unity
offers.

The look and feel in Mesh Emulation Mode is similar but not identical to the look and feel in
the Mesh app. We're continuously working to reduce the differences where
possible without sacrificing the lightweight environment necessary for
quick iteration. A key feature of Mesh Emulation Mode is the ability to run
multiple clients within the same process; this allows a single developer
to easily get a first impression of a multi-user scenario.

**To use Mesh Emulation Mode in your project (or not)**:

1.  Ensure that you have the Mesh toolkit imported.
1.  Ensure that the scene contains a piece of solid floor below the origin that's set to the *GroundCollision* layer.
1.  Press the Play button. The toolkit checks to see if a GameObject with "EmulatorSetup" in its name exists at the top level of the **Hierarchy**. If it doesn't, this dialog appears:

    ![A screenshot of the Mesh Emulator Setup missing dialog.](../../media/debug-and-optimize/003-emulator-setup-missing-dialog.png)

    Do one of the following:

    **To ensure that Mesh Emulation Mode runs every time you click Play**:  
    - Select the first button, **Add working MeshEmulatorSetup prefab.** The **MeshEmulatorSetup [NoUpload]** prefab appears in the **Hierarchy**.

    ![A screenshot of the Mesh Emulator Setup No Upload prefab added to the Hierarchy.](../../media/debug-and-optimize/004-mesh-emulator-in-hierarchy.png)

    **To avoid running the Emulator and prevent the "Emulator Setup missing" dialog from appearing again when you click Play**:  
    - Select the second button, **Add dummy NoMeshEmulatorSetup game object**. As the name suggests, this doesn't actually do anything, but the toolkit will find "EmulatorSetup" in its name and will refrain from showing you the **Emulator Setup missing** dialog again.

If you initially decide you don't want to use Mesh Emulation Mode, but change your mind later on, delete the **NoMeshEmulatorSetup [NoUpload]** GameObject from the **Hierarchy**. The next time you click Play, the toolkit will display the **Emulator Setup missing** dialog again, and you can click the button to add the Emulator.

## Teleport Player on Play

When working in a large scene, you may find it valuable to teleport the player to a specific location at startup. To achieve this:

1. In the **Hierarchy**, select **MeshEmulatorSetup [NoUpload]**.
1. In the **Inspector**, navigate to the **Mesh Emulator Setup** script.
1. In the **Teleport Player on Play** section, enter the **Position** and **Rotation** XYZ values you want the player to teleport to.

![A screenshot of the Mesh Emulator Setup component with the Teleport Player on Play section highlighted.](../../media/debug-and-optimize/005-teleport-player-on-play.png)

## Mesh Emulation Mode Split Screen

This feature lets you run multiple clients within the same process and
show them side-by-side within the same window. Mesh toolkit itself implements a very minimal emulated network component that's sufficient to communicate the player position between the clients, allowing the different players
to see each other as heavily stylized avatars:

![A screenshot of multiple clients displayed side-by-side in Mesh Emulation Mode.](../../media/debug-and-optimize/image043.png)

This is sufficient for previewing static content. When developing
interactive content, [visual scripting](../script-your-scene-logic/visual-scripting/visual-scripting-overview.md), [cloud scripting](../script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts.md) and/or [WebSlate](../enhance-your-environment/webcontent.md), keep in mind that those features each contain their own networking mechanisms
which provide a Mesh Emulation Mode preview of a synchronized experience with multiple users.

Do one of the following:

-   Increase the initial screen count before entering Play mode by setting the value in the **Mesh Emulator Setup** component:

![A screenshot of the Mesh Emulator Setup component with the Initial Screen Count property set to two.](../../media/debug-and-optimize/006-initial-screen-count.png)

-or-

1.  Start Play Mode.

2.  In the **DontDestroyOnLoad** scene, navigate to the
    **EmulatorSplitScreen** component and then select **Add screen**.

![___](../../media/debug-and-optimize/007-add-screen.png)

Now you can quickly test your Unity Scene without going through the
build and upload process each time you make an iteration.

 > [!IMPORTANT]
 > If you're using the [Visual Profiler](performance-guidelines.md#performance-profiler) in your scene, make sure the **Initial Screen Count** setting in the **Mesh Emulator Setup** component is zero. If it's "1" or higher, you won't see the Visual Profiler.

 ![A screen shot of the Mesh Emulator Setup component with Initial Screen Count set to zero.](../../media/debug-and-optimize/008-screen-count-zero.png)
