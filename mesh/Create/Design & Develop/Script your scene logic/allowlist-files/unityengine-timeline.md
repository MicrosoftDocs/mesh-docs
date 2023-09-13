---
title: UnityEngine Timeline
description: UnityEngine Timeline
author: typride
ms.author: vinnietieto
ms.date: 9/13/2023
ms.topic: Guide
keywords: Microsoft Mesh, UnityEngine Timeline, allowlist, timeline
---

# UnityEngine Timeline

## Scene

### UnityEngine\.Playables\.PlayableDirector

Instantiates a PlayableAsset and controls playback of Playable objects\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`extrapolationMode`|UnityEngine\.Playables\.DirectorWrapMode|Controls how the time is incremented when it goes beyond the duration of the playable\.|yes|no|no|Playable Director \| Get Extrapolation Mode
|`initialTime`|double|The time at which the Playable should start when first played\.|yes|yes|yes|Playable Director \| Get Initial Time<br>Playable Director \| Set Initial Time
|`playableAsset`|UnityEngine\.Playables\.PlayableAsset|The PlayableAsset that is used to instantiate a playable for playback\.|yes|no|no|Playable Director \| Get Playable Asset
|`state`|UnityEngine\.Playables\.PlayState|The current playing state of the component\. \(Read Only\)|yes|no|no|Playable Director \| Get State
|`time`|double|The component's current time\. This value is incremented according to the PlayableDirector\.timeUpdateMode when it is playing\. You can also change this value manually\.|yes|yes|no|Playable Director \| Get Time<br>Playable Director \| Set Time

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Pause`||void|Pauses playback of the currently running playable\.|Playable Director \| Pause
|`Play`||void|Instatiates a Playable using the provided PlayableAsset and starts playback\.|Playable Director \| Play
|`Play`|`asset` UnityEngine\.Playables\.PlayableAsset|void|Instatiates a Playable using the provided PlayableAsset and starts playback\.|Playable Director \| Play
|`Play`|`asset` UnityEngine\.Playables\.PlayableAsset<br>`mode` UnityEngine\.Playables\.DirectorWrapMode|void|Instatiates a Playable using the provided PlayableAsset and starts playback\.|Playable Director \| Play
|`Resume`||void|Resume playing a paused playable\.|Playable Director \| Resume
|`Stop`||void|Stops playback of the current Playable and destroys the corresponding graph\.|Playable Director \| Stop

## Other

### UnityEngine\.Playables\.IPlayableAsset



| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`duration`|double|Duration in seconds\.|yes|no|Playable Asset Interface \| Get Duration

### UnityEngine\.Playables\.PlayableAsset

A base class for assets that can be used to instantiate a Playable at runtime\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`duration`|double|The playback duration in seconds of the instantiated Playable\.|yes|no|Playable Asset \| Get Duration

## Enums

### UnityEngine\.Playables\.DirectorWrapMode

Wrap mode for Playables\.

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Hold`|0|Hold the last frame when the playable time reaches it's duration\.
|`Loop`|1|Loop back to zero time and continue playing\.
|`None`|2|Do not keep playing when the time reaches the duration\.
### UnityEngine\.Playables\.PlayState

Status of a Playable\.

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Paused`|0|The Playable has been paused\. Its local time will not advance\.
|`Playing`|1|The Playable is currently Playing\.
|`Delayed`|2|The Playable has been delayed, using PlayableExtensions\.SetDelay\. It will not start until the delay is entirely consumed\.
