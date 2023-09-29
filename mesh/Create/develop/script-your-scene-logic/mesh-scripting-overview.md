---
title: Mesh scripting overview
description: Overview of Mesh Cloud Scripting and Mesh Visual Scripting.
author: typride
ms.author: vinnietieto
ms.date: 8/28/2023
ms.topic: Guide
keywords: Microsoft Mesh, scripting, cloud scripting, visual scripting, coding
---

# Mesh Scripting overview

## Introduction

You can add Mesh Scripting development tools to your project in Unity, then create an Environment, and then assign behaviors to objects in the Environment and the Environment itself. 

There are two different Mesh Scripting approaches:

**Mesh Cloud Scripting**: The development workflow and model for Mesh Cloud Scripting is very similar to regular Unity scripting with MonoBehaviours. Scripts can edit runtime values of game objects, have "initialize" and "quit" methods, and subscribe to events. As with MonoBehaviours, Mesh scripts are written in C#.

**Mesh Visual Scripting**: This is based on Unity Visual Scripting but has added features for Mesh development.

## Benefits of using Mesh Cloud Scripting

- Simple app model (all code and logic runs in one place).
- Easy connection to cloud side content.
- Allows code reviews, diffs, history inspection, and Git integration.
- Better debugging tools.
- Access to external assemblies.

## Benefits of using Mesh Visual Scripting**:

- Add interactivity and dynamic runtime behavior to your Mesh Environments without writing code.
- Enables client-side scripting.
- Allows low latency operations such as custom tethered objects from the character’s viewpoint.
- Server deployment can be hard or even impossible in some organizations. Mesh Visual Scripting is simpler to get started with than Mesh Cloud Scripting because it can work “standalone” without a MeshApp server deployment.

## Which scripting approach should you use?

Fortunately, you don’t have to choose one approach exclusively. You can do Mesh Visual Scripting only or Mesh Cloud Scripting only, but you can also combine them. The two systems work well together; if you start scripting with one system, your script will still work seamlessly in the other.


## Prerequisites

Before getting started with Mesh Scripting, you should be able to create a basic Environment in Unity (to learn more, see our document named *Get Started with Mesh Environments* TBD). You should also familiarize yourself with the document named *Mesh 3D Design and Performance Guide* TBD. That document goes beyond the basics and includes many tips for building an Environment in Unity. Mesh Scripting builds on this Unity-based toolchain to let you add scripts to your Environments.

## Next steps

> [!div class="nextstepaction"]
> [Cloud scripting basic concepts](cloud-scripting-basic-concepts.md)
> [Visual Scripting](visual-scripting.md)