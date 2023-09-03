---
title: Creating a new Unity project for your Mesh experience
description: Learn how to create a new Mesh project in Unity.
author: typride
ms.author: vinnietieto
ms.date: 8/25/2023
ms.prod: mesh
ms.topic: How to
keywords: Microsoft Mesh, Unity, M365, Immersive spaces, Avatars, getting started, documentation, features
---

# Creating a new Unity project

An easy way to start creating a Mesh experience is to [open an existing sample](TBD) and build from there. If you know what you want to build and prefer to start from scratch, this article will get you started. You can add your own content to the scene and then upload it as an *Environment* to Mesh.

1. Create a new Unity project using the **3D URP** (Core) template.

![Rectangle Description automatically generated with low
confidence](../../../media/get-started-developing-mesh/image008.png)

2. In Unity, create a new scene using the **Standard (URP)** scene
    template. Save it with an appropriate name.

3. In the **Hierarchy**, delete **Global Volume**.

4. Add content to the scene.

**Notes**

- For tips on maximizing your creativity here, see our document named
    "Mesh 3D Design and Performance Guide". There are also guides for
    implementing advanced features such as Mesh Physics and Scripting.

- **IMPORTANT**: Every scene in your project requires a NavMesh so
    that the user can navigate using teleport. [Learn more about the
    NavMesh](https://docs.unity3d.com/Manual/nav-Overview.html).

- Environments can't depend on any scripts that aren't included in the Mesh Toolkit Uploader package. This includes scripts you've added to the project manually or ones obtained by installing other packages.

- If you get a dialogue asking you to configure project settings, confirm to ensure these items show up in the Menu bar.

Next Steps:
Building for single and multiple platforms TBD