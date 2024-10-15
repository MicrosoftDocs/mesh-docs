---
title: UnityEngine.ParticleSystem
description: UnityEngine.ParticleSystem allowlist for Visual Scripting in Mesh.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 10/14/2024
ms.topic: Guide
keywords: Microsoft Mesh, scripting, visual scripting, nodes, allowlist
---

# UnityEngine\.ParticleSystem

## Scene

### [UnityEngine\.ParticleSystem](https://docs.unity3d.com/ScriptReference/ParticleSystem.html)

Script interface for the Built\-in Particle System\. Unity's powerful and versatile particle system implementation\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`emission`|UnityEngine\.ParticleSystem\.EmissionModule|Script interface for the EmissionModule of a Particle System\.|yes|no|no|Particle System \| Get Emission
|`isEmitting`|bool|Determines whether the Particle System is emitting particles\. A Particle System may stop emitting when its emission module has finished, it has been paused or if the system has been stopped using ParticleSystem\.Stop\|Stop with the ParticleSystemStopBehavior\.StopEmitting\|StopEmitting flag\. Resume emitting by calling ParticleSystem\.Play\|Play\.|yes|no|no|Particle System \| Is Emitting
|`isPaused`|bool|Determines whether the Particle System is paused\.|yes|no|no|Particle System \| Is Paused
|`isPlaying`|bool|Determines whether the Particle System is playing\.|yes|no|no|Particle System \| Is Playing
|`isStopped`|bool|Determines whether the Particle System is in the stopped state\.|yes|no|no|Particle System \| Is Stopped
|`particleCount`|int|The current number of particles \(Read Only\)\. The number doesn't include particles of child Particle Systems|yes|no|no|Particle System \| Get Particle Count

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Clear`||void|Remove all particles in the Particle System\.|Particle System \| Clear
|`Clear`|`withChildren` bool|void|Remove all particles in the Particle System\.|Particle System \| Clear
|`Emit`|`count` int|void|Emit count particles immediately\.|Particle System \| Emit
|`Pause`||void|Pauses the system so no new particles are emitted and the existing particles are not updated\.|Particle System \| Pause
|`Pause`|`withChildren` bool|void|Pauses the system so no new particles are emitted and the existing particles are not updated\.|Particle System \| Pause
|`Play`||void|Starts the Particle System\.|Particle System \| Play
|`Play`|`withChildren` bool|void|Starts the Particle System\.|Particle System \| Play
|`Stop`||void|Stops playing the Particle System using the supplied stop behaviour\.|Particle System \| Stop
|`Stop`|`withChildren` bool|void|Stops playing the Particle System using the supplied stop behaviour\.|Particle System \| Stop

## Structs

### [UnityEngine\.ParticleSystem\.EmissionModule[(https://docs.unity3d.com/ScriptReference/ParticleSystem.EmissionModule.html)]

| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`enabled`|bool|yes|yes|Emission Module of Particle System \| Get Enabled<br>Emission Module of Particle System \| Set Enabled

