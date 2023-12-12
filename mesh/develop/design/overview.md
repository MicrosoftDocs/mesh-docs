---
title: Design for Mesh overview
description: An overview for technical artists and developers for how to design for Mesh.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 12/8/2023
ms.topic: Guide
keywords: Microsoft Mesh, unity, design, models, modeling, prerequisites
---

# Designing for Mesh: Overview

This is a guide for artists, designers and developers who want to create Mesh experiences using Unity and possibly other design tools such as 3D modeling programs. Mesh has unique style and development guidelines that should be reviewed to ensure that Attendees at Mesh events are provided with the best experiences possible.

In Unity, you create a project from scratch or use one of our existing samples as a starting point, then add content, and then publish the project as an *Environment* to a Collection in Mesh on the web. When an Event Organizer creates a Mesh event, they can choose to hold their Event in the custom Environment you created.  

Mesh is a new product and is always evolving to meet the needs of our partners. This and other articles cover the design guidelines for creating 3D Environments for various use cases.

It's important to consider that your design and performance needs may be more expansive than what our documentation provides. For example, needs may
differ based on the scale of your Mesh Experiences; a 16-person Environment has different performance requirements from a 200-person
Environment. This doc provides principles and guidelines that should satisfy most needs for businesses deploying Mesh.

A Microsoft Mesh Experience can allow multiple users to simultaneously experience the content you create. Because of this, we deliberately restrict some of the features
available in Unity to a subset that are supported in Microsoft Mesh. 

Here are some things to consider when creating content:

- Microsoft Mesh controls the camera in the scene.

- Microsoft Mesh controls Attendees' movements and interactions in the scene.

- For security reasons, C# behaviors are restricted to a limited set of the behaviors provided in the Mesh Toolkit. Any unsupported behaviors you include in your content won't be loaded or executed.

- Events callbacks are limited to `ScriptMachine.TriggerUnityEvent` and `ScriptMachine.TriggerAnimationEvent`. If you use any unsupported event callback in your components you won't be able to upload your Environment; the build step will fail.

In general, Unity Packages downloaded from the Unity Asset store aren't expected to work unless they conform to the restrictions above.

## Prerequisites

Before creating Mesh Environments, it's important to have a strong foundation in the following disciplines:

- 3D modeling skills or a source for obtaining the models you need

- Texturing and light-mapping (UVs)

- Performance and model optimization

## Recommended tools

To design assets for use in Mesh Environments, you should have some experience with 3D modeling software such as Maya, 3DS Max, Cinema 4D, Houdini, ZBrush, or Blender. For painting and texturing models, you can use the features built into those apps or use a dedicated tool such as Adobe Substance Painter.

## Sharing Unity projects

Currently, sharing Unity projects with other parties is not guaranteed. Be aware that sharing can raise some errors and is **not** fully validated for Mesh-related projects.

