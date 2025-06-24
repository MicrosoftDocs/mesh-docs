---
title: UnityEngine.Audio
description: UnityEngine.Audio allowlist for Visual Scripting in Mesh.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 10/14/2024
ms.topic: reference
keywords: Microsoft Mesh, scripting, visual scripting, nodes, allowlist
---

# UnityEngine\.Audio

## Scene

### [AudioSource](https://docs.unity3d.com/ScriptReference/AudioSource.html)

A representation of audio sources in 3D\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Audio Source \| Get Clip<br>Audio Source \| Set Clip |AudioClip|The default AudioClip to play\.|yes|yes|no|
| Audio Source \| Is Playing |bool|Is the clip playing right now \(Read Only\)?|yes|no|no|
| Audio Source \| Get Loop<br>Audio Source \| Set Loop |bool|Is the audio clip looping?|yes|yes|yes|
| Audio Source \| Get Mute<br>Audio Source \| Set Mute |bool|Un\- / Mutes the AudioSource\. Mute sets the volume=0,  Unmute restore the original volume\.|yes|yes|yes|
| Audio Source \| Get Pan Stereo<br>Audio Source \| Set Pan Stereo |float|Pans a playing sound in a stereo way \(left or right\)\. This only applies to sounds that are Mono or Stereo\.|yes|yes|yes|
| Audio Source \| Get Pitch<br>Audio Source \| Set Pitch |float|The pitch of the audio source\.|yes|yes|yes|
| Audio Source \| Get Time<br>Audio Source \| Set Time |float|Playback position in seconds\.|yes|yes|yes|
| Audio Source \| Get Time Samples<br>Audio Source \| Set Time Samples |int|Playback position in PCM samples\.|yes|yes|yes|
| Audio Source \| Get Volume<br>Audio Source \| Set Volume |float|The volume of the audio source \(0\.0 to 1\.0\)\.|yes|yes|yes|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Audio Source \| Pause ||void|Pauses playing the clip\.|
| Audio Source \| Play ||void||
| Audio Source \| Play Clip At Point |`clip` AudioClip<br>`position` Vector3|void|Plays an AudioClip at a given position in world space\.|
| Audio Source \| Play Clip At Point |`clip` AudioClip<br>`position` Vector3<br>`volume` float|void|Plays an AudioClip at a given position in world space\.|
| Audio Source \| Play Delayed |`delay` float|void|Plays the clip with a delay specified in seconds\. Users are advised to use this function instead of the old Play\(delay\) function that took a delay specified in samples relative to a reference rate of 44\.1 kHz as an argument\.|
| Audio Source \| Play One Shot |`clip` AudioClip|void|Plays an AudioClip, and scales the AudioSource volume by volumeScale\.|
| Audio Source \| Play One Shot |`clip` AudioClip<br>`volumeScale` float|void|Plays an AudioClip, and scales the AudioSource volume by volumeScale\.|
| Audio Source \| Stop ||void|Stops playing the clip\.|
| Audio Source \| Un Pause ||void|Unpause the paused playback of this AudioSource\.|

## Other

### [AudioClip](https://docs.unity3d.com/ScriptReference/AudioClip.html)

A container for audio data\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
| Audio Clip \| Get Channels |int|The number of channels in the audio clip\. \(Read Only\)|yes|no|
| Audio Clip \| Get Frequency |int|The sample frequency of the clip in Hertz\. \(Read Only\)|yes|no|
| Audio Clip \| Get Length |float|The length of the audio clip in seconds\. \(Read Only\)|yes|no|
| Audio Clip \| Get Samples |int|The length of the audio clip in samples\. \(Read Only\)|yes|no|


