---
title: Mesh object and avatar interactions
description: Learn how to create interactions between avatars and objects using components and scripts.
author: typride
ms.author: vinnietieto
ms.date: 9/6/2023
ms.topic: overview
keywords: Microsoft Mesh, M365, documentation, features, scripting, object and player interactions
---

# Mesh object and avatar interactions

Mesh Interactables is a system for configuring objects with Unity scripts that defines interaction with an object or avatar behavior at runtime. The Interactables package contains scripts of different object types that can be defined. When a project runs, it sets up all the necessary prefabs and settings required for objects or the avatar to behave as defined. If you intend to use Interactables in Playmode, include the Interactables Playmode package in your project. This sets everything up automatically so that all you have to do is click Play to test your objects. Note that the IK functionality seen in the Mesh app isn’t available in Playmode.

For objects you want the avatar to interact with, add a *MeshInteractableProperties* script. The properties for a group of objects that all behave the same can be set up with a parent *MeshInteractableProperties* script. The properties will be applied to all children with rigidbodies at runtime by automatically adding a *MeshInteractableBody* script. **MeshInteractableBody** will allow each interactable to behave independently. If you want to set up an object’s interactions with Visual Scripting, you can add the *MeshInteractableBody* yourself and use its events, such as OnHovered or *OnSelected*. For example, if you have a button that should enable another object, add a *MeshInteractableProperties* and *MeshInteractableBody*to the object and set up a Visual Scripting graph with the *OnSelected* callback to enable that other object. The button will be fully interactable just by adding the script and a collider and you won't have to do anything else.

Another option for interactable objects is to make them manipulable. Manipulable objects will move through space on the end of your interactor ray. There are even more features you can set up for use in the Mesh app, such as IK targeting to make your avatar's hand reach towards the object while they are manipulating it and shortcut controls to rotate ortranslate the object. To turn this feature on, select the Manipulable box and then choose your desired settings. Manipulable objects don’t require a rigidbody, but you should add one if you want the objects to have physics capabilities.

Interactable objects can also be equippable (with or without also being manipulable). Equippable objects will attach to your avatar's hand when you equip them; in the Mesh app, this is done by clicking the object or pressing ‘F’ while the object is selected. Equippable objects contain settings for IK targets for your avatar’s arm pose while the object is equipped. The IK targets are an offset from the avatar’s chest; this determines where the hand goes while the object is held or activated. Equippables also have the option of being **throwable**. When a throwable object is equipped, you can enter into aim mode by pressing and holding the space bar. This will allow your avatar’s arm to follow your mouse target and the object will be thrown when you release the space bar.

Other scenarios you can achieve with Interactables scripts include anchoring your avatar to moving objects such as ziplines or elevators to transport them. You can add an AvatarAnchor component to a moving object to ensure that your avatar moves along smoothly with that object, both locally and for other avatars’ views across the network. If you want an avatar to be attached to an object that’s stationary (for example, a seat or podium) or has various settings for locomotion, you could add an AvatarTether component. This “tethers” the avatar to the object. AvatarTethers first transport the avatar to their location, and then follow the tether settings you’ve chosen to restrict movement while the avatar is tethered. 
All the Interactables components have interaction callbacks and methods available to Visual Scripting so you have an unlimited amount of ways to make them work together. An interactable object can have a callback to its **OnSelected**cted event to an AvatarTether to tether a avatar. The AvatarTether could have its tether located on the same object as a moving AvatarAnchor so the avatar will start moving along with that object as soon as they’re tethered. At the end of the anchor's journey you could have an AvatarTrigger that untethers the avatar from its anchor object when they reach the zone; they are then free to move about as they please.


## Object Types

### *MeshInteractableProperties*

An object that can be interacted with using XRI interactors.

:::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture1.png" alt-text="Meshinteractable properties (script)":::

#### Settings

**[Recommended Component]** Rigidbody: A rigidbody must be added if you want this object to be physics enabled.

**Equippable:** Whether or not this object can be equipped in the avatar's hand.

- **Interaction Offset:** The position and rotation offset relative to the avatar’s hand to place the object.  
- **Equip Target Pose**  
    - *Position*: The distance from the avatar’s chest to place the hand when an item is equipped.  
    - *Rotation*: The amount to rotate the wrist when an item is equipped.  
- **Held Hand Pose:**
    - **Hand Pose Shape:** The hand pose shape to put the avatar's hand into when equipped.  
    - **Hand Pose Size:** Size of the hand pose from 0 – 1.  

- **Activate Settings**  
    - **Activate Type:** When to set the item as active  
        - None: This item can't be activated.  
        - **Toggle:** This item toggles between active/not active every time the activate control is clicked.  
        - **Single:** This item is active for a frame when the activate control is triggered and released.  
    - **Activate Target Poses:** A list of target poses used to place the avatar’s hand when an item is activated. The avatar will interpolate using the animation curve from the previous pose to the current one sequentially down the list for the amount of time defined in interpolation time, staying at the final pose until deactivated. When deactivated, the avatar hand pose will move backwards through the list.  
- **Throw Settings**  
    - **Throwable:** Whether or not the object can be thrown. Throwable objects will enter the avatar into an aim state when the space bar is held  
    - **Throw Velocity:** The velocity to throw the object at when the space bar is released
    - Arm Extension on Aim – The amount to extend the arm when in aim mode.  
    - **Aim Hand Pose:**  
        - **Hand Pose Shape:** The hand pose shape to put the avatar's hand into when aiming.  
        - **Hand Pose Siz****e:** Size of the hand pose from 0 – 1. 
    - **Aim Hand Rotation:** The rotation of the hand while aiming  
    - **Throw Hand Pose:**  
        - **Hand Pose Shape:** The hand pose shape to put the avatar's hand into when the throw is released  
        - **Hand Pose Size:** Size of the hand pose from 0 – 1.  
    - **Throw Target Poses:** A list of target poses used to place the avatar’s hand when an item is thrown. The avatar will interpolate using the animation curve from the previous pose to the current one sequentially down the list for the amount of time defined in interpolation time. The object will be released and the throw hand pose will be used at the second to last target.

**Manipulable:** Whether or not the object can be manipulated through space along the XR ray interactors.

- **Force Mode:** The mode to use to force the object through space  
    - **Default:** Default MRTK behavior that moves the object using its center.  
    - **Point Spring:** Alternative behavior that moves the object by applying force at a grab point (works only for rigidbodies)  

- **Rotation  (Only available for Default mode)**

    - **Enabled**: Whether or not the object can be rotated while manipulating. Each axis can be set individually.  
    - **Manipulation Rotation Logic**

    -   Default: When manipulating an object, it will rotate around the camera and stay at the same orientation relative to the camera (actual transform values will rotate).  
    - Restrictive: When manipulating an object, it will not rotate its transform and will not stay at the same orientation relative to the camera.  
- **Translation (Only available for Default mode) =Enabled**: Whether or not the object can be translated while manipulating. Each axis can be set individually.  
- **Point Spring (Only available for Point Spring mode)**  
    - **Spring strength:** The force of the spring which pulls the object. The higher the value, the faster it will reach the target point.  
    - **Damping Factor:** How much damping is applied to prevent oscillation around the grab point.  
- **Modify Target Transform:** Gives user the option to override the default transform and set the desired position and rotation of object relative to camera/avatar while object is selected:  
    - **Target Space:**  
        -   **Local Space Of Camera:** Whether to specify position and rotation in the camera local space.

        -   **Local Space Of Avatar:** Whether to specify position and rotation in the avatar local space.

    - **New Target Position:** New target position (z component is the direction where camera/avatar is facing)

    - **New Target Rotation:** New target rotation

- **Avatar IK**

    - **Hand Pose Shape**: The hand pose shape to put the avatar's hand into when manipulating the object

    - **Hand Pose Size**: Size of the hand pose from 0 – 1.

    - **Use IK**: Whether or not the avatar's arm will reach towards the object while manipulating using IK targeting.

        -   **Constrain IK Spherical**: If true, arm IK will be done on a sphere. This will cause the avatar arm to not stick straight out.


**Hover IK Settings** – IK settings to be used when hovering over an object

- **Hand Pose Shape**: The hand pose shape to put the avatar's hand into when hovering over the object

- **Hand Pose Size**: Size of the hand pose from 0 – 1.

- **Use IK**: Whether or not the avatar's arm will reach towards the object while hovering using IK targeting.

    - **Constrain IK Spherical**: If true, arm IK will be done on a sphere. This will cause the avatar arm to not stick straight out.

**Highlight Settings**


- **While Hovered/ While Selected**: Whether or not to highlight the object if it’s highlighted or selected.


- **Highlight Mechanism**


    - **Inner Glow** Applies a highlight with a glow effect using the given properties.

        - **Custom highlight material**: Override option specific to this object to set the material used for the glow. If this isn’t set, the default material from the settings asset will be used.

        -  **Exclusion string:** If this is set then any Game Object with a name containing the exclusion string will be excluded from the highlight.

- **Mesh Outline:** Adds an automatic outline of the specified color/width to objects.


    -   **Shader Properties**

        - **Highlight Color**: The color to set the material's color properties when the object is highlighted.
    
        - **Highlight Transition Duration**: The amount of time to fade the highlight in/out when transitioning.
    
        - **Highlight Amount Properties**: The material's properties to set the amount of highlight when highlighted. This is a float value.
    
        - **Highlight Color Properties**: The material's properties to set the color of highlight when highlighted. This is a color value.

### AvatarTether

An object that tethers the avatar to its transform. This does a one-time position change for the local avatar and puts them into a tethered locomotion state based on the object's settings. Only one avatar at a time can be tethered.

:::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture2.png" alt-text="Avatar Tether Script":::

#### Settings

- Tether Transform: The point to tether the avatar to. Will default to the transform the component is attached to.  
- Avatar Tether Point: The point on the avatar to place them at the transform.  
- Allow Rotation: Whether or not the avatar can rotate when they’re tethered.  
- Allow Teleport: Whether or not the avatar can teleport when they’re tethered.  
- Untether Via Attempted Movement: Whether or not the avatar will untether after a small amount of time trying to locomote.  
- Track HMD Movement: Whether or not the avatar will untether after physically walking away.  
- Enforce HMD User Tether: What to do when the avatar exceeds physical movement range. If true, the avatar will be teleported back to tether position; if false, the avatar will be untethered.  

Avatar tether exposes the following settings to visual scripting:

- Properties:  
    - PlayerIsTethered – Whether or not any avatar is tethered  
    - TetheredPlayerIsLocal - Whether or not the local avatar is tethered  
- Methods:
    - TetherLocalPlayer (bool) – Tether or untether the local avatar to this tether  
    - ToggleTether – Tether the avatar when they are not tethered or untether when they are

### AvatarTrigger

An object that invokes events when the local avatar enters/exits its trigger volume. The events are invoked by a sibling TriggerZone.

:::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture3.png" alt-text="Avatar Trigger Script":::

#### Settings

**[Required Component] Collider:** A Collider is required to know what the trigger volume is. This should have **IsTrigger** set to true.

AvatarTether exposes the following properties to visual scripting:
- PlayerInsideTrigger – true when the local avatar is inside the trigger


### AvatarAnchor

An object that the avatar will anchor to when they’re inside the object’s trigger volume so that the avatar moves along with the object. Inherits from AvatarTrigger. Networked avatars will anchor as well so movement is smooth across the network. Any number of players can be anchored to a single object.

:::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture4.png" alt-text="AvatarAnchor":::

#### Settings

**[Required Component] Collider:** A Collider is required to know what the trigger volume is. This should have IsTrigger set to true.

**Detach On Trigger Exit:** If true, the avatar will automatically be detached from the anchor when exiting the trigger.  If false, you will need to call Detach manually.

### Billboard2D

Script to make an object always face the camera.

## TravelPoint and TravelPointGroup

TravelPoints are a component in the Interactables package that can be used to define where to place an avatar when first joining an event or space and also to transport avatars during their experience using Visual Scripting, Unity events, or production tools.

If a TravelPoint is not present in an Environment, and there is a floor at the origin, the avatar will be grounded on the floor when spawned.  If no floor is present near the origin, the avatar will spawn above the origin and fall for a little while and then respawn in a loop.

For Unity events or Visual Scripting the methods available are:  
- TravelPointGroup.TravelToRandomTravelPoint  
    - This will travel the local avatar to a random point in the group
- TravelPoint.TravelToTravelPoint  
    - This will travel the local avatar directly to a specific travel point

Setting up Travel Groups and Travel Points:

1. Create a Travel Point Group: all travel points must belong to a group; a default group will be assigned to any travel points that don't have one. Every travel group must have a unique name.  
    1. To do this, create a new GameObject with a TravelPointGroup component attached.

        :::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture5.png" alt-text="Travelpoint3":::

1. Add Travel Points to the group. To do this, add new GameObjects as children of the Travel Point Group with a Travel Point Component attached.

    :::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture6.png" alt-text="Travelpointcomponentattached":::

    :::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture7.png" alt-text="Travelpoint-zoomed-in":::

    1. Look At Transform: the point you want the camera to look at after spawning into that transform. This will default to CenterTransform forward.  
    1. Radius: the size of the travel area. It’s a circle around the center transform.  
    1. Single Travel: If this is true, only one avatar at a time will spawn into this point unless there are no more points to choose from.  
1. Enable Travel Group GameObjects that you want avatars to spawn into when initially joining an Event or space and disable travel groups that you do not.  
    1. Disabled travel groups can still be directly traveled into during the experience but only the enabled Travel Groups will be used when first joining.  
    1. In this example, only the StartingTravelGroup will be used when first joining.

        :::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture8.png" alt-text="Travelpointfirst join":::

Travel Point exposes the following methods to visual scripting:  
- TravelToPoint() – Will travel the local avatar to this point

Travel Point Group exposes the following methods to visual scripting:  
- TravelToRandomTravelPoint() – Will travel the local avatar to a random point in this group

### Mesh Interactable Body

This component is added automatically at runtime to interactable bodies; developers don’t need to use it. You may want to add it manually to use Mesh interactables with Visual Scripting, such as with interaction events, or to modify the manipulable target transform through the visual script.

Mesh Interactable Body exposes the following properties to Visual Scripting:

For all interactable bodies:

- IsHovered – Whether or not your local avatar is hovering the object. Can also be set to invoke hovered callbacks when someone else hovers.  
- IsSelected – Whether or not any avatar is selecting the object.  
- IsMine (read only)– True for the last avatar to select or equip the object.  

For equippables:
- EquippedAt - Where this object is equipped – None, DefaultHand, RightHand, LeftHand.  
- EquipTime – What time this object was equipped.  
- IsActivated – If this object is in the activated state.  
- IsEquipped (read only) – If this object is currently equipped.  
- IsThrowable – if this object is throwable.  
- ThrowVelocity – The velocity to throw the object when it’s released.  


For manipulables to modify the Target Position:  
- **Target Position (read only)**: Target position of the body when using Default Force Mode in Mesh Interactable Properties  
- **Target Rotation (read only)**: Target rotation of the body when using Default Force Mode in Mesh Interactable Properties  
- **Ray Hit Position (read only)**: Position of the ray-cast hit of the interactor on the body  
- **Ray Hit Rotation (read only)**: The rotation of the interactor around the direction of the ray  
- **Modified Target Position (read and write)**: Used to set the new target position by the visual script. This will override the default target position. Best practice is to override this property:  
    1. Using On State Changed of Target Position. In this case, the visual script will fire a flow only when the interactor and the new position has changed.  
    1. Using On Late Update. If you require to change the target transform in every frame, do it in late update so that the new target transform is available immediately in the next frame.  
- **Modified Target Rotation (read and write)**: Used to set the new target rotation by the visual script. This will override the default target position.

#### Settings

**Modify With Visual Script:** Enable this to modify target transform for manipulable bodies using visual script. 

:::image type="content" source="../../../media/mesh-scripting/object-player-interactions/Picture9.png" alt-text="Modify-with-visual-script":::