---
title: Microsoft Mesh Interactions
description: Microsoft Mesh Interactions
author: typride
ms.author: vinnietieto
ms.date: 9/13/2023
ms.topic: Guide
keywords: Microsoft Mesh, interactions, allowlist
---

# Microsoft Mesh Interactions

## Scene

### Microsoft\.Mesh\.Interactables\.AvatarTether

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`PlayerIsTethered`|bool||yes|no|no|Avatar Tether \| Get Player Is Tethered
|`TetheredPlayerIsLocal`|bool||yes|no|no|Avatar Tether \| Get Tethered Player Is Local

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`TetherLocalPlayer`|`tethered` bool|void||Avatar Tether \| Tether Local Player
|`ToggleTether`||void||Avatar Tether \| Toggle Tether

### Microsoft\.Mesh\.Interactables\.AvatarTrigger



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`PlayerInsideTrigger`|bool||yes|yes|no|Avatar Trigger \| Get Player Inside Trigger<br>Avatar Trigger \| Set Player Inside Trigger

### Microsoft\.Mesh\.Interactables\.MeshInteractableBody



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`EquippedAt`|Microsoft\.Mesh\.Interactables\.OCLTypes\.EquipLocation||yes|yes|no|Mesh Interactable Body \| Get Equipped At<br>Mesh Interactable Body \| Set Equipped At
|`EquipTime`|System\.DateTime||yes|yes|no|Mesh Interactable Body \| Get Equip Time<br>Mesh Interactable Body \| Set Equip Time
|`IsActivated`|bool||yes|yes|no|Mesh Interactable Body \| Is Activated<br>Mesh Interactable Body \| Set Activated
|`IsEquipped`|bool||yes|no|no|Mesh Interactable Body \| Is Equipped
|`IsHovered`|bool||yes|yes|no|Mesh Interactable Body \| Is Hovered<br>Mesh Interactable Body \| Set Hovered
|`IsMine`|bool||yes|no|no|Mesh Interactable Body \| Is Mine
|`IsSelected`|bool||yes|yes|no|Mesh Interactable Body \| Is Selected<br>Mesh Interactable Body \| Set Selected
|`IsThrowable`|bool||yes|yes|no|Mesh Interactable Body \| Is Throwable<br>Mesh Interactable Body \| Set Throwable
|`ModifiedTargetPosition`|UnityEngine\.Vector3||yes|yes|no|Mesh Interactable Body \| Get Modified Target Position<br>Mesh Interactable Body \| Set Modified Target Position
|`ModifiedTargetRotation`|UnityEngine\.Quaternion||yes|yes|no|Mesh Interactable Body \| Get Modified Target Rotation<br>Mesh Interactable Body \| Set Modified Target Rotation
|`RayHitPosition`|UnityEngine\.Vector3||yes|no|no|Mesh Interactable Body \| Get Ray Hit Position
|`RayHitRotation`|UnityEngine\.Quaternion||yes|no|no|Mesh Interactable Body \| Get Ray Hit Rotation
|`TargetPosition`|UnityEngine\.Vector3||yes|no|no|Mesh Interactable Body \| Get Target Position
|`TargetRotation`|UnityEngine\.Quaternion||yes|no|no|Mesh Interactable Body \| Get Target Rotation
|`ThrowVelocity`|float||yes|yes|no|Mesh Interactable Body \| Get Throw Velocity<br>Mesh Interactable Body \| Set Throw Velocity

### Microsoft\.Mesh\.Interactables\.TravelPoint



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`TravelToPoint`||void||Travel Point \| Travel To Point

### Microsoft\.Mesh\.Interactables\.TravelPointGroup



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`TravelToRandomTravelPoint`||void||Travel Point Group \| Travel To Random Travel Point

## Enums

### Microsoft\.Mesh\.Interactables\.OCLTypes\.EquipLocation



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`None`|0|
|`DefaultHand`|1|
|`RightHand`|2|
|`LeftHand`|3|
