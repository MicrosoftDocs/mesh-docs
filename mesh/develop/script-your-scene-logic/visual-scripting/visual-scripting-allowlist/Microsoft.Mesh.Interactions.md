# Microsoft\.Mesh\.Interactions

## Scene

### Microsoft\.Mesh\.Interactables\.AvatarTether

A script that can be added to any object with settings for how this object tethers the local player\. 

Example use cases: 

\- Default interactable object, add a Unity event callback to SendTetherPlayerSignal for OnSelected\. When user clicks on the object they get tethered to the object\.  
\- Player trigger object, add a Unity event callback to SendTetherPlayerSignal for OnActivated\. When a user walks into the object they get tethered to a point within the object\.  
\- Moving platform and zipline, etc\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Read? | Write? | Share? | Script |
|----------|------|:-----:|:------:|:------:|--------|
|`AvatarIsTethered`|bool|yes|no|no|Avatar Tether \| Get Avatar Is Tethered
|`LocalAvatarIsTethered`|bool|yes|no|no|Avatar Tether \| Get Local Avatar Is Tethered

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`TetherLocalAvatar`|`tethered` bool|void|Avatar Tether \| Tether Local Avatar
|`ToggleTether`||void|Avatar Tether \| Toggle Tether

### Microsoft\.Mesh\.Interactables\.AvatarTrigger

Attach this script to a GameObject containing a Collider and a TriggerZone (which will be automatically added) to invoke callbacks when a local player enters or exits the zone\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`LocalAvatarInTrigger`|bool|Controls our trigger state \- when this changes, and event (and telemetry and signal) are sent\.|yes|no|no|Avatar Trigger \| Get Local Avatar In Trigger

### Microsoft\.Mesh\.Interactables\.MeshInteractableBody



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Read? | Write? | Share? | Script |
|----------|------|:-----:|:------:|:------:|--------|
|`EquippedAt`|Microsoft\.Mesh\.Interactables\.EquipLocation|yes|no|yes|Mesh Interactable Body \| Get Equipped At
|`EquipTime`|System\.DateTime|yes|no|yes|Mesh Interactable Body \| Get Equip Time
|`IsActivated`|bool|yes|no|yes|Mesh Interactable Body \| Is Activated
|`IsAiming`|bool|yes|no|no|Mesh Interactable Body \| Is Aiming
|`IsEquipped`|bool|yes|no|yes|Mesh Interactable Body \| Is Equipped
|`IsHovered`|bool|yes|no|no|Mesh Interactable Body \| Is Hovered
|`IsMine`|bool|yes|no|no|Mesh Interactable Body \| Is Mine
|`IsSelected`|bool|yes|no|yes|Mesh Interactable Body \| Is Selected
|`IsSelectedLocally`|bool|yes|no|no|Mesh Interactable Body \| Is Selected Locally
|`IsThrowable`|bool|yes|yes|no|Mesh Interactable Body \| Is Throwable<br>Mesh Interactable Body \| Set Throwable
|`IsThrowing`|bool|yes|no|no|Mesh Interactable Body \| Is Throwing
|`ModifiedTargetPosition`|UnityEngine\.Vector3|yes|yes|no|Mesh Interactable Body \| Get Modified Target Position<br>Mesh Interactable Body \| Set Modified Target Position
|`ModifiedTargetRotation`|UnityEngine\.Quaternion|yes|yes|no|Mesh Interactable Body \| Get Modified Target Rotation<br>Mesh Interactable Body \| Set Modified Target Rotation
|`RayHitPosition`|UnityEngine\.Vector3|yes|no|no|Mesh Interactable Body \| Get Ray Hit Position
|`RayHitRotation`|UnityEngine\.Quaternion|yes|no|no|Mesh Interactable Body \| Get Ray Hit Rotation
|`TargetPosition`|UnityEngine\.Vector3|yes|no|no|Mesh Interactable Body \| Get Target Position
|`TargetRotation`|UnityEngine\.Quaternion|yes|no|no|Mesh Interactable Body \| Get Target Rotation
|`ThrowVelocity`|float|yes|yes|no|Mesh Interactable Body \| Get Throw Velocity<br>Mesh Interactable Body \| Set Throw Velocity

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`DeselectObject`||void|Mesh Interactable Body \| Deselect Object
|`DropObject`||void|Mesh Interactable Body \| Drop Object
|`EquipObject`||void|Mesh Interactable Body \| Equip Object

### Microsoft\.Mesh\.Interactables\.TravelPoint

Defines the travel target points that the user can teleport to; for example, for the local player spawn, TravelPoints belong to a TravelGroup and are managed by TravelPointManager.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`TravelToPoint`||void|Travel Point \| Travel To Point

### Microsoft\.Mesh\.Interactables\.TravelPointGroup

Used to group a several TravelPoints together. All the TravelPoints have to be children of the group GameObject, and the name has to be unique\. Note that manually creating a TravelPointGroup is not required. TravelPointManager will create one automatically for you and assign travel points to it that don't already belong to any group\. However, you can create your own groups if you want to modify the name, or if you want to divide travel points into multiple groups instead of the default one created by the manager\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`TravelToRandomTravelPoint`||void|Travel Point Group \| Travel To Random Travel Point

## Enums

### Microsoft\.Mesh\.Interactables\.EquipLocation



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`None`|0
|`DefaultHand`|1
|`RightHand`|2
|`LeftHand`|3
