---
title: Create a new Unity project for your Mesh Experience
description: Learn how to create a new Mesh project in Unity.
author: typride
ms.author: vinnietieto
ms.date: 10/20/2023
ms.service: mesh
ms.topic: How to
keywords: Microsoft Mesh, Unity, M365, Immersive spaces, Avatars, getting started, documentation, features
---

# Create a new project or update an existing one

An easy way to start creating a Mesh experience is to [open an existing sample](../getting-started/choose-your-journey.md) and build from there. However, if you know what you want to build and prefer to start from scratch, this article will get you started. You can add your own content to the scene and then upload it as an *Environment* to Mesh.

> [!IMPORTANT]
> In rare instances, after you update the Toolkit package, your Unity project may become unexplainably and temporarily broken. This can result in mysterious compiler errors and missing script references despite the script file being present and clean. The steps to resolve this are:
> 1. Close and restart Unity.
> 1. If this doesn't work, in the Unity menu bar select **Assets** then **Reimport All**. *Note that this process can take some time.*

**To create a new project**:

1. Create a new Unity project using the **3D URP** (Core) template.  You may need to click **Download template** on the right before proceeding.

    ![A screenshot of the 3D URP Core template option when you create a new Unity project.](../../media/get-started-developing-mesh/image008.png)

1. In Unity, create a new scene using the **Standard (URP)** scene
    template. Save it with an appropriate name.

1. In the **Hierarchy**, delete **Global Volume**.

1. [Add the Mesh Toolkit package.](add-the-mesh-toolkit-package.md)

**To update an existing project**:

1. Ensure that your project targets the Universal Render Pipeline (URP).
1. [Add the Mesh Toolkit package.](add-the-mesh-toolkit-package.md)

## General Tips

- For design tips, see our series of design articles starting with [Designing for Mesh: Overview](../../develop/design/overview.md). There are also guides for implementing advanced features such as [Mesh Physics](../enhance-your-environment/physics/mesh-physics-overview.md) and [Mesh Scripting](../../develop/script-your-scene-logic/mesh-scripting-overview.md).

- Environments can't depend on any scripts that aren't included in the Mesh Toolkit package. This includes scripts you've added to the project manually or ones obtained by installing other packages.

- The only event callbacks that are allowed to be called by environment components are _ScriptMachine.TriggerUnityEvent_ and _ScriptMachine.TriggerAnimationEvent_.

- Only some Unity components, methods and properties are supported in Visual Scripting within Mesh environments.

- If you get a dialog asking you to configure project settings, allow this to ensure your project is fully set up for Mesh.

- You can't use UnityUI (uGUI) for custom UI.

- You must use Text Mesh Pro for displaying text.

## Next steps

[Add the Mesh Toolkit package](add-the-mesh-toolkit-package.md)
