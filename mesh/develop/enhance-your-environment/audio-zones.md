---
title: Audio Zones in Mesh
description: Learn how to provide the optimal audio experience for all attendees in a Mesh event. 
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 6/14/2024
ms.topic: conceptual
keywords: Microsoft Mesh, Mesh, audio, sound, audio zones, sound
---

# Audio Zones in Mesh

A Mesh event has *audio spatialization* (we describe this as "the way a sound behaves in a 3D space"). However, until now, you've had limited control over how spatialization works; there's one default audio setting that hasn't been customizable for different event sizes and scenarios. this can be a problem if, for example, your event takes place in a large room and you want the volume of the voices between attendees to fade out more gradually as the attendees get further apart. Another example is an event where there's a large table and attendees at the extreme ends of the table are far enough apart that they can't hear each other. In real life, if you're far away, you can speak louder, but in Mesh event all voice volumes are *normalized* so this doesn't work. In some cases, there are workarounds (for example, make everyone in the event an *Organizer* so they can push the *megaphone* button to make themselves heard by everyone) but these limitations and workarounds can detract from immersion and presence. 

With our latest Mesh toolkit updates, you have much more control over how sound behaves in your environment. You can customize the sound settings for the whole space or create *Audio Zones* which are individual areas in the space that have their own unique audio settings. this gives you the ability to not simply equal the experience of being in a real-life acoustic space but to go beyond it. 

- No matter how large the space is, you can give certain attendees the ability to be heard throughout the entire space.

- Certain attendees can have multi-directional conversations without interrupting each other. tbd - more detail.

the benefits:

--Increase productivity, interaction and engagement.

--Decrease mis-communication.

--If you want to change an audio setting, you can do this __________________ tbd without having to edit the environment itself.

Common scenarios:

- In an environment, create a small "discussion area" with a few chairs or couches. Place an Audio Zone over the area. Select the Audio Zone setting called "low attentuation." Anyone inside of this Audio Zone will hear anyone else inside the Zone clearly. You can also choose a setting called "Muffled voices outside" (tbd -- check on name) which muffles the voices of anyone outside the Audio Zone, making it easier for people inside the Zone to hear each other.

- Set up walls and create distinct seperations between rooms.

- Create tunnels that have more reverberation.

- Have distinct acoustic features for different areas. For example, you can have an "outdoor space" where there's no echo and things sound flat, and an "indoor space" where concrete and glass surfaces result in more echo.


=====================

Solution for Organizer/Megaphone problem: create a *stage* area. Anyone who walks into this area is automatically heard by everyone in the environment. 

## Create an Audio Zone

1. Add an empty GameObject to the scene.
1. Add an Audio Zone script to this new GameObject.
1. Add a trigger collider in the shape you want (capsule collider, or rectangle).
1. Adjust the trigger collider to the size you want.
1. Specify the Audio Zone options you want. For example:
    1. For Default Voice, choose "Low attenuation."
    1. Choose "Muffled voices."

Note: these steps aren't the preferred way to set up an Audio Zone. We want Audio Zones to be Objects. the Audio Zones in the environment should be more about defining acoustics than user functionality (for example, muffled voices). By configuring these options within objects, the environment creator can place the objects in an environment. the environment can then be used as the basis for tEmplates. An Organizer can then choose the template that has the Audio Zone-based objects they want for an event. 

Prefabs

