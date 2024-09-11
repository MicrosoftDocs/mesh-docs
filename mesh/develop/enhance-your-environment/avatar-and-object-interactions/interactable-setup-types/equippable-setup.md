---
title: Setup for Interactable type Equippable
description: Learn about the settings in the Setup component for Interactable type Equippable.
ms.service: mesh
author: jackiecurley
ms.author: vinnietieto
ms.date: 9/9/2024
ms.topic: overview
keywords: Microsoft Mesh, object and player interactions, interactables, manipulables, equippables, throwables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw, attach, Mesh emulator, emulator, Mesh Emulation, Basic
---

# Setup for Interactable type Equippable

![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/003-interactable-setup-equippable.png)

## Terminology

In this article, "hover" means "when the cursor (PC or Mac) or controller pointer (Quest) is over the object."

## Interaction Settings

- **Interaction Range**: Furthest distance, in meters, the avatar can be to interact with this object.

- **Aim IK arm on Hover**: Whether or not the avatar's arm will reach towards the object while hovering using IK targeting.

- **Hover Hand Pos**: The hand pose shape to put the avatar's hand into when hovering over the object.

    ![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/002-hover-hand-position.png)

    For example, if you choose *Pinch*, when the avatar reaches for the object, its hand will assume the pinch position.

    ![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/007-hand-hover-pinch.png)


## Highlight Settings

**Highlight Settings**
- **Hovered/Selected**: Whether or not to highlight the object if it's highlighted or selected.
- **Highlight Mechanism**

    - Menu item 1: **Shader Properties**
        - **Highlight Color**: The color to set the material's color properties when the object is highlighted.
        - **Highlight Transition Duration**: The amount of time to fade the highlight in/out when transitioning.
        - **Highlight Amount Properties**: The material's properties to set the amount of highlight when highlighted. This is a float value.
        - **Highlight Color Properties**: The material's properties to set the color of highlight when highlighted. This is a color value.

    - Menu item 2: **Mesh Outline**: Adds an automatic outline of the specified color/width to objects.
        
        - **Highlight Color**: The color of the outline.
        - **Highlight Transition Duration**: The amount of time to fade the outline in/out when transitioning.
        - **Highlight Outline Width**: How thick (in meters) should the outline be. Overrides the "Extrusion Value" in the Graphics Tools/Standard material.
        - **Custom Outline Material**: The material used to render the outline.
        - **Custom Stencil Write Material**: The material used write a value to the stencil buffer
        - **Outline Exclusion Mode**: Option to filter out renderers you don’t want included in the outline.

    - Menu item 3: **Inner Glow**: Applies a highlight with a glow effect using the given properties.

        - **Highlight Color**: The color of the inner glow.
        - **Highlight Transition Duration**: The amount of time to fade the inner glow in/out when transitioning
        - **Custom highlight material**: Override option specific to this object to set the material used for the glow. If this isn't set, the default material from the settings asset will be used.
        -  **Exclusion string:** If this is set then any Game Object with a name containing the exclusion string will be excluded from the highlight.

## Object Positioning

- **Position** and **Rotation**: Use these settings to fine-tune the position and rotation of the object relative to the avatar's hand. Small adjustments here can significantly improve the realism of how the object is held.

    Use these settings to fine-tune how the object looks when the avatar is holding it.

## **Hand Positioning**

These settings determine the position of the avatar's hand (specifically, the wrist) relative to the position of its chest. 

### Presets

In addition to the *default* pose for the avatar's hand, there are nine presets that give you a variety of pose choices. For example, if you choose *Preset 1*, the avatar will hold the object with its palm facing up.

![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/010-preset-1-palm-up.png)

**To select a preset**:
Do one of the following:

- Click the button that displays **Default Pose**, and then select a preset from the list.

![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/009-preset-list.png)

-or-

- Click the forward/backward arrows to the right of **Hand Positioning**.

![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/008-preset-arrows.png)

#### Change a preset's settings

Navigate through the preset list using the forward/backward buttons and note that each preset has its own unique settings.

![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/011-preset-settings.png)

- **Position**: The distance from the avatar's hand to its chest when an object is equipped.  
- **Rotation**: The amount to rotate the wrist when an object is equipped.  
- **Hand Pose Shape:** This is a drop-down that provides a range of hand pose shapes to put the avatar's hand into when equipped. You can also choose *none*.
- **Hand Pose Size:** Size of the hand pose from 0 – 1.  

#### Reset to the default preset settings

If you find that a preset doesn't give you the precise pose you're looking for, you can change these settings for further improvement. As soon as you make any changes, a message appears telling you that you can restore the default preset settings by clicking the **Reset** button.

![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/012-hand-positioning-reset.png)

## Create your own presets







- **Activation Settings**  

    - **Activate Type:** When to set the item as active. Throwable objects cannot be activated and will always have activated type set to none.
        - **None**: This item can't be activated.  
        - **Toggle:** This item toggles between active/not active every time the activate control is clicked.  
        - **Single:** This item is activated when the activate control is clicked and then automatically deactivated once it reaches its last target pose.
