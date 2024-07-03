---
title: Audio Zones in Mesh
description: Learn how to provide the optimal audio experience for all attendees in a Mesh event. 
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 7/2/2024
ms.topic: conceptual
keywords: Microsoft Mesh, Mesh, audio, sound, audio zones, sound
---

# Audio Zones in Mesh

## Overview

A Mesh event has *audio spatialization* (we describe this as "the way a sound behaves in a 3D space"). However, until now, you've had limited control over how spatialization works; there's one default audio setting and it hasn't been customizable for different event sizes and scenarios. This can be a problem if, for example, your event takes place in a large room and you want the volume of the voices between attendees to fade out more gradually as the attendees get further apart. Another example is an event where there's a large table and attendees at the extreme ends of the table are far enough apart that they can't hear each other. In real life, if you're far away, you can speak louder, but in a Mesh event all voice volumes are *normalized* so this doesn't work. In some cases, there are workarounds (for example, make everyone in the event an *Organizer* so they can push the *megaphone* button to make themselves heard by everyone) but these limitations and workarounds can detract from immersion and presence.

With our latest Mesh toolkit updates, you have much more control over how sound behaves in your environment. You can customize the sound settings for the whole space or create *Audio Zones* which are individual areas in the space with customized audio settings that override the settings of the environment. In a sense, this gives you audio "super powers; you can Give event attendees audio experiences beyond what they could have in real life. For example, no matter how large the space is, you can give certain attendees the ability to be heard throughout the entire space. Attendees can have multi-directional conversations without interrupting each other. tbd - more detail.

## Audio Zone benefits

--Increase productivity, interaction and engagement.

--Decrease miscommunication.

--If you want to change an audio setting, you can do this __________________ tbd without having to edit the environment itself.

--You can set up Audio Zones to be very visible to attendees by using properties such as glowing borders or short messages called *toasts* that display when an attendee enters or exits the Zone. However, you can also design Audio Zones to work "behind the scenes" without any of these visual cues.

Common scenarios:

- In an environment, create a small "discussion area" with a few chairs or couches. Place an Audio Zone over the area. Select the Audio Zone setting called "low attenuation." Anyone inside of this Audio Zone will hear anyone else inside the Zone clearly. You can also choose a setting called "Muffled voices outside" (tbd -- check on name) which muffles the voices of anyone outside the Audio Zone, making it easier for people inside the Zone to hear each other.

- Set up walls and create distinct separations between rooms.

- Provide a more realistic ambience to tunnels by increasing reverberation.

- Have distinct acoustic features for different areas. For example, you can have an "outdoor space" where there's no echo and things sound flat, and an "indoor space" where concrete and glass surfaces cause more echo.

- Create a "production booth" for people who are in the event who are tasked with helping the host (for example, running the lights).  When they talk normally, no one outside the booth can hear them, but they can hear voices and sounds from outside the booth.

- Create a "stage" Audio Zone. Anyone who walks into this Zone is automatically heard by everyone in the event.

## Audio terminology

In order to fully understand how you can control sound with Audio Zones, it's useful to be familiar with some audio terminology.

**attenuation**: the lowering of sound volume levels. If you create an Audio Zone and you want the sounds outside of the Zone to barely be audible inside the Zone, you can *attenuate* those incoming sounds using the *Low Attenuation Volume** filter.

**frequency**: the property of sound that most determines its pitch. We perceive tones coming from a bass guitar as having low frequencies, while tones from a flute are perceived as high frequency.

**low pass filter**: this is a filter that you can apply to an Audio Zone. Lower frequencies in a sound will *pass through* the filter and be audible, while higher frequencies will be *attentuated*.

 **reverb** (short for "reverbation"): the amount of echo in a sound. Sounds in a cave, tunnel or large cathedral typically have a lot of reverb; sounds in a small room have a little to no reverb.

**Megaphone**: When an attendee in an event has their *Megaphone* turned on, they can be heard by everyone in the event regardless of location.

## Audio Zone Package

the Audio Zone package is included with the Mesh toolkit.

![______](../../media/enhance-your-environment/audio-zones/033-audio-zones-package.png)

## Create an Audio Zone

1. Add an empty GameObject to the scene and select it.
1. In the **Inspector**, click the **Add Component** button and then search for and add the "Audio Zone" component.

![______](../../media/enhance-your-environment/audio-zones/032-add-audio-zone-component.png)

1. Click the **Add Component** button again and then add the collider that comes closest to the shape of the Audio Zone you have in mind. For example, for a rectangular room, your best choice is probably the "Box Collider".
1. If needed, in the **Box Collider** component, click the **Edit Collider** button and then adjust the shape of the Collider.
1. In the **AudioZone** component, specify the settings you want. [Audio Zone properties are explained further below](#audio-zone-properties).

## Audio Zone flow from creator to event Organizer

1. You, the environment creator, create

Note: these steps aren't the preferred way to set up an Audio Zone. We want Audio Zones to be Objects. the Audio Zones in the environment should be more about defining acoustics than user functionality (for example, muffled voices). By configuring these options within objects, the environment creator can place the objects in an environment. the environment can then be used as the basis for templates. An Organizer can then choose the template that has the Audio Zone-based objects they want for an event. tbd



## Elements of an Audio Zone

### Voice Settings Collection

-In the Audio Zone component, you can choose an existing *Voice Settings Collection* prefab for the Zone. You can also choose "no Collection"; if you do this, the "Default Voices" Collection prefab is applied.

![______](../../media/enhance-your-environment/audio-zones/035-default-voice-collection.png)

### Voice Setting

The purpose of a Voice Collection is to make a variety of *Voice Settings* available for the Audio Zone to use. You can think of a Voice setting as "the thing you apply to a sound to give it the qualities you want." In the Default Voices Collection, there are seven available Voice Settings.

![______](../../media/enhance-your-environment/audio-zones/036-voices.png.png)

The Voice Settings prefabs are located in the **VoiceSetting* folder.

![______](../../media/enhance-your-environment/audio-zones/037-voice-setting-folder.png)

Why would you want up to seven different Voice Setting options for one Audio Zone? Different circumstances, and different Objects in the Audio Zone, may require different sets of audio qualities. You can set a default Voice Setting for the Zone in the Audio Zone component. Let's say we want voices outside of the Audio Zone to sound audible but muffled to anyone inside the Zone. For **Default Voice Selection*, we'll choose "Muffled".

![______](../../media/enhance-your-environment/audio-zones/038-muffled.png)

However, if someone in the event turns on the Megaphone, we don't want attendees in our Audio Zone to hear that voice as sounding muffled; we want it heard clearly. This is, in fact, what happens; we have the "Megaphone" Voice Setting the Collection chosen for our Audio Zone, so the Zone switches to that Voice Setting while the Megaphone is on.

![______](../../media/enhance-your-environment/audio-zones/039-megaphone.png)

Also, let's say you have a Media Player Object in the Audio Zone. When the Player is turned on, the "Media" Voice Setting becomes the active setting for the Audio Zone.

![______](../../media/enhance-your-environment/audio-zones/040-media.png)

How does this happen? Each Voice Setting has a **Uses** property. For the *Media* Voice Setting, this property is set to "Media.

![______](../../media/enhance-your-environment/audio-zones/041-uses.png)

This property tells the Audio Zone to detect if a Media Player in the Zone gets turned on. If it does, the Zone switches its Voice Setting to "Media" 
 



**Filters**: the **Filters* folder contains the following:

- Filter Scripts that provide basic sound elements such as volume and reverb.
- Filter Prefabs. Each prefab has a Filter Script plus some control settings that are unique to the sound element being controlled. For example, the *LowAttenuationReverbFilter* has the *ReverbFilter* attached plus controls for the amount of reverb, the amount of time it takes for the reverb to fade out, and more.

    ![______](../../media/enhance-your-environment/audio-zones/034-low-atten-rev-filter.png)

**VoiceSetting**: a *VoiceSetting* is made of the *VoiceSetting* script, a couple of control settings (*Spread* and *Spatial Blend*), and one or more filters that affect the sound of the VoiceSetting in various ways. It also has a *Uses* setting that determines *when* the VoiceSetting is used. For example, the *Megaphone* VoiceSetting has its **Uses* set to "Megaphone." This means that when the Megaphone is turned on in an event, this VoiceSetting becomes the active VoiceSetting in the Collection.

![______](../../media/enhance-your-environment/audio-zones/011-use.png)









### VoiceSetting Collection

the items in this folder are (I think) made up of collections of individual "voice settings". One of these Voice Settings is "Default Voices".

![______](../../media/enhance-your-environment/audio-zones/007-voice-collection.png)

**Tip**: Voice Settings and Voice Setting Collections are *Scriptable Objects*. A Voice Setting Collection Scriptable Object can be added to the overall environment, to an acoustic zone (tbd what is this?) in the environment, or to an Audio Zone in the environment. 




======

 Each item listed here in the Packages > MM AudioZones > VoiceSetting window is a "voice setting." If you select the voice setting "MixedVoicesLowAttenuation", its individual features (and settings) are shown in the window above. In this case, the VS has three filters (volume, low pass, reverb)

![______](../../media/enhance-your-environment/audio-zones/013-low-atten.png)

Note: You get a lot more control over audio with these voice settings than by using Unity Spatial Audio source. 

We want this "Megaphone" voice setting to apply to people who are "megaphoned" in the space.

![______](../../media/enhance-your-environment/audio-zones/014-megaphoned.png)

this has:
--flat volume filter (similar to the attenuation filter)
--reverb filter (we want lots of reverb--"Wizard of Oz" effect)

the "Use" is set to "Megaphone", which is found in the "Default Voices" collection.

![______](../../media/enhance-your-environment/audio-zones/015-voices-collection.png

Example: in Room #1 here, you don't want to use the Voice Settings in the Default Voices Collection--you want it to sound different for the immersed and Megaphone attendees.

![______](../../media/enhance-your-environment/audio-zones/016-room-one.png)

to achieve this:

1. Create a folder to hold your custom Voice Collections. In this example, the folder is named "Workshop_Voice_Collections".

![______](../../media/enhance-your-environment/audio-zones/017-custom-folder.png)

1. Copy the Default Voices Voice Collecion to this new folder and then rename. Here, we renamed it to "ImaginaryRoomVoices".

    We don't want to use any of the existing Voice Settings so we'll make a new one.

1. Create a folder to hold your custom Voice Settings. Here, we named it "Workshop_Voice_Settings".
1. Drag an existing Voice Setting (we'll use "Low Attenuation") to copy it into the new folder and then rename it "ImaginaryRoomImmersiveSetting".

![______](../../media/enhance-your-environment/audio-zones/018-new-voice-setting.png)

    We don't want the current Reverb filter, so let's delete that. Click the "-" button next to that filter.

![______](../../media/enhance-your-environment/audio-zones/019-delete-reverb-filter.png)

    We'll add a new Reverb filter with settings more in line with our needs

1. Create a new folder. We'll name it "Workshop_Voice_Filters".
1. Drag an existing filter (we'll use "NaturalReverbFilter") to copy it into the new folder and then rename it "ImaginaryRoomImmersedSetting".

1. In the **Inspector** window for our "ImaginaryRoomImmersedSetting" Voice Setting, click the "+" button.
1. In the **Select Voice Filter** window, search for and then select the new filter you created.

    ![______](../../media/enhance-your-environment/audio-zones/020-new-filter.png)

## Common Audio Zone use cases

### Simple meeting room

In this example, we just want a basic discussion environment where attendees can talk easily. this will only require one Audio Zone, but you could add several Audio Zones and customize the settings for each one.

1. Create an environment that will act as a meeting room.
1. Add an empty GameObject to the scene and then name it "Acoustics".

    In this example scenario, there's a child object to *Acoustics* named "teamArea" that has its own Audio Zone. We've also create another child object that's a container for several objects that each have their own custom Audio Zone: **Room_1**, **Room_2**, and more. We'll take a look at how the **Room_1** object is constructed. As the name implies, this is the Audio Zone object that will be applied to Room 1 in the scene.

1. In the **Inspector**, click the **Add Component** button and then search for and add the "Audio Zone" component.
1. In the Audio Zone component, click the **Default Voice Selection** drop-down and then select **Low Attenuation**.
1. Add the "Box Collider" component and then select its **Is trigger** property to *true*.
1. to choose a collection, click the round button in the **Voices** field and then, in the **Select Voice Setting Collection** window, search for and select the Voice Collection you want.

    ![______](../../media/enhance-your-environment/audio-zones/021-select-vc.png)

1. We want attendees in the room to hear if something is going on outside the room, but at a low volume. to make this happen, select **Muffle Voices Outside**. the Voice Setting Collection selected for this Audio Zone contains a "Muffled Voice" setting that makes this work.
1. 

### Stage

1. Create an environment that will act as a meeting room as described in the previous section.
1. Add a GameObject that will act as a stage in front of the room.
1. Follow the steps in the previous section to add an Audio zone to the stage and choose its settings.
1. In the **Audio Zone** component attached to the stage, then click the **Applicability** drop-down, and then select **When Audio Source inside**.

    

<!-- Note tbd: it looks like there are more settings in the Audio Zone component that are already in place:

trigger collider: Room_1 (Box Collider)
Applicability: When Both Inside
Voices: WorkshopRoomVoices (Voice Setting _____).

See 29:30. -->

At runtime, you might have different audio sources inside an Audio Zone (for example, attendees, video players, and radios). Mesh determines which Voice should be assigned to which source and then applies the appropriate setting using the Spatializer. Every time someone enters or exists an Audio Zone, the settings are adjusted.

## Distance attenuation curves

In each Volume Filter, you not only get a **Distance Curve** for attenuation (the sound volume decreases based on the attendee's distance from the sound source), you also get an **Angle  Curve** (the sound volume decreases based on the angle of the attendee's head relative to the sound source). For example, if you want something to sound much quieter when it's behind the attendee's head, you can control this by adjusting the Angle Curve.

    ![______](../../media/enhance-your-environment/audio-zones/029-angle-curve.png)




## Audio Zone properties

**Trigger Collider**: This property contains the GameObject that has an attached Trigger Collider that defines the boundary of the Audio Zone. In most cases, this will be the GameObject the Audio Zone component is attached to. You can set this by dragging the GameObject from the **Hierarchy** and dropping it onto the **Trigger Collider** property, or clicking the round button in the property and then selected a GameObject in the **Select Collider** window.

    ![______](../../media/enhance-your-environment/audio-zones/023-trigger-collider.png)




State: Leave this set to **Uninitialized**.

Zone type: Leave this set to **Normal**.

Priority: You can assign a priority value to the Audio Zone which can be useful if there are several Audio Zones in the scene. For more details, hover the cursory over this property and read the informational popup.

    ![______](../../media/enhance-your-environment/audio-zones/024-priority.png)




Applicability:

- **When both inside**: the Zone's rules apply only if the attendee *and* the source of the audio are both inside the Audio Zone.
- **When Audio Source inside**: the Zone's rules apply if the source of the audio is inside the Audio Zone. (this is how a stage works, for example. When the presenter is on the stage, the stage's Audio Zone settings go into effect.) 

![______](../../media/enhance-your-environment/audio-zones/022-applicability.png)

    


Voices: Choose the Voice Settings Collection that contains the Voice Settings you want for this Audio Zone. Click the round button in the property and then search for and choose a Collection in the **Select Voice Setting Collection" window.

![______](../../media/enhance-your-environment/audio-zones/025-collection.png)





**Default Voice Selection**: the drop-down for this property contains a list of various *uses* you may be interested in. If, for example, you want the Audio Zone to use the settings for the *Natural* use, select *Natural* here and the Audio Zone will look for and use a Voice within the Collection you chose that has *Natural* set for its Use. If no Voices with that Use can be found in the Collection and there are nested Audio Zones, the Audio Zone will look in the Collections for other Audio Zones (going from highest Priority to lowest Priority) for a Voice with that Use. If no Audio Zones have such a Voice, the Audio Zone looks to the Environment for such a Voice. If it still can't be found, the default settings for all environments are used.


the voice in the Voice Collection you chose that you want to be used by default for any attendee who enters the Audio Zone. this property contains a drop-down list with a number of choices. the "standard" option is **Normal**. However, if you want everyone inside the Zone to be heard easily, then **Low Attenuation" might be a better option.

![______](../../media/enhance-your-environment/audio-zones/026-default-voice.png)




Muffle Voices Outside: Allows attendees inside the Audio Zone to hear voices outside the Zone and applies settings that make those voices sound muffled. the "Muffled" Voice Setting uses three filters.

![______](../../media/enhance-your-environment/audio-zones/027-muffled-filters.png)

Much of the "muffled" effect from this voice is due to the strong influence of the [Low Pass Filter](https://docs.unity3d.com/Manual/class-AudioLowPassFilter.html).

 ![______](../../media/enhance-your-environment/audio-zones/028-low-pass-filter.png)





**Can Audio Exit** and **Can Audio Enter**: these properties are useful for controlling privacy. Let's say this current Audio Zone is for Room #1, and Room #2 next to it has an Audio Zone with its "Muffle Voices Outside" property selected. 

    **to allow sounds from Room #1 to be heard in Room #2 (or any area outside the room)**:
    Select **Can Audio Exit**. 
    
    **to prevent sounds from Room #1 from being heard outside the room**:
    Make sure **Can Audio Exit** is unselected. 
    
    **to allow sounds from outside of Room #1 to be heard inside the room:
    Select **Can Audio enter**.
    
    **to prevent sounds from outside Room #1 from being heard inside the room:
    Make sure **Can Audio Enter** is unselected.

**Glow Sound at Border**: This works best when you have some sort of visual representation for the border of the Audio Zone. When this property is selected, a sound triggers when an attendee gets close to the border. For example, you could create an Audio Zone that has an electric fence as its border, and then when an attendee approaches the fence, they hear a crackling electrical sound.

**Attenuate Voices at Border**: As an attendee approaches the border of the Audio Zone, overall volume of voices is lowered.

**Walla Murmur**: this is another property that's useful when you want a certain level of privacy. Let's say that for this room/Audio Zone, you have **Can Audio Exit** deselected, meaning you don't want attendees outside the room to hear what's being said inside the room. However, in this instance, you *do* want attendees outside the room to detect that attendees are inside the room and talking. With **Walla Murmur** selected, when attendees inside the room talk, attendees outside the room will hear what *sounds* like conversation coming from the room but is actually just a sound effect that mimics talking and doesn't represent the actual conversation.

**tip**: **Glow Sound at Border**, **Attenuate Voices at Border**, and **Walla Murmur** are designed to work together. Imagine this scenario: you're in an open space, with attendees talking around you, and you walk towards Room #1 which has an Audio Zone with the three above-mentioned features turned on. As you approach the room, you can hear that attendees inside the room are talking (*Walla Murmur*). the volume levels of the voices around you fade to nothing (*Attenuate Voices at Border*). At the same time, you start to hear a sound that steadily increases in volume as you approach the border of the room (*Glow Sound at Border*). As you walk into the room, the glow sound gets quieter and the volume of the voices inside the room increases. the result is a smooth transition from the voices you were hearing outside the room to the voices inside it.


Entry toast title:
Entry toast body:
Exit toast title:
Exit toast body:

A *toast* is a short message that pops up on the screen and then, after a brief period of time, disappears. You can create a toast that will be displayed when an attendee enters or exits the Audio Zone. 

## Acoustic Zones

If you don't need all the properties that come with an Audio Zone and you just want to specify a particular set of Voice Settings for a bounded region, you can use an *Acoustic Zone* prefab. 

 ![______](../../media/enhance-your-environment/audio-zones/030-acoustic-zones.png)

An Acoustic Zone prefab comes with the *Environment Acoustic Zone* script and is like a simplified Audio Zone. It lets you select a Voice Setting Collection and the trigger Collider it applies to.

 ![______](../../media/enhance-your-environment/audio-zones/031-env-acoustic-zone-script.png)

Prefabs

Rectangular acoustic zone
Circular acoustic zone

these aren't audio zones. they're "marker prefabs" used at runtime to configure an acoustically-oriented audio zone. tbd

## Simple Acoustic Zones experiment

1. Apply an Acoustic Zone prefab that uses the *DefaultEnvironmentAcoustics* script to your whole environment.
1. Select a Voice Settings Collection for the whole environment.
1. Apply an Acoustic Zone prefab that uses the *RectangularAcousticZone* script for a specific area in the environment.




T

















