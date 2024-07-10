---
title: Spatial audio customization in Mesh overview
description: Learn about the basics of providing custom spatial audio zones in a Mesh event. 
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 7/10/2024
ms.topic: conceptual
keywords: Microsoft Mesh, Mesh, audio, sound, audio zones, spatial audio, spatialization, voices, 3D audio, surround sound
---

# Spatial audio customization in Mesh: overview

People meet in Mesh to talk to one another; the voice experience touches every single Mesh Attendee in an event. Mesh achieves an immersive 360-degree "surround sound" experience through the use of *spatial audio*. This applies not only to voices but to any sounds in the event.

In the past, you had limited control over how spatialization works; there was one default audio setting for the whole environment and it wasn't customizable for different event sizes and scenarios. This can be a problem if, for example, your event takes place in a large room and you want the volume of the voices between attendees to fade out more gradually as the attendees get further apart. Another example is an event where there's a large table and attendees at the extreme ends of the table are far enough apart that they can't hear each other. In real life, if you're far away, you can speak louder, but in a Mesh event all voice volumes are *normalized* so this doesn't work. In some cases, there are workarounds (for example, make everyone in the event an *Organizer* so they can push the *megaphone* button to make themselves heard by everyone) but these limitations and workarounds can detract from immersion and presence.

With our latest Mesh toolkit update, you have much more control over how sound behaves in your environment; you can now customize the sound settings for the whole environment. You can also create *Audio Zones* or *Acoustic Zones*. These are individual areas in the environment with customized audio settings that override the default Mesh app audio settings for the environment. For example, you could have an environment that has five different "rooms", with each room serving a different purpose and each one having its own unique Audio Zone.

![______](../../../media/enhance-your-environment/audio-zones/076-zones-overhead-view.png)

In a sense, this gives you audio "super powers; you can provide event attendees with audio experiences beyond what they could have in real life. For example, no matter how large the space is, you can give certain attendees the ability to be heard throughout the entire space. Another example is that Attendees can have multi-directional conversations without interrupting each other.

**Three levels of audio control**

There are three different approaches to adding audio control to your environment. From most powerful to least, these are:

*Audio Zones*  
*Acoustic Zones*  
*Custom environment audio* 

To fully understand these, we recommend that you first learn about *Voice Settings*, *Voice Setting Collections*,  and *Filters*. You'll then be better equipped to choose and implement these various approaches.

Since *Audio Zones* give you the most extensive control over sound, our documentation emphasizes their use.

## Audio Zone benefits

--Increase productivity, interaction and engagement.

--Decrease miscommunication.

--You can set up Audio Zones to be very visible to attendees by using properties such as glowing borders or short messages called *toasts* that display when an attendee enters or exits the Zone. However, you can also design Audio Zones to work "behind the scenes" without any of these visual cues.

## Common scenarios

- In an environment, create a small "discussion area" with a few chairs or couches. Place an Audio Zone over the area. Select the Audio Zone setting called "low attenuation." Anyone inside of this Audio Zone will hear anyone else inside the Zone clearly. You can also choose a setting called "Muffle Voices Outside", which muffles the voices of anyone outside the Audio Zone, making it easier for people inside the Zone to hear each other.

- Set up walls and create distinct separations between rooms.

- Provide a more realistic ambience to tunnels by increasing reverberation.

- Have distinct acoustic features for different areas. For example, you can have an "outdoor space" where there's no echo and things sound flat, and an "indoor space" where concrete and glass surfaces cause more echo.

- Create a "production booth" for people who are in the event who are tasked with helping the host (for example, running the lights).  When they talk normally, no one outside the booth can hear them, but they can hear voices and sounds from outside the booth.

- Create a "stage" Audio Zone. Anyone who walks into this Zone is automatically heard by everyone in the event.

## Audio terminology

In order to fully understand how you can control sound with Audio Zones, it's useful to be familiar with some audio terminology.

**attenuation**: a decrease in the intensity of certain elements of a sound. For our purposes, that means a lowering of volume, a lessening of reverb, or a lessening of high frequencies ("low pass"). The names of the prefabs indicate which elements of the sound they're affecting.

![______](../../../media/enhance-your-environment/audio-zones/070-attenuation-filters.png)

For example, if you create an Audio Zone and you want the sounds outside of the Zone to barely be audible inside the Zone, you can *attenuate* those incoming sounds using the *LowAttenuation VolumeFilter** prefab.

You'll see "low" in the names of a number of sound-related prefabs; for example, "LowAttenuationVolumeFilter" or "LowAttenuationReverbFilter". In normal attenuation, the further away you get from a sound source, the more the element of the sound being attenuated decreases until it finally reaches zero. The inclusion of "Low" in the names here indicate that there is some attenuation, but it's a lower amount than usual; the element of the sound being attenuated decreases somewhat but never quite reaches zero.

**frequency**: the property of sound that determines its pitch. We perceive tones coming from a bass guitar as having low frequencies, while tones from a flute are perceived as high frequency.

**low pass filter**: this is a filter that you can apply to a Voice Setting. Lower frequencies in a sound will *pass through* the filter and be audible, while higher frequencies will be *attenuated*.

 **reverb** (short for "reverbation"): the amount of echo in a sound. Sounds in a cave, tunnel or large room typically have noticeable reverb; sounds in a small room have little to no reverb.

**Megaphone**: this is a Mesh term. When an attendee in an event has their *Megaphone* turned on, they can be heard by everyone in the event regardless of location.

## Audio Zone Package

the Audio Zone package is included with the Mesh toolkit.

![______](../../../media/enhance-your-environment/audio-zones/033-audio-zones-package.png)