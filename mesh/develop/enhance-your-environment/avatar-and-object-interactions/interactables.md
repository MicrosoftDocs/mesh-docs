---
title: Grab, hold and throw with Interactables
description: Learn how to create grab, hold, and throw interactions between avatars and objects using components and scripts.
ms.service: mesh
author: jackiecurley
ms.author: vinnietieto
ms.date: 1/16/2024
ms.topic: overview
keywords: Microsoft Mesh, object and player interactions, interactables, avatars, anchors, tethers, triggers, trigger volumes, grab, hold, throw, attach, Mesh emulator, emulator, Mesh Emulation Mode
---

# Grab, hold and throw with Interactables

## Overview

Mesh Interactables is a system for configuring objects with Unity scripts that defines interaction with an object or avatar behavior at runtime. The scripts define the properties of the object that can be interacted with using XRI interactors. The [Mesh toolkit](../../build-your-basic-environment/add-the-mesh-toolkit-package.md) contains scripts of different object types that can be defined. When a project runs, it sets up all the necessary prefabs and settings required for objects or the avatar to behave as defined. If you'd like to see an approximate preview of what your interactable objects will look and feel like when they run in the Mesh app, be sure to [set up Mesh Emulation Mode](../../debug-and-optimize-performance/mesh-emulator.md). Note that the IK functionality seen in the Mesh app isn't available in Mesh Emulation Mode.

**To make an object interactable**:
1. In the **Hierarchy**, select the object.
1. In the **Inspector**, click the **Add Component** button and then select **Mesh Interactable Setup**.

![A screen shot of the Add Component dialog with the Mesh Interactable Setup component select.](../../../media/enhance-your-environment/object-player-interactions/015-interactable-add-component.png)

The component is added and with its default **Object Type** property set to **Interactable**. (Object types will be explained in the next section.)

![A screen shot of the Mesh Interactable Setup component with Object Type set to Interactable.](../../../media/enhance-your-environment/object-player-interactions/009-interactables-common-settings.png)

The properties for a group of objects that all behave the same can be set up with a parent *Mesh Interactable Setup* component. The properties will be applied to all children with rigidbodies at runtime by automatically adding a *Mesh Interactable Body* component to each child object. You may want to add *Mesh Interactable Body* manually to use Mesh interactables with [Visual Scripting](#visual-scripting), such as with interaction events or to modify the manipulable target transform through the visual script.

![A screen shot of the Mesh Interactable Body component.](../../../media/enhance-your-environment/object-player-interactions/016-mesh-interactable-body.png)

**Notes**:

- *Mesh Interactable Body* will allow each interactable to behave independently.

- A rigidbody must be added to an object if you want it to be physics enabled.

## Interactable Object Types

There are four object types:

- Interactable  
- Manipulable  
- Equippable  
- Throwable  

**To choose an object type**:
- In the **Mesh Interactable Setup** component, click the **Object Type** drop-down and then select one of the four options.

![A screen shot of the Object Type menu options in the Mesh Interactable Body component.](../../../media/enhance-your-environment/object-player-interactions/014-interactables-object-type-drop-down.png)

### Interactable

As mentioned above, this is the default type and the most basic one. It gives you access to callbacks that can be invoked when the user hovers over or selects the object that you can have other scripts react to. For example, if you have a button that you want to use to enable another object, add this type to the object with an *OnSelected* callback to enable that other object. The button will be fully interactable just by adding this type and a collider; you won't have to do anything else. 

### Manipulable

An object of this type can have its transform manipulated at runtime and will move through space on the end of an interactor ray. Shortcut controls are available to rotate or translate the object. For manipulation of objects in the Mesh app, you can turn on IK settings for the avatar hand to follow the object. Manipulable objects don't require a rigidbody, but you should add one if you want the objects to have physics capabilities.

![A screen shot of a Mesh experience with a coffee pot being manipulated.](../../../media/enhance-your-environment/object-player-interactions/017-manipulable-coffeepot.png)

### Equippable

An object of this type will attach to your avatar's hand. The PC controls for equip are clicking the object or pressing ‘F' while the object is selected. The Quest controls for equip are pressing the 'Grip' button while the object is selected. Equippable objects contain settings for IK targets for your avatar's arm pose while the object is equipped. The IK targets are an offset from the avatar's chest; this determines where the hand goes while the object is held or activated.

### Throwable

As the name implies, you can grab and throw an object of this type. After grabbing, you can enter into aim mode by pressing and holding the left mouse button. This will allow your avatar's arm to follow your mouse target; to throw the object, release the left mouse button.

![A screen shot of a dart game with a dart grabbed and read to be thrown.](../../../media/enhance-your-environment/object-player-interactions/018-throwable-dart.png)

All the Interactables components have interaction properties and methods available to Visual Scripting so you have an unlimited amount of ways to make them work together. 

## Make objects interactable with Visual Scripting

If you want to set up reactions to an object's interactions with [Visual Scripting](../../script-your-scene-logic/visual-scripting/visual-scripting-overview.md), you can make use of the *Mesh Interactable Body* component inside a script graph with a node to an available property, such as *OnHovered* or *OnSelected*, hooked up to an *OnStateChanged* node. For example, the following script graph will enable the cylinder while the button is pressed and disable it when the button is released. The button is fully interactable just by adding the script and a collider; you don't have to do anything else.

![A screen shot of a script graph with a Mesh Interactable body Is Selected node.](../../../media/enhance-your-environment/object-player-interactions/Picture10.png)

## Settings

### Settings common to Manipulables, Equippables and Throwables

![A screen shot of a Mesh Interactable Setup component with the properties common to all object types highlighted.](../../../media/enhance-your-environment/object-player-interactions/020-common-settings-or-all-types.png)

**Interaction Proximity Radius** Furthest distance the avatar can be to interact with this object

**Hover IK Settings** – IK settings to be used when hovering over an object
- **Hand Pose Shape**: The hand pose shape to put the avatar's hand into when hovering over the object
- **Hand Pose Size**: Size of the hand pose from 0 – 1.
- **Enable IK Tracking**: Whether or not the avatar's arm will reach towards the object while hovering using IK targeting.
    - **Constrain IK Spherical**: If true, arm IK will be done on a sphere. This will cause the avatar arm to not stick straight out.

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

### Settings exclusive to Manipulables

![A screen shot of the Mesh Interactable Setup component with the Manipulable settings displayed.](../../../media/enhance-your-environment/object-player-interactions/011-interactables-object-type-manipulable.png)

- **Force Mode:** The mode to use to force the object through space  
    - **Default:** Default MRTK behavior that moves the object using its center.  
    - **Point Spring:** Alternative behavior that moves the object by applying force at a grab point (works only for rigidbodies)  
- **Rotation  (Only available for Default mode)**
    - **Enabled**: Whether or not the object can be rotated while manipulating. Each axis can be set individually.  
    - **Manipulation Rotation Logic**
        - **Default**: When manipulating an object, it will rotate around the camera and stay at the same orientation relative to the camera (actual transform values will rotate).  
        - **Restrictive**: When manipulating an object, it will not rotate its transform and will not stay at the same orientation relative to the camera.  
- **Translation (Only available for Default mode) =Enabled**: Whether or not the object can be translated while manipulating. Each axis can be set individually.  
- **Point Spring (Only available for Point Spring mode)**  
    - **Spring strength:** The force of the spring which pulls the object. The higher the value, the faster it will reach the target point.  
    - **Damping Factor:** How much damping is applied to prevent oscillation around the grab point.  
- **Modify Target Transform:** Gives user the option to override the default transform and set the desired position and rotation of object relative to camera/avatar while object is selected. When this is set to **Enabled**, you get the following three properties:
    - **Target Space:**  
        - **Local Space Of Camera:** Whether to specify position and rotation in the camera local space.
        - **Local Space Of Avatar:** Whether to specify position and rotation in the avatar local space.
    - **New Target Position:** New target position (z component is the direction where camera/avatar is facing)
    - **New Target Rotation:** New target rotation
- **Avatar IK**
    - **Hand Pose Shape**: The hand pose shape to put the avatar's hand into when manipulating the object
    - **Hand Pose Size**: Size of the hand pose from 0 – 1.
    - **Enable IK Tracking**: Whether or not the avatar's arm will reach towards the object while manipulating using IK targeting.
        -   **Constrain IK Spherical**: If true, arm IK will be done on a sphere. This will cause the avatar arm to not stick straight out.

### Settings shared by Equippables and Throwables

![A screen shot of the Mesh Interactable Setup component with the settings common to Equippables and Throwables highlighted.](../../../media/enhance-your-environment/object-player-interactions/019-common-settings-for-equippable-and-throwable.png)

- **Interaction Offset:** The position and rotation offset relative to the avatar's hand to place the object.  
- **Equip Target Pose**  
    - *Position*: The distance from the avatar's chest to place the hand when an item is equipped.  
    - *Rotation*: The amount to rotate the wrist when an item is equipped.  
- **Held Hand Pose:**
    - **Hand Pose Shape:** This is a drop-down that provides a range of hand pose shapes to put the avatar's hand into when equipped. You can also choose *none*.
    - **Hand Pose Size:** Size of the hand pose from 0 – 1.  

### Settings exclusive to Equippables

![A screen shot of the Mesh Interactable Setup component with the Equippable settings displayed.](../../../media/enhance-your-environment/object-player-interactions/012-interactables-object-type-equippable.png)

- **Activate Configuration**  
    - **Activate Type:** When to set the item as active. Throwable objects cannot be activated and will always have activated type set to none.
        - **None**: This item can't be activated.  
        - **Toggle:** This item toggles between active/not active every time the activate control is clicked.  
        - **Single:** This item is activated when the activate control is clicked and then automatically deactivated once it reaches it's last target pose.
    - **Activate Target Poses:** A list of target poses used to place the avatar's hand when an item is activated. Each pose consists of four properties: Position, Rotation, Interpolation time, and Animation Curve. The position and rotation offsets are relative to the avatar's chest. The avatar will interpolate using the animation curve from the previous pose to the current one sequentially down the list for the amount of time defined in interpolation time, staying at the final pose until deactivated. When deactivated, the avatar hand pose will move backwards through the list.  

### Settings exclusive to Throwables

![A screen shot of the Mesh Interactable Setup component with the Throwable settings displayed.](../../../media/enhance-your-environment/object-player-interactions/013-interactables-object-type-throwable.png)

**Aim Configuration**:
- **Arm Extension on Aim** – The amount to extend the arm when in aim mode.  
- **Aim Hand Pose:**  
    - **Hand Pose Shape:** The hand pose shape to put the avatar's hand into when aiming.  
    - **Hand Pose Size:** Size of the hand pose from 0 – 1.
- **Aim Hand Rotation:** The rotation of the hand while aiming  
- **Throw Hand Pose:**  
    - **Hand Pose Shape:** The hand pose shape to put the avatar's hand into when the throw is released  
    - **Hand Pose Size:** Size of the hand pose from 0 – 1.
- **VR Min Throw Velocity:** The minimum velocity to apply to an object when thrown on the Quest.
- **VR Max Throw Velocity:** The maximum velocity to apply to an object when thrown on Quest. This is the velocity value used on PC. On Quest the velocity will be scaled based on the user's physical arm movement.

On the Quest, the velocity applied when an object is thrown will be scaled between the minimum and maximum values using the real velocity of the user's arm movement.

- **2D Settings**
    - **2D Throw Velocity**: The velocity to apply to an object when it's thrown on PC.
    - **Throw Direction Offset**: A directional offset to apply to an object when it's thrown on PC.
- **Throw Target Poses:** A list of target poses used to place the avatar's hand when an item is thrown. The position and rotation offsets are relative to the position of the avatar's hand when the throw was initiated. The avatar will interpolate using the animation curve from the previous pose to the current one sequentially down the list for the amount of time defined in interpolation time. The object will be released and the throw hand pose will be used at the second to last target.

## Visual Scripting

**For all interactable bodies:**

- **Properties**
    - **IsHovered (read only)** – Whether or not your local avatar is hovering the object.  
    - **IsSelected (read only)** – Whether or not any avatar is selecting the object. When running in MeshBrowser this will be networked.
    - **IsSelectedLocally** – Whether or not the local avatar is selecting the object.
    - **IsMine (read only)** – True for the last avatar to select or equip the object.  

**For Equippables:**

- **Properties**
    - **EquippedAt (read only)** - Where this object is equipped – None, DefaultHand, RightHand, LeftHand. When running in MeshBrowser this will be networked.
    - **EquipTime (read only)** – What time this object was equipped. When running in MeshBrowser this will be networked.
    - **IsActivated (read only)** – If this object is in the activated state. Only valid for objects that are not throwable. When running in MeshBrowser this will be networked.
    - **IsAiming (read only)** – If the local avatar is in the aiming state while holding this object. Only valid for throwables.
    - **IsThrowing (read only)** – If the local avatar is in actively throwing the object. Only valid for throwables.
    - **IsEquipped (read only)** (read only) – If this object is currently equipped by an avatar. When running in MeshBrowser this will be networked.
    - **IsThrowable** – if this object is throwable.
    - **ThrowVelocity** – The velocity to throw the object when it's released.

**For manipulables to modify the Target Position:**

- **Target Position (read only)**: Target position of the body when using Default Force Mode in Mesh Interactable Properties  
- **Target Rotation (read only)**: Target rotation of the body when using Default Force Mode in Mesh Interactable Properties  
- **Ray Hit Position (read only)**: Position of the ray-cast hit of the interactor on the body  
- **Ray Hit Rotation (read only)**: The rotation of the interactor around the direction of the ray  
- **Modified Target Position (read and write)**: Used to set the new target position by the visual script. This will override the default target position. Best practice is to override this property:  
    - Using On State Changed of Target Position. In this case, the visual script will fire a flow only when the interactor and the new position has changed.  
    - Using On Late Update. If you require to change the target transform in every frame, do it in late update so that the new target transform is available immediately in the next frame.  
- **Modified Target Rotation (read and write)**: Used to set the new target rotation by the visual script. This will override the default target position.

#### Settings

**Modify With Visual Script:** Enable this to modify target transform for manipulable bodies using visual script. 
![Modify-with-visual-script](../../../media/enhance-your-environment/object-player-interactions/Picture9.png)

## Next steps

[Triggers, anchors and tethers](./triggers-anchors-and-tethers.md)
[Create avatar spawn and teleport points](./create-avatar-spawn-and-travel-points.md)
[Physics interactions](../physics/mesh-physics-overview.md)
[Enhanced features overview](../enhanced-features-overview.md)
