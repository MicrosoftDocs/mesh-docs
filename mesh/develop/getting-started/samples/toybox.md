---
title: Mesh toolkit Toybox sample
description: Learn about the Mesh toolkit Toybox sample.
author: vtieto
ms.author: vinnietieto
ms.date: 10/02/2024
ms.topic: overview
ms.service: mesh
keywords: Microsoft Mesh, getting started, samples, tutorials, features, physics, toybox, interactables
---

# Microsoft Mesh toolkit Sample: Toybox

## The Toybox Package

The Toybox package is named *com.microsoft.mesh.toolkit.toybox* and can be found in File Explorer in the *Packages* folder.

![A screen shot of the Toybox package in File Explorer.](../../../media/samples/010-toybox-pkg-in-file-explorer.png)

Here's how it looks in the Unity project.

![A screen shot of the Toybox package in the Unity project.](../../../media/samples/009-toybox-package.png)

## Understanding the scene Interactables

In order to understand the interactions between objects in the scene, we recommend that you review the [Grab, hold and throw with Interactables](../../enhance-your-environment/avatar-and-object-interactions/interactables.md) article and then take a look at the objects in the Toybox package that are made interactable by containing the [*Mesh Interactable Setup*](../../enhance-your-environment/avatar-and-object-interactions/interactables.md#the-mesh-interactable-setup-component) or *Mesh Interactable Body* components. Examining the visual scripts attached to certain objects will give you further insights. The scripts contain a mixture of standard Unity nodes and nodes that are specially made for Mesh. To learn more about the Mesh nodes, see the [Visual Scripting Node Reference](../../script-your-scene-logic/visual-scripting/visual-scripting-node-reference.md). There are a lot of GameObjects in the Toybox package; the lists and tables below should make it easier for you to find the interactable objects and the Mesh nodes in the scripts.

## Toybox Activities

The following activities have been removed from the Toybox sample and are now being showcased in the [Mesh Pavilion sample](./pavilion.md).

1. Bean Bag Toss
1. Fire Pit and Roasting Marshmallows
1. Ice Breaker
1. Sphere Sculpture
1. Solar System
1. Radio
1. Boombox

## Add the Toybox package to an existing project

There are a couple of ways to add the Toybox package to your project.

1. Copy and paste the *com.microsoft.mesh.toolkit.toybox* folder located in the [Packages](https://github.com/microsoft/Mesh-Toolkit-Unity/tree/main/Packages) folder into your project's Packages folder.
2. Reference the Toybox package from GitHub.

> [!IMPORTANT]
> To reference the Toybox package from GitHub you must have [Git](https://gitforwindows.org/) installed on your computer.

**To import Toybox into your Unity project using GitHub**:

1. In your project, on the menu bar, select **Window** > **Package Manager**.
1. In the *Package Manager*, click the '+' drop-down and then select "Add package from git URL..."

    ![A screen shot of Add package from Github menu option.](../../../media/samples/011-add-package-with-github.png)

1. Paste <https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.toybox> into the text field and then click **Add**.

    ![A screen shot of the toybox URL pasted into the Github text box.](../../../media/samples/012-add-github-url.png)

Toybox will now be installed in your Unity project as a package in the project's *Packages* folder with the name  *Microsoft Mesh Toolkit Toybox*.

> [!TIP]
> We recommend that you use a specific release of the Toybox package to ensure your project is locked to a release.

You can reference a specific release version, branch, or Git commit hash by altering the URL in step 3 as demonstrated below:

| Syntax           | URL example                                                                                                                                     |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Specific version | <https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.toybox#vX.Y.Z>                                   |
| Specific branch  | <https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.toybox#my_branch>                                |
| Git commit hash  | <https://github.com/microsoft/Mesh-Toolkit-Unity.git?path=/Packages/com.microsoft.mesh.toolkit.toybox#badc0ffee0ddf00ddead10cc8badf00d1badb002> |

## Objects with the Mesh Interactable Setup component

- beanbag_red  
- beanbag_blue  
- toybox_beanbag_reset_button_variant  
- InteractableSphere  
- Planet_Mars  
- Planet_Earth  
- Planet_Jupiter  
- Reset_Button_Marshmallow_Varient  
- MarshmallowStick  
- Button  
- toybox_play_button_01_varient  
- Planet_Mars  
- Planet_Earth  
- Planet_Jupiter  
- Planet_astronaut_hip  
- Button (child object of *ButtonHolder*)  
- toybox_play_button_01_varient  

## Objects with the Mesh Interactable Body component

- beanbag_red  
- beanbag_blue  
- toybox_beanbag_reset_button_variant  
- Reset_Button_Marshmallow_Varient  
- Button (child object of *ButtonHolder*)
- toybox_play_button_01_varient

## Objects with the Mesh Physics Components

| GameObject | Component |
|------------|-----------|
| Gravity | [Orbital Gravity Field](../../enhance-your-environment/physics/mesh-physics-programmers-guide.md#orbital-gravity-field) |
| ContainmentField | [Containment Field](../../enhance-your-environment/physics/mesh-physics-programmers-guide.md#containment-field) |
| Astronaut_containment | Containment Field |
| Buoyancy | [Buoyancy Field](../../enhance-your-environment/physics/mesh-physics-programmers-guide.md#buoyancy-field) |
| BeanBags, Marshmallow Holder, Marshmallow_Pos | [Reset Body Transform](../../enhance-your-environment/physics/mesh-physics-programmers-guide.md#reset-body-transforms) |
| Marshmallow_Pos | Reset Body Transforms |

### Mesh nodes used in script graphs

**[Microsoft Mesh: On State Changed](../../script-your-scene-logic/visual-scripting/visual-scripting-node-reference.md#on-state-changed)**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| Campfire | Reset_Button_Marshmallow_Varient | ResetButton | ResetButton |
| Bean Bag Toss | beanbag_red, beanbag_blue | BeanBagPower | BeanBagGraph |
| Sphere Sculpture | InteractableSphere | SpheresSculptureSphere | SpheresSculptureSphere_Simple |
| IceBreaker | IceBreaker | IceBreaker | IceBreaker |  
| Music Box | Radio_Pressable_Prefab | Pressable Radio | PressableRadio
| Music Box | toybox_play_button_01_varient | PlayButton Script | PlayButton_Script |

<br/>

**Mesh Interactable Body: Is Equipped**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| Bean Bag Toss | beanbag_red, beanbag_blue | BeanBagPower | BeanBagGraph |

***
<br/>

**Mesh Interactable Body: Is Aiming**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| Bean Bag Toss | beanbag_red, beanbag_blue | BeanBagPower | BeanBagGraph |  

***
<br/>

**Mesh Interactable Body: Is Selected**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| Campfire | Reset_Button_Marshmallow_Varient | ResetButton | ResetButton |  
| Bean Bag Toss | beanbag_red, beanbag_blue | BeanBagPower | BeanBagGraph |  
| Sphere Sculpture | InteractableSphere | SpheresSculptureSphere | SpheresSculptureSphere_Simple |  

<br/>

**Mesh Interactable Body: Is Selected Locally**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| IceBreaker | IceBreaker | IceBreaker | IceBreaker |  
| Music Box | Radio_Pressable_Prefab | Pressable Radio | PressableRadio |
| Music Box | toybox_play_button_01_varient | PlayButton Script | PlayButton_Script |

<br/>


**Mesh Interactable Body: IsHovered**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| Sphere Sculpture | InteractableSphere | SpheresSculptureSphere | SpheresSculptureSphere_Simple | 
| IceBreaker | IceBreaker | IceBreaker | IceBreaker |  


<br/>

**Reset Body Transforms: Reset Body Transforms Now**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| Campfire | Reset_Button_Marshmallow_Varient | ResetButton | ResetButton |  

<br/>

**Spatial Audio Properties: Create**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| Bean Bag Toss | beanbag_red, beanbag_blue | BeanBagPower | BeanBagGraph |  
| Sphere Sculpture | InteractableSphere | SpheresSculptureSphere | SpheresSculptureSphere_Simple |  

<br/>

**Microsoft Mesh: Play Mesh Audio**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |  
|----------|-----------------|---------------------|------------|  
| Bean Bag Toss | beanbag_red, beanbag_blue | BeanBagPower | BeanBagGraph |  
| Sphere Sculpture | InteractableSphere | SpheresSculptureSphere | SpheresSculptureSphere_Simple |  

<br/>

**Microsoft Mesh: Random Sound**
***

| Activity | GameObjects     | Script Machine Name | Graph Name |
|----------|-----------------|---------------------|------------|  
| Bean Bag Toss | beanbag_red, beanbag_blue | BeanBagPower | BeanBagGraph |  

<br/>

## Warning about sample load time

The sample could take 15 minutes or slightly longer to load into Unity due to large asset sizes. If you need to, change your Sleep mode setting so that the computer doesn't go to sleep while the project is loading. If this happens, it could cause the project to not load properly.

## Contributions

We are not currently accepting code contributions to our samples.  If you have any feedback or if you run into any issues with the samples or the Mesh toolkit, do the following: in a Unity project that has the Mesh toolkit package installed, select **Mesh Toolkit** -> **Give feedback to Microsoft** and then use the feedback link in the Mesh toolkit to let us know.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## License

The Mesh sample in this project is governed by the MIT license as shown in the [LICENSE.MD](https://github.com/microsoft/Mesh-Toolkit-Unity/blob/main/LICENSE) file in the *Mesh-Toolkit-Unity* repository. However, the samples functionality is dependent on the Mesh toolkit, which is governed by a separate license, and contains 3rd party software. 