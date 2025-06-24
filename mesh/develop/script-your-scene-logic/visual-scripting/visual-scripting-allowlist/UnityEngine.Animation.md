---
title: UnityEngine.Animation
description: UnityEngine.Animation allowlist for Visual Scripting in Mesh.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 10/14/2024
ms.topic: reference
keywords: Microsoft Mesh, scripting, visual scripting, nodes, allowlist
---


# UnityEngine.Animation

## Scene

### [Animator](https://docs.unity3d.com/ScriptReference/Animator.html)

Interface to control the Mecanim animation system.

Supports additional properties and methods from UnityEngine.Behaviour, UnityEngine.Component, and UnityEngine.Object.

| Nodes | Inputs | Outputs |
|--------|------------|---------|
| Animator \| Get Bool |`name` string|bool|Returns the value of the given boolean parameter\.|
| Animator \| Get Float |`name` string|float|Returns the value of the given float parameter\.|
| Animator \| Get Integer |`name` string|int|Returns the value of the given integer parameter\.|
| Animator \| Reset Trigger |`name` string|void|Resets the value of the given trigger parameter\.|
| Animator \| Set Bool |`name` string<br>`value` bool|void|Sets the value of the given boolean parameter\.|
| Animator \| Set Float |`name` string<br>`value` float|void|Send float values to the Animator to affect transitions\.|
| Animator \| Set Float |`name` string<br>`value` float<br>`dampTime` float<br>`deltaTime` float|void|Send float values to the Animator to affect transitions\.|
| Animator \| Set Integer |`name` string<br>`value` int|void|Sets the value of the given integer parameter\.|
| Animator \| Set Trigger |`name` string|void|Sets the value of the given trigger parameter\.|

## Other

### [AnimationClip](https://docs.unity3d.com/ScriptReference/AnimationClip.html)

Stores keyframe based animations\.

Supports additional properties and methods from UnityEngine\.Object.

| Nodes | Inputs | Outputs |
|--------|------------|---------|
| Animation Clip \| Sample Animation |`go` GameObject<br>`time` float|void|Samples an animation at a given time for any animated properties\.|


