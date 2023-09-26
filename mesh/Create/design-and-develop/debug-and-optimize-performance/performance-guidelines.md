---
title: Performance guidelines for Mesh
description: Development for Mesh using Unity.
author: typride
ms.author: tmilligan
ms.date: 7/27/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, Immersive spaces, Avatars, getting started, documentation, features, performance
---

# Performance guidelines for Mesh

## Performance

Your current choice is to develop for desktop PC or Quest. Once your
scene is created and optimized for either of these platforms, it will
generally be easier to build for other platforms that may become
available in the future. Your Environment will be performant and you can
maximize the number of possible participants. In the future, you can
clone the scene to develop for higher-end platforms and take advantage
of extra computing power to incorporate advanced materials, particle FX,
lighting, and higher model polycount.

### Simple vs complex scenes

As with all game development, in Mesh there's a tradeoff between
complexity/quality and performance. Depending on the machine running
Mesh, or other programs running simultaneously, your user may experience
decreased performance, especially if your scene is complex. As you
increase complexity and/or quality of your Mesh environments, the number
of users that Mesh can support without performance issues decreases.

## Resources for analyzing performance

### Content Performance Analyzer (CPA)

We recommend that you use the Content Performance Analyzer (CPA) to
maximize the number of users that can access and use a Mesh environment
without performance issues. You can use the CPA to audit polycount, draw
call, texture size, and more. This allows you to catch content
optimization issues and opportunities before content is uploaded to
Mesh. Issues are reported via an editor window in Unity.

![A screenshot of a computer Description automatically generated with
medium confidence](../../../media/3d-design-performance-guide/image002.png)

![A screenshot of a video game Description automatically
generated](../../../media/3d-design-performance-guide/image003.png)

The CPA is included in the Mesh Toolkit package which is required for
any Unity project being used to generate a Mesh Environment. You can
find more details in the CPA package's README.

### Visual Profiler

The Visual Profiler provides a drop in solution for viewing your mixed
reality Unity application\'s frame rate, scene complexity, and memory
usage across a variety of platforms.

![A screen shot of a number Description automatically
generated](../../../media/3d-design-performance-guide/image004.png)

Missed frames are displayed over time to visually find problem areas.
Scene complexity is reported in the form of draw calls and rendered
vertex counts (or triangle counts). Memory is reported as current, peak
and max usage in a bar graph.

**Note:** To ensure the profiler is minimally intrusive it does not
create any GameObjects, perform any per frame managed allocations, and
renders in a single draw call.

Although we've included the Visual Profiler here for use with
development of Mesh environments in Unity, it can also work on a variety
of platforms, such as:

- Microsoft Immersive headsets (IHMD)

- OpenXR platforms

- Steam VR (HTC Vive / Oculus Rift)

- Meta Quest & Quest 2

- WebGL

**Installation of Visual Profiler**

The Visual Profiler is normally ingested as a
Unity [package](https://docs.unity3d.com/Manual/Packages.html) . To
import the Visual Profiler package into your Unity project follow the
below steps:

**NOTE:** The Visual Profilers package requires Unity 2021.3 and above.

1. Open your Unity project and select Window \> Package Manager from
    the file menu bar.

2. Click the \'+\' icon within the Package Manager and select \"Add
    package from git URL\...\".

3. Paste

    <https://github.com/microsoft/VisualProfiler-Unity.git?path=/com.microsoft.mixedreality.visualprofiler#v3.0.0>

    into the text field and click \"Add\".

    ![A screenshot of a computer Description automatically generated](../../../media/3d-design-performance-guide/image005.png)`

4. The Visual Profiler will now be installed within your Unity project
    as an immutable package within the project's Packages folder
    named Microsoft Mixed Reality Visual Profiler.

5. Finally, add the VisualProfiler component to any GameObject in the
    Unity scene you wish to profile. The profiler is initially active
    and visible (toggle-able via the IsVisible property), but can be
    toggled via the enabled/disable voice command keywords (on
    Windows/UWP platforms only).

**Important!**

It is advised you use a specific release of the Visual Profiler package
to ensure your project is locked to a stable release. Release version
3.0.0 is suggested in step three above. You can also pull another
version, specific branch, or git commit hash by altering the URL as
demonstrated below:

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Syntax**         **URL example**
  ------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specific version   [*https://github.com/microsoft/VisualProfiler-Unity.git?path=/com.microsoft.mixedreality.visualprofiler#vX.Y.Z*](https://github.com/microsoft/VisualProfiler-Unity.git?path=/com.microsoft.mixedreality.visualprofiler#vX.Y.Z)

  Specific branch    [*https://github.com/microsoft/VisualProfiler-Unity.git?path=/com.microsoft.mixedreality.visualprofiler#my_branch*](https://github.com/microsoft/VisualProfiler-Unity.git?path=/com.microsoft.mixedreality.visualprofiler#my_branch)

  Specific branch    [*https://github.com/microsoft/VisualProfiler-Unity.git?path=/com.microsoft.mixedreality.visualprofiler#badc0ffee0ddf00ddead10cc8badf00d1badb002*](https://github.com/microsoft/VisualProfiler-Unity.git?path=/com.microsoft.mixedreality.visualprofiler#badc0ffee0ddf00ddead10cc8badf00d1badb002)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Usage of the Visual Profiler**

When using the profiler look for \"missed frames\" which appear as
orange bars. Missed frames indicate your application is not hitting its
target frame rate and may need optimization work. Draw call counts and
vertex counts (or triangle counts) are also displayed under the missed
frame indicators. These numbers can be indicative of why your app isn\'t
meeting its target frame rate.

![A screenshot of a computer Description automatically
generated](../../../media/3d-design-performance-guide/image006.png)

One should also keep an eye on the bottom memory bar to insure memory
usage isn't rapidly changing or approaching the application\'s memory
limit.

The profiler UI (such as anchoring, scale, follow behavior and UI color)
can also be tweaked in the component inspector.

![A screenshot of a computer program Description automatically generated](../../../media/3d-design-performance-guide/image007.png)

Custom profilers can be added to the bottom of the Visual Profiler by
adding to the list of \"Profiler Groups.\" Profiler Groups use
Unity\'s [ProfilerRecorder](https://docs.unity3d.com/ScriptReference/Unity.Profiling.ProfilerRecorder.html)  API.
For example the below image shows how the \"BehaviorUpdate\",
"LateBehaviourUpdate\", and \"FixedBehaviourUpdate\" markers display a
millisecond average over 300 samples with the group label "Scripting."

![A screenshot of a computer Description automatically generated](../../../media/3d-design-performance-guide/image008.png)

**Feedback on the Visual Profiler**

To file issues or suggestions, please use
the [Issues](https://github.com/Microsoft/VisualProfiler/issues)  page
for this project on GitHub.

### Performance Optimization

Optimizing for performance can be a balancing act depending on the
scenario you're developing for and the experience you want to achieve.
Below are our how-to suggestions for our two current platforms.

We suggest that you use the cheaper out-of-the-box Universal Render
Pipeline shaders; this will make upgrading easier in the future. We also
understand the value of custom shaders. In general, we try to keep our
custom shaders for most of the environment at:

- 30 math operations in vertex

- 120 math operations in fragment

- Two texture lookups

#### Android

|Polycount           |Batches             | Renderer         | Color                  |
|--------------------|--------------------|------------------|------------------------|
| <~80k Triangles    |  ~50 batches       |  URP required    |     Linear required    |

|Textures          |Lightmaps             | Skybox           | Shader                  |
|--------------------|--------------------|------------------|------------------------|
| <~15 MB (=16) 512x512)  |  < ~20 MB (=(4) 1023x2024)       |  1024x2048    |     Universal Render Pipeline/Baked Lit    |

#### High-end PCs

|Polycount           |Batches             | Renderer         | Color                  |
|--------------------|--------------------|------------------|------------------------|
| <~500k Triangles    |  ~200 batches  (Use Unit Frame Debugger)    |  URP required    |     Linear required    |

|Textures          |Lightmaps             | Skybox           | Shader                  |
|--------------------|--------------------|------------------|------------------------|
| <~160 MB   |  < ~80 MB        |  2048x4096    |     Universal Render Pipeline/Baked Lit    |

#### Resources for developing advanced Mesh environments in Unity

**Frame Debugger:** <https://docs.unity3d.com/Manual/FrameDebugger.html>

**Unity Sky:** <https://docs.unity3d.com/Manual/sky.html>

**URP:** <https://docs.unity3d.com/Manual/universal-render-pipeline.html>

**Lightmaps:** <https://docs.unity3d.com/Manual/Lightmappers.html>

**Draw Calls** <https://docs.unity3d.com/Manual/DrawCallBatching.html>

**Mipmapping:** [Advanced VR Graphics Techniques
(arm.com)](https://developer.arm.com/documentation/102073/0100/Mipmapping)

## Next steps

> [!div class="nextstepaction"]
> [Playmode](playmode.md)
