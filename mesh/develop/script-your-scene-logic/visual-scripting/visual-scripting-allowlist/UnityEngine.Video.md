---
title: UnityEngine.Video
description: UnityEngine.Video allowlist for Visual Scripting in Mesh.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 10/14/2024
ms.topic: reference
keywords: Microsoft Mesh, scripting, visual scripting, nodes, allowlist
---

# UnityEngine\.Video

## Scene

### [UnityEngine\.Video\.VideoPlayer](https://docs.unity3d.com/Manual/class-VideoPlayer.html)

Plays video content onto a target\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`canSetPlaybackSpeed`|bool|Whether you can change the playback speed\. \(Read Only\)|yes|no|no|Video Player \| Can Set Playback Speed
|`canSetTime`|bool|Whether you can change the current time using the time or timeFrames property\. \(Read Only\)|yes|no|no|Video Player \| Can Set Time
|`isLooping`|bool|Determines whether the VideoPlayer restarts from the beginning when it reaches the end of the clip\.|yes|yes|no|Video Player \| Is Looping<br>Video Player \| Set Looping
|`isPaused`|bool|Whether playback is paused\. \(Read Only\)|yes|no|no|Video Player \| Is Paused
|`isPlaying`|bool|Whether content is being played\. \(Read Only\)|yes|no|no|Video Player \| Is Playing
|`isPrepared`|bool|Whether the VideoPlayer has successfully prepared the content to be played\. \(Read Only\)|yes|no|no|Video Player \| Is Prepared
|`length`|double|The length of the VideoClip, or the URL, in seconds\. \(Read Only\)|yes|no|no|Video Player \| Get Length
|`playbackSpeed`|float|Factor by which the basic playback rate will be multiplied\.|yes|yes|no|Video Player \| Get Playback Speed<br>Video Player \| Set Playback Speed
|`time`|double|The presentation time of the currently available frame in VideoPlayer\.texture\.|yes|yes|no|Video Player \| Get Time<br>Video Player \| Set Time

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Pause`||void|Pauses the playback and leaves the current time intact\.|Video Player \| Pause
|`Play`||void|Starts playback\.|Video Player \| Play
|`StepForward`||void|Advances the current time by one frame immediately\.|Video Player \| Step Forward
|`Stop`||void|Stops the playback and sets the current time to 0\.|Video Player \| Stop

