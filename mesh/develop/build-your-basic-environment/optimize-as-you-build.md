---
title: Optimize as you build
description: View tips and tool suggestions for optimizing your Mesh project as you build it.
author: vtieto
ms.author: vinnietieto
ms.date: 1/19/2024
ms.service: mesh
ms.topic: How to
keywords: Microsoft Mesh, Unity, getting started, Unity, scene, teleportation, navmesh, travel point, travelgroup, player movement
---

# Optimize as you build

This article contains a brief overview of optimization and performance. You can learn a lot more by reading our article named [Performance Guidelines](../debug-and-optimize-performance/performance-guidelines.md).

As you start your Mesh project, it's important to keep in mind the things you can do to ensure the best experience  for your users. This should include:

- Having a performance budget that aligns with the platforms you're targeting. You can build for PC, Quest/Android, or both. If you build for both, you'll need to optimize for Quest/Android.

- Ensuring that any 3D models you import into your project are constructed appropriately for high performance.

- As you build, regularly checking with the [Content Performance Analyzer](../debug-and-optimize-performance/cpa.md) (CPA) tool to view a range of helpful performance-related statistics about your project.

![A screenshot of the Content Performance Analyzer tool.](../../media/build-your-basic-environment/005-cpa-analyzer-with-background.png)

- Within the Mesh app, using the Performance Profiler to view your Mesh project's frame rate, scene complexity, and memory usage across all platforms. The Performance Profiler is also accessible within the Mesh toolkit.

![A screenshot of the Performance Profiler.](../../media/build-your-basic-environment/005-cpa-analyzer-with-background.png)

You can also use these tools which are useful for profiling content in Unity:

- [Unity's Profiler](https://docs.unity3d.com/Manual/Profiler.html)
- [Unity's Frame Debugger](https://docs.unity3d.com/Manual/FrameDebugger.html)
- [RenderDoc](https://docs.unity3d.com/Manual/RenderDocIntegration.html) (**IMPORTANT**: RenderDoc can only perform captures from the Unity editor. Mesh app builds won't work).

## Next Steps

> [!div class="nextstepaction"]
> [Environment construction tips](./environment-construction-tips.md)
> [Performance Guidelines](../debug-and-optimize-performance/performance-guidelines.md)

