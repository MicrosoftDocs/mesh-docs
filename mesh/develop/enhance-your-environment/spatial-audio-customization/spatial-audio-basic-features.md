---
title: Spatial audio basic features
description: Learn about three basic features that are essential to creating spatial audio zones in Mesh. 
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 7/12/2024
ms.topic: conceptual
keywords: Microsoft Mesh, Mesh, audio, sound, audio zones, spatial audio, spatialization, voices, 3D audio, surround sound
---

# Spatial audio basic features

There are three different approaches to adding audio control to your environment. From most powerful to least, these are:

[*Audio Zones*](./create-zones-and-environment-audio.md#create-an-audio-zone)  
[*Acoustic Zones*](./create-zones-and-environment-audio.md#create-an-acoustic-zone)  
[*Custom environment acoustics*](./create-zones-and-environment-audio.md#choose-custom-environment-acoustics)

To fully understand these, we recommend that you first learn about *Voice Settings*, *Voice Setting Collections*,  and *Filters*, explained below. You'll then be better equipped to choose and implement these various approaches.

### Voice Setting

You can think of a Voice setting as "the thing you apply to a sound to give it the qualities you want." Voice Settings are [ScriptableObjects](https://docs.unity3d.com/Manual/class-ScriptableObject.html) and are located in the *VoiceSetting* folder.

![______](../../../media/enhance-your-environment/audio-zones/036-voices.png)

A Voice Setting ScriptableObject is defined by the VoiceSetting.cs script. It's made up of several properties and one or more [*filters*](#filters).

![______](../../../media/enhance-your-environment/audio-zones/078-voice-setting.png)

A Voice Setting can be applied to a Zone in several ways; you can choose it explicitly as the default VoiceSetting for the Zone, or it can be chosen automatically from a collection of Voice Settings if the Zone determines that it's the most appropriate VoiceSetting for a given circumstance.

### Voice Settings Collection

As the name implies, a Voice Setting Collection is a collection of Voice Settings. It's a [ScriptableObject](https://docs.unity3d.com/Manual/class-ScriptableObject.html), and its purpose is to make the voices it contains available for use for Audio Zones, Acoustic Zones, or Custom Environment Acoustics.

The Voice Setting Collections are located in the **VoiceSettingCollection** folder.

![______](../../../media/enhance-your-environment/audio-zones/079-voice-setting-collection.png)

The only VoiceCollection in the folder currently is *DefaultVoices*. It contains the default Voice Settings that ship with Mesh. If you select *DefaultVoices* in the **Project** folder, you can see the Voice Settings it contains listed as *Elements* in the **Inspector.

![______](../../../media/enhance-your-environment/audio-zones/080-voices.png)

### Filters

*Filters* are found in the **Filters** folder.

![______](../../../media/enhance-your-environment/audio-zones/081-filters.png)

You can think of filters as the lowest level unit that affects the sound. Filters are typically added to a *Voice Setting* prefab; they play an important role in determining how that prefab shapes the sound. 

![______](../../../media/enhance-your-environment/audio-zones/082-filters.png)

There are four filter scripts and a variety of filter prefabs. Each prefab has a filter script attached and some control settings that are unique to the sound element being controlled. For example, the *LowAttenuationReverbFilter* has the *ReverbFilter* script attached plus controls for the amount of reverb, the amount of time it takes for the reverb to fade out, and more.

![______](../../../media/enhance-your-environment/audio-zones/044-low-atten-reverb-filter.png)

**Distance and Angle attenuation curves**

In each Volume Filter, you not only get a **Distance Curve** for attenuation (the sound volume decreases based on the attendee's distance from the sound source), you also get an **Angle  Curve** (the sound volume decreases based on the angle of the attendee's head relative to the sound source). For example, if you want something to sound much quieter when it's behind the attendee's head, you can control this by adjusting the Angle Curve.

![______](../../../media/enhance-your-environment/audio-zones/029-angle-curve.png)

**Note**: You get a lot more control over audio with the [Voice Setting properties](./audio-zone-properties.md) than by using Unity Spatial Audio source.

## Next steps

> [!div class="nextstepaction"]
> [Create Audio Zones and custom environment acoustics](create-zones-and-environment-audio.md)