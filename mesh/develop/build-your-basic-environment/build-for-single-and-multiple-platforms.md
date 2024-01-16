---
title: Building a Mesh experience for single and multiple platforms
description: Learn about your options for which platforms to build for.
author: typride
ms.author: vinnietieto
ms.date: 10/3/2023
ms.topic: How to
ms.service: mesh
keywords: Microsoft Mesh, Unity, getting started, platform, Quest, Android, new project
---

# Building for single and multiple platforms

Before starting to build your Environment, it's good to keep in mind
that Mesh events can be experienced on two different platforms: desktop
PC and Android, which powers the Meta Quest headset. (In the future,
this may be expanded to more platforms.) Since desktop PCs typically
have far more power than mobile devices using Android, there are several
potential scenarios to consider here:

1. Create a single scene and then build and publish it for PC only.

    You can make this a "high resolution" scene that leverages the full power of the PC.

2. Create a single scene and then build and publish it for Android only.

    In this scenario, your scene must be a more "low resolution" version that will run performantly on Quest/Android.

3. Create a single scene and then build and publish it for PC *and* Android.

This scene must also be a more "low resolution" version to in order to perform well Quest/Android. This means that your Environment won't take advantage of all the PC power available even when it runs on a PC.

The steps for each of these are explained in later sections. To learn more about optimizing for different platforms, see the *Performance optimization* section of the article named [Performance guidelines for Mesh](../debug-and-optimize-performance/performance-guidelines.md#performance-thresholds).

Keep in mind that if you want to host a multi-platform event where Attendees can join from PC and from Meta Quest headset you should use option 3 above. You can only select one environment per event so you will not be able to select an environment for PC and another environment for Android when creating your event.

## Next steps

> [!div class="nextstepaction"]
> [Set up your scene](set-up-your-scene.md)
