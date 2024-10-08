---
title: Setup for Interactable type Throwable
description: Learn about the settings in the Setup component for Interactable type Throwable.
ms.service: mesh
author: jackiecurley
ms.author: vinnietieto
ms.date: 9/16/2024
ms.topic: overview
keywords: Microsoft Mesh, object and player interactions, interactables, manipulables, equippables, throwables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw, attach, Mesh emulator, emulator, Mesh Emulation, Basic, throwable
---

# Setup for Interactable type Throwable

![__________________](../../../../media/enhance-your-environment/object-player-interactions/interactable-types/005-interactable-setup-throwable.png)

## Terminology

In this article, "hover" means "when the cursor (PC or Mac) or controller pointer (Quest) is over the object."

To "equip" an object means to hold the object in your hand. Objects that can be grabbed and held are "equippable". When an avatar is holding an object, we say that the object is "equipped".

## Testing limitations

**Important**: In the *Aim Configuration Settings*, *Throw Configuration Settings*, *Object Positioning*, and *Hand Positioning* features described in this article, you have the ability to make adjustments to the position and rotation of an object relative to the avatar's hand or chest. Note that in the Unity Editor, you can only see the results using the Mesh Emulator avatar, which is limited. In order to see the results of these adjustments with a full Mesh event avatar, you must build and publish your project, then create a Mesh event, and then join the event and grab and hold the object in the scene. 

## The three phases of Throwable behavior

With Throwables, it's helpful to think of a throw as occurring in three phases:

1. The avatar is holding the object (in other words, the object is "equipped").
2. The avatar is aiming the object.
3. The avatar is throwing the object.

Each of these phases has its own distinct settings, but some settings are found in all three phases. For example, each phase has a *Hand Pose Shape* that's unique to that phase. Note that the phases aren't listed in order in the *Mesh Interactable Setup* component; the settings for phase 1, holding the object, are in the **Hand positioning** section at the bottom of the component. Settings for phase 2, aiming the object, are in the **Interaction Settings** > **Aim Configuration Settings** section, and settings for phase 3, throwing the object, are in the **Interaction Settings** > **Throw Configuration Settings** section.

## Interaction Settings

- **Aim Configuration Settings**  
        - **Arm Extension on Aim** – The amount to extend the arm when in aim mode.  
        - **Hand Pose Shape:** The hand pose shape to put the avatar's hand into when aiming.  
        - **Hand Pose Size:** Size of the hand pose from 0 – 1.
        - **Aim Hand Rotation:** The rotation of the hand while aiming  

- **Throw Configuration Settings**

    - **Throw Hand Pose Settings:**  
        - **Hand Pose Shape:** The hand pose shape to put the avatar's hand into when the throw is released.
        - **Hand Pose Size:** Size of the hand pose from 0 – 1.

    - **VR Settings**

        - **Min Throw Velocity VR:** The minimum velocity to apply to an object when thrown on the Quest.
        - **Max Throw Velocity VR:** The maximum velocity to apply to an object when thrown on Quest. This is the velocity value used on PC. On Quest the velocity will be scaled based on the user's physical arm movement.

        **Note**: On the Quest, the velocity applied when an object is thrown will be scaled between the minimum and maximum values using the real velocity of the user's arm movement.

    - **2D Settings**

        - **2D Throw Velocity**: The velocity to apply to an object when it's thrown on PC.
        - **Throw Direction Offset**: A directional offset to apply to an object when it's thrown on PC.
        - **Throw Target Poses:** A list of target poses used to place the avatar's hand when an item is thrown. The position and rotation offsets are relative to the position of the avatar's hand when the throw was initiated. The avatar will interpolate using the animation curve from the previous pose to the current one sequentially down the list for the amount of time defined in interpolation time. The object will be released and the throw hand pose will be used at the second to last target.

        You can add or remove poses by clicking the "+" or "-" buttons located below the list. The number to the right of **Throw Target Poses** tells you how many poses are in the list.
        - **Show Aim arc:**  The Aim Arc is the curved visual indicator that projects from the avatar's hand outward. This indicator helps to determine where the object will be thrown in 3D space.
            - **Aim Arc Origin:** Click the round button in this field to open the **Select Transform** window. You can then select an object whose transform determines the point in 3D space where the Aim Arc starts. This is useful for situations where you want the equipped object to show in the avatars hand while establishing some distance between the arc and the object. 
            - **Override Aim Arc Color:** When you select this, the **Aim Arc Color** property appears with a color box that allows you to select a custom color to override the default Aim Arc color. One use for this is to set the Aim Arc color to red when the cursor (PC) or laser pointer (Quest) lands in an area where you don't want the attendee to throw an object. When the cursor/laser pointer moves to an area where an object *can* be thrown, the Aim Arc turns to green.

**Highlight Settings**

- **Hovered/Selected**: Whether or not to highlight the object if it's hovered over or selected.  

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

## Hand Positioning

- **Position**: The distance from the avatar's hand to its chest when an object is equipped.  
- **Rotation**: The amount to rotate the wrist when an object is equipped.  
- **Hand Pose Shape:** This is a drop-down that provides a range of hand pose shapes to put the avatar's hand into when equipped. You can also choose *none*.
- **Hand Pose Size:** Size of the hand pose from 0 – 1.  

## Next steps

> [!div class="nextstepaction"]
> [Grab, hold and throw with Interactables](../interactables.md)
