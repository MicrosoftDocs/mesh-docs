---
title: Mesh Visual Scripting Best Practices Overview
description: Learn about best practices for Visual Scripting in Mesh.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 8/1/2024
ms.topic: conceptual
keywords: Microsoft Mesh, scripting, visual scripting, coding, nodes, units, graphs, Mesh, best practices
---

# Mesh Visual Scripting best practices overview

At its core, Mesh Visual Scripting is simply Unity Visual Scripting extended and augmented to work well in Mesh:  

- Interface with [Interactables](../../../enhance-your-environment/avatar-and-object-interactions/interactables.md), [Physics](../../../enhance-your-environment/physics/mesh-physics-overview.md), [WebSlates](../../../enhance-your-environment/webcontent.md), [Audio](../../../enhance-your-environment/play-audio-in-mesh.md), [Cloud Scripting](../../cloud-scripting/cloud-scripting-basic-concepts.md), and many more Mesh features through visual scripts.

- Share scene state and visual script variables across all clients connected to a room.  

- Test your custom environments that contain Physics, Interactables, and visual scripts directly in the  Unity Editor with [Mesh Emulator](../../../debug-and-optimize-performance/mesh-emulator.md)--even with multiple simulated clients in split-screen mode.  

- Get actionable guidance on correctness issues and potential [bandwidth or performance bottlenecks](./visual-scripting-best-practices-debugging.md) with on-the-fly diagnostics in Mesh Emulator and across your entire environment with [Content Performance Analyzer (CPA)](../../../debug-and-optimize-performance/cpa.md).

Mesh Visual Scripting also comes with some restrictions:

- Mesh puts limits on the subset of the Unity and C# API that can be used by visual scripts. Some of these restrictions are for security and safety reasons; some restrictions are just technical and may be lifted in future versions.

- Mesh restricts scene access by visual scripts to those parts of the scene that were uploaded by the environment creator. Avatars, Mesh user interfaces, and other Mesh-internal additions to the scene are out of bounds for visual scripts.

Visual Scripting is easy to get started with, but it can be tricky to get all the nuances right--especially for visual scripts that share state across clients in a room. Click the links below to more best practice articles that'll help you make your visual script-enhanced Mesh experiences run delightfully fast and solidly shared for all your Mesh event attendees.

## Next steps

> [!div class="nextstepaction"]  
> [Visual Scripting best practices for performance](./visual-scripting-best-practices-performance.md) 

> [Visual Scripting best practices for networking](./visual-scripting-best-practices-networking.md)  

> [Visual Scripting best practices for debugging](./visual-scripting-best-practices-debugging.md)



