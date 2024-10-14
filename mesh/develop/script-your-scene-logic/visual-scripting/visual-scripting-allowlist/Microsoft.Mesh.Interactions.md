# Microsoft\.Mesh\.Interactions

## Scene

### AvatarTether

A script that can be added to any object with settings for how this object tethers the local player\. 

Example use cases: 

- Default interactable object, add a Unity event callback to SendTetherPlayerSignal for OnSelected\. When user clicks on the object they get tethered to the object\.  
- Player trigger object, add a Unity event callback to SendTetherPlayerSignal for OnActivated\. When a user walks into the object they get tethered to a point within the object\.  
- Moving platform and zipline, etc\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Read? | Write? | Share? | 
|----------|------|:-----:|:------:|:------:|
| Avatar Tether \| Get Avatar Is Tethered |bool|yes|no|no|
| Avatar Tether \| Get Local Avatar Is Tethered |bool|yes|no|no|

| Node | Inputs | Outputs | 
|--------|------------|---------|
| Avatar Tether \| Tether Local Avatar |`tethered` bool|void|
| Avatar Tether \| Toggle Tether ||void|

### AvatarTrigger

Attach this script to a GameObject containing a Collider and a TriggerZone (which will be automatically added) to invoke callbacks when a local player enters or exits the zone\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | 
|----------|------|-------------|:-----:|:------:|:------:|
| Avatar Trigger \| Get Local Avatar In Trigger |bool|Controls our trigger state \- when this changes, and event (and telemetry and signal) are sent\.|yes|no|no|

### MeshInteractableBody

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Read? | Write? | Share? | Script |
|----------|------|:-----:|:------:|:------:|--------|
| Mesh Interactable Body \| Get Equipped At |EquipLocation|yes|no|yes|
| Mesh Interactable Body \| Get Equip Time |System\.DateTime|yes|no|yes|
| Mesh Interactable Body \| Is Activated |bool|yes|no|yes|
| Mesh Interactable Body \| Is Aiming |bool|yes|no|no|
| Mesh Interactable Body \| Is Equipped |bool|yes|no|yes|
| Mesh Interactable Body \| Is Hovered |bool|yes|no|no|
| Mesh Interactable Body \| Is Mine |bool|yes|no|no|
| Mesh Interactable Body \| Is Selected |bool|yes|no|yes|
| Mesh Interactable Body \| Is Selected Locally |bool|yes|no|no|
| Mesh Interactable Body \| Is Throwable<br>Mesh Interactable Body \| Set Throwable |bool|yes|yes|no|
| Mesh Interactable Body \| Is Throwing |bool|yes|no|no|
| Mesh Interactable Body \| Get Modified Target Position<br>Mesh Interactable Body \| Set Modified Target Position |UnityEngine\.Vector3|yes|yes|no|
| Mesh Interactable Body \| Get Modified Target Rotation<br>Mesh Interactable Body \| Set Modified Target Rotation |UnityEngine\.Quaternion|yes|yes|no|
| Mesh Interactable Body \| Get Ray Hit Position |UnityEngine\.Vector3|yes|no|no|
| Mesh Interactable Body \| Get Ray Hit Rotation |UnityEngine\.Quaternion|yes|no|no|
| Mesh Interactable Body \| Get Target Position |UnityEngine\.Vector3|yes|no|no|
| Mesh Interactable Body \| Get Target Rotation |UnityEngine\.Quaternion|yes|no|no|
| Mesh Interactable Body \| Get Throw Velocity<br>Mesh Interactable Body \| Set Throw Velocity |float|yes|yes|no|

| Node | Inputs | Outputs | 
|--------|------------|---------|
| Mesh Interactable Body \| Deselect Object ||void|
| Mesh Interactable Body \| Drop Object ||void|
| Mesh Interactable Body \| Equip Object ||void|

### TravelPoint

Defines the travel target points that the user can teleport to; for example, for the local player spawn, TravelPoints belong to a TravelGroup and are managed by TravelPointManager.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Node | Inputs | Outputs | 
|--------|------------|---------|
|Travel Point \| Travel To Point||void|

### TravelPointGroup

Used to group a several TravelPoints together. All the TravelPoints have to be children of the group GameObject, and the name has to be unique\. Note that manually creating a TravelPointGroup is not required. TravelPointManager will create one automatically for you and assign travel points to it that don't already belong to any group\. However, you can create your own groups if you want to modify the name, or if you want to divide travel points into multiple groups instead of the default one created by the manager\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Node | Inputs | Outputs | 
|--------|------------|---------|
|Travel Point Group \| Travel To Random Travel Point||void|

## Enums

### EquipLocation



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`None`|0
|`DefaultHand`|1
|`RightHand`|2
|`LeftHand`|3
