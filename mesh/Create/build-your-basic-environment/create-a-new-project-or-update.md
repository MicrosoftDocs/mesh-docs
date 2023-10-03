---
title: Creating a new Unity project for your Mesh experience
description: Learn how to create a new Mesh project in Unity.
author: typride
ms.author: vinnietieto
ms.date: 9/12/2023
ms.prod: mesh
ms.topic: How to
keywords: Microsoft Mesh, Unity, M365, Immersive spaces, Avatars, getting started, documentation, features
---

# Create a new project or update an existing one

An easy way to start creating a Mesh experience is to [open an existing sample](../../getting-started/choose-your-journey.md) and build from there. If you know what you want to build and prefer to start from scratch, this article will get you started. You can add your own content to the scene and then upload it as an *Environment* to Mesh.

> [!IMPORTANT]
> In rare instances, after you update the Toolkit package, your Unity project may become unexplainably and temporarily broken. This can result in mysterious compiler errors and missing script references despite the script file being present and clean. The steps to resolve this are:
> 1. Close and restart Unity.
> 1. If this doesn't work, in the Unity menu bar select **Assets** then **Reimport All**. *Note that this process can take some time.*

**To create a new project**:

1. Create a new Unity project using the **3D URP** (Core) template.

    ![A screenshot of the 3D URP Core template option when you create a new Unity project.](../../media/get-started-developing-mesh/image008.png)

1. In Unity, create a new scene using the **Standard (URP)** scene
    template. Save it with an appropriate name.

1. In the **Hierarchy**, delete **Global Volume**.

1. > [Import the Mesh Toolkit](import-the-mesh-toolkit.md)

**To update an existing project**:

- > [Import the Mesh Toolkit](import-the-mesh-toolkit.md)

**Notes**

- For design tips, see our series of design articles starting with [Designing for Mesh: Overview](../../Create/design/overview.md). There are also guides for implementing advanced features such as [Mesh Physics](../../Create/enhance-your-environment/physics-interactions.md) and [Mesh Scripting](../../Create/script-your-scene-logic/mesh-scripting-overview.md).

- **IMPORTANT**: Every scene in your project requires a NavMesh so that the user can navigate using teleport. [Learn more about the NavMesh](https://docs.unity3d.com/Manual/nav-Overview.html).

- Environments can't depend on any scripts that aren't included in the Mesh Toolkit Uploader package. This includes scripts you've added to the project manually or ones obtained by installing other packages.

- If you get a dialogue asking you to configure project settings, confirm to ensure these items show up in the Menu bar.

## Add a TravelPoint

Every scene must have at least one TravelPoint, which is used to configure avatar spawning behavior. If you're new to TravelPoints, we recommend that you [read our TravelPoint and TravelGroup documentation](../enhance-your-environment/object-avatar-interactions.md#travelpoint-and-travelpointgroup) and follow the instructions there. When you're finished, continue on with the article named [Building for single and multiple platforms](build-for-single-and-multiple-platforms.md).



