---
title: Add Event features to your Environment
description: Learn about the Event features you can add to your Environment.
author: typride
ms.author: vinnietieto
ms.date: 8/31/2023
ms.topic: Guide
keywords: Microsoft Mesh, Unity, environments, scenes, events, animation, timelines, templates
---

# Add Event features to your Environment

## Overview

You can add various Event features to your Environment that can be controlled during an Event. Events in Mesh can create powerful interactive experiences for hosting all-hands meetings, social gatherings, showcases, or trainings. After you've uploaded your finished custom Environment to Mesh, an Event Producer can use your Environment to create an Event.  

## Playables

*Playables* are objects that are meant to be played, paused, looped, and
stopped; example Playables include Unity-based Timeline elements and
Unity Video Players. When you include Playables in your Environment, they appear in the Mesh app's Event Control Panel where they can be turned on or off.

To learn more about the Unity Playables API, see [Unity - Manual:
Playables API
(unity3d.com)](https://docs.unity3d.com/Manual/Playables.html).

### Unity Video Players

Video playback for the Control Panel can be done using the **Unity Video
Player**. You'll first need to embed a video player in your Unity scene.
Once added, it will appear as an option in your **Control Panel**
content list and can be added to your **Control Panel** using the **+**
button. You can then toggle it **on/off** or adjust playback controls.
Learn more about how to use the **Control Panel** in the document named
*Mesh Event Producer Guide.pdf*, section: *Add Content with the Control
Panel*.

To learn more about the Unity Video Player component, see [Unity -
Manual: Video Player component
(unity3d.com)](https://docs.unity3d.com/Manual/class-VideoPlayer.html).

## Event production scripts

 The *EventProduction* folder included in
*com.microsoft.mesh.toolkit.-X.X.X+X.tgz* includes scripts that
integrate into the Mesh event production system.

**To locate the scripts:**

In the Project panel, navigate to **Packages** **Microsoft Mesh
Toolkit** **mesh.toolkit.sharedcontent** **Scripts** >
**EventProduction**.

![A screenshot of a computer Description automatically generated](../../media/enhance-your-environment/image032.jpg)
The scripts include:

- *EmbeddedAudioBehavior*: For controlling Unity AudioSources with
    hard-coded/embedded audio clips

- *EmbededVideoBehavior:* For controlling hard-coded video

- *ObjectBehavior*: For marking GameObjects that can be
    enabled/disabled via the control panels

- *StreamedVideoBehavior:* For playing online videos

- *UnityPlayableBehavior:* For controlling a PlayableDirector

## Next steps

> [!div class="nextstepaction"]
> [MRTK Graphics tools](mrtk-graphics-tools.md)
