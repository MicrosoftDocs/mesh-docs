---
title: Mesh 101 Add interactivity with Mesh Visual Scripting
description: Learn adding about adding interactivity to objects with Mesh Visual Scripting.
author: typride
ms.author: vinnietieto
ms.date: 9/8/2023
ms.topic: Tutorial
keywords: Microsoft Mesh, getting started, Mesh 101, tutorial, scripting, visual scripting, code, coding, interactivity
---

# Mesh 101 Tutorial Chapter 3: Add interactivity with Mesh Visual Scripting

Now that we've completed the setup phase, let's move on to making your GameObjects interactive! In this chapter, we'll dive into Mesh Visual Scripting, which you can use to add custom logic to your Environment.

> [!NOTE]
>
> - There are two types of Mesh Scripting: Mesh Cloud Scripting, which uses C# code, and Mesh Visual Scripting, where you create a Script Graph and then add nodes (also called *units*) in a sequence to create your coding logic. This version of the Mesh 101 tutorial uses Mesh Visual Scripting; the previous version used Mesh Cloud Scripting.
>
> - Mesh Scripting isn't required for every Environment, but you'll need it for the features we'll be adding here: making a button interactive, triggering an informational text popup, and teleporting around the scene.

### Choose the NavMesh layer

For this project, we want our avatar to be able to walk around only on
the floors inside the *Sphere Terrace* objects and the floor of a
platform that's attached to one of the wind turbine generators. For
these areas to be walkable, they must be on the *NavMesh* layer. Let's
add the *Sphere Terrace* in Chapter 3 to the NavMesh layer.

1. In the **Hierarchy**, expand the **Chapter 3** GameObject.

2. Select the **Sphere Terrace** GameObject that's a child object to
    the **Chapter3** GameObject.

    ![A screenshot of a computer Description ](../../media/sample-mesh-101/021-chapter-3-sphere-terrace-full-v2.png)

3. In the **Inspector**, select the **Layer** drop-down and then choose
    **NavMesh**.

    ![A screenshot of a computer Description automatically generated](../../media/sample-mesh-101/image025.png)

You don't have to add the other walkable GameObjects to the NavMesh
layer---we've already done it for you.

### Station 3.1: Create an Interactable Button

For our first task, we want to create a button that will play a video
when it's pressed by a participant.

- In the **Scene** window, navigate to the Sphere Terrace that
    contains the stations for Chapter 3, and adjust the view so that
    you're looking at the first station, **3.1 -- Video Playback**, as
    shown below.

![A screenshot of a video playlist Description automatically generated with low confidence](../../media/sample-mesh-101/025-button-v2.png)

We already have a backplate for the button in the correct location in
our scene, but we need to build up the button a little more and add a
label to it. As the text box for the station explains, we'll create a
Script Graph with some button logic so that the button can be used to toggle the VideoPlayer on
and off and change the button text.

**Add the button to the scene**

1. In Unity, make sure the GameObject named **Chapter3** and its child object named **3.1 - Video** are expanded.

    ![A screenshot of a computer Description automatically generated](../../media/sample-mesh-101/031-chapter-3-expanded-v2.png)

2. Search for the **ButtonBase** prefab.

    ![A screenshot of a computer Description ](../../media/sample-mesh-101/032-buttonbase-v2.png)

3. Drag **ButtonBase** from the **Project** window and then, in the
    **Hierarchy**, drop it on the GameObject named **3.1 -- Video** so
    that **ButtonBase** is placed as a child to **3.1 -- Video**.

    ![A screenshot of a computer Description automatically generated](../../media/sample-mesh-101/image038.jpg)

    Make sure the **Transform** > **Position** values for **ButtonBase** are 0, 0, 0.

**ButtonBase** is placed in the scene a little lower than where we want it.

![A picture containing text, screenshot, multimedia software, software Description automatically generated](../../media/sample-mesh-101/033-buttonbase-too-low-v2.png)

Let's fix that.

1. Ensure that **ButtonBase** is selected in the **Hierarchy**.

2. In the **Inspector**, change the **Transform** > **Position** >
    **Y** value to "1".

Perfect! Now **ButtonBase** is correctly located just in front of the **BackplateBase** object.

![A screenshot of a video play Description ](../../media/sample-mesh-101/034-buttonbase-correct-v2.png)

**Rename the button**

- With **ButtonBase** selected, in the **Inspector**, change the name
    of **ButtonBase** to "PlayVideoButton".

    ![A screenshot of a computer Description ](../../media/sample-mesh-101/035-playvideo-button-v2.png)

**Change the label of the button**

Right now, the text on the button says "Label." Let's change that to
"Play."

1. In the **Hierarchy**, expand the **PlayVideoButton** GameObject to
    display its child objects, and then select the **Label** child
    object.

    ![A screenshot of a computer Description ](../../media/sample-mesh-101/image042.png)

2. In the **Inspector**, navigate to the **TextMeshPro -- Text**
    component, and then, in the **Text Input** box, change the text to
    "Play."

    ![A screenshot of a computer Description automatically generated](../../media/sample-mesh-101/036-play-label-v2.png)

#### Create the Visual Script for the button

Before we add our first visual script, in the **Hierarchy**, collapse **PlayVideoButton** and then expand **VideoPlayer**.

![A screenshot of a video play Description ](../../media/sample-mesh-101/200-expand-videoplayer-v2.png)

1. In the **Hierarchy**, select **VideoPlayer**.
1. In the **Inspector**, click **Add Component**, and then select **Script Machine**.

Note that two new components have been added in the **Inspector**: **Script Machine** and **Variables.** There's also a new window named *Mesh Visual Scripting Diagnostics* at the bottom of the **Inspector**. This window will give you feedback on your visual script and can be useful for troubleshooting.

![A screenshot of a video play Description ](../../media/sample-mesh-101/201-script-machine-v2.png)

Note that in the **Script Machine** component, the **Source** is set to **Graph**. Let's keep that setting. This means that we'll be creating a new script graph as an asset and saving it in the project.

1. In the **Script Machine** component, click the **New** button.
1. Navigate to the **Chapter3** > **StartingPointVisualScripts** folder.

Note that there are already two existing assets: **SPShowInfoDialog.asset** and **SPTeleportToOpenAir.asset**.

![A screenshot of a video play Description ](../../media/sample-mesh-101/202-assets-v2.png)

We'll be using these as starting points for the other two features in this chapter. For the feature we're working on right now, the interactable button, we'll create a new script graph.

1. In the **File name** box, enter "SPVideoPlayerBehavior" and then click the **Save** button.
1. In the **Script Machine** component, enter a name in the *Title* field for the graph: "Video Player Behavior."
1. Enter a description in the *Summary* field for the graph: "Video player behavior definition."

#### Putting the script graph together

1. In the **Script Machine** component, click **Edit Graph**. This opens the **Script Graph** window. Dock it next to the **Project** and **Console** tab so that we can see the script graph and **Scene** window at the same time. As we add nodes, you may want more space in the window; you can click the three-dot button and then select **Maximize** for achieve this, or click the **Full Screen** button in the upper right corner of the window.

![A screenshot of a video play Description ](../../media/sample-mesh-101/203-script-graph-maximized-v2.png)

1. We don't need the **OnStart** and **OnUpdate** events; delete them.

#### Get a reference to the PlayVideoButton GameObject

1. In the **Blackboard** section of the **Script Graph**, select the **Object** tab.
1. Enter the variable name "PlayVideo" in the text box and then press the Enter key or click the + button.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/204-playvideo-variable-v2.png)

1. Click the **Type** drop-down for the variable and then select **Game Object**.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/205-type-gameobject-v2.png)

1. Click the circle button next to **Value** and then, in the **Select GameObject** window, search for and select **PlayVideoButton**.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/206-value-playvideobutton-v2.png)

#### Add your new variable to the graph

1. In the **PlayVideo** variable, click and hold on the double lines to the left of **Type**, and then drag the variable and drop it in the graph, where it appears as a node.

> [!NOTE]
> A node is also called a *unit* in Visual Scripting. In this tutorial, we'll be using the term *node*.

![A screenshot of a video play Description ](../../media/sample-mesh-101/207-drag-variable-v2.png)

**TIP**: You may want to take a moment here to examine some of the components for the PlayVideoButton GameObject:

- *Mesh Interactable Properties*: This makes *PlayVideoButton* an object that you can interact with. This component helps to track interactions--note that in the image below it has some "hover" settings chosen. You can learn more about this component in our article named *Mesh Object and Avatar Interactions*.

- *Script Machine*: This has a script graph named *Button Base Behaviour.*

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/208-playvideobutton-components-v2.png)

If you go into Play mode, you'll see that a new component named **Mesh Interactable Body** is added to **PlayVideoButton**.

![A screenshot of a video play Description ](../../media/sample-mesh-101/209-body-v2.png)

This component is added automatically at runtime to interactable bodies; it exposes various properties to Visual Scripting such as *IsHovered* and *IsSelected*, which will come in handy in a moment.

Back in the script graph, we'll add a node that lets us know when the button is selected.

1. Click and hold on the outport port of the **PlayVideo** variable, and then release the mouse button. This opens the Fuzzy Finder.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/210-add-body-node-v2.png)

1. Search for "Mesh Interactable Body," click it, and then select "Is Selected." **Note**: This generates a Boolean value; you can confirm this in the **Graph Inspector**.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/211-is-selected-node-v2.png)

> [!TIP]
> The Graph Inspector can help you to better understand the makeup of all your nodes.
>
>![A screenshot of a video play Description ](../../media/sample-mesh-101/215-graph-inspector-v2.png)

#### Triggering the button

At this point, nothing is triggering the button yet. We need to add a node that ensures that every time the button is selected, the visual script runs.

1. Connect the output port of the "Is Selected" node to a new node that you create called "Microsoft Mesh: On State Changed." (In the Fuzzy Finder, search for "on state changed.")

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/212-on-state-changed-v2.png)

In addition to knowing when the button is selected, we also want to be able to set the player mode.

1. Connect the output control port of the "On State Changed" node to the "True" input control port of a new "If" node that you create.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/213-if-node-v2.png)

1. Connect the second output port of "On State Changed" to the second input port of the "If" node. Note that this points to the "False" value.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/214-if-node-false-v2.png)

#### Set a variable to let you know if the button is selected

1. Add a "Set Object Variable" node to the "True" output port of the "If" node.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/216-set-object-variable-v2.png)

1. In the **Blackboard**, go to the **Object** tab, and then create a variable named "isPlaying." Make the **Type** "Boolean" and the value false (the default).

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/217-isplaying-var-v2.png)

1. In the **Set Object Variable" node, click the variable name drop-down and then select "isPlaying."

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/218-select-isplaying-v2.png)

1. Drag the the "isPlaying" variable from the **Blackboard** to the graph to create a new "Get Object Variable" node.

    ![A screenshot](../../media/sample-mesh-101/325-get-var-node.png)

1. Connect the outport port of the "Get Object Variable" node to a new node you create called "Negate*.
1. Connect the output port of the "Negate" node to the bottom input port of the "Set Variable Object" node.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/326-negate-connected.png)

If the video is playing, set to true. If it's not playing, set to false. The "Negate" node negates whatever the value of "IsPlaying" is.

All the nodes you just added basically do one thing: tell you when the button is pressed.

#### Create a group for the nodes

1. Ctrl-drag over the nodes to add them to a group.

    ![A screenshot of a video play Description ](../../media/sample-mesh-101/220-group-v2.png)

1. Select the group title and then change it to "Check Button Press."

#### Define the Play action

In the following steps, we enable and disable two GameObjects: "Video" and "VideoStill."

When we want the video to play, we invoke "Video." It has an animation attached.

When we want the video to stop and just have the video screen show an image, we invoke "VideoStill."

We want this flow to be triggered every time the value of "isPlaying" changes.

1. In the portion of the graph below the "Check Button Press" group, add the "isPlaying" variable.
1. Attach a new "On State Changed" node to "isPlaying."

    ![A screenshot ](../../media/sample-mesh-101/221-two-nodes-v2.png)

#### Play the video when the Play button is pressed

1. Connect the control output port of the "On State Changed" node to the "True" input port of a new "If" node that you create.
1. Connect the remaining output port of the "On State Changed" node to the "False" input port of the "If" node.

    ![A screenshot ](../../media/sample-mesh-101/222-if-node-v2.png)

1. Attach the "True" output control of the "If" node to the control input port of a new "Game Object: Set Active" node that you create.

    ![A screenshot ](../../media/sample-mesh-101/224-set-active-v2.png)

If true (in other words, if the button has been pressed), we want the video to play, so let's set it up as follows:

1. Create two new Object variables as shown here:

    ![A screenshot ](../../media/sample-mesh-101/223-two-variables-v2.png)

1. Add the two new variables to the graph.

    ![A screenshot ](../../media/sample-mesh-101/225-add-nodes-to-graph-v2.png)

We want the "Video" GameObject to be active because it has the video animation attached to it. (Note that in the "Set Active" node attached to "Video, **Value** is selected.)

![A screenshot ](../../media/sample-mesh-101/226-set-active-to-video-v2.png)

Simultaneously, if the "If" node's value is true, we set the "VideoStill" GameObject to inactive.

1. Add a new "Game Object: Set Active" node to the graph.
1. Connect the output port of the first "Get Object: Set Active" node to the input control port of the new "Game Object: Set Active" node.
1. Connect the output of the "VideoStill" node to the next available input port of the second "Game Object: Set Active" node.

 (Note that in the "Set Active" node attached to "VideoStill", **Value** is *not* selected.)

![A screenshot ](../../media/sample-mesh-101/227-set-videostill-inactive-v2.png)

#### Stop the video if the Play button (now labeled the "Stop" button) is pressed while the video is playing

This is similar to what we just did, but in reverse: if the "If" node is false, we make the "VideoStill" GameObject the active object.

1. Select the four nodes that follow the "If" node.

    ![A screenshot ](../../media/sample-mesh-101/228-select-nodes-v2.png)

1. Right-click on a selected node and then choose **Duplicate Selection.**
1. Drag the duplicated nodes to an empty space towards the bottom of the graph.

    ![A screenshot ](../../media/sample-mesh-101/229-duplicated-nodes-v2.png)

1. Connect the "False" control output of the "If" node to the control input of the first "Game Object: Set Active" node in our duplicated set of nodes.

    ![A screenshot ](../../media/sample-mesh-101/230-if-is-false-v2.png)

1. In the first "Game Object: Set Active" node of the duplicate set, deselect "Value."
1. In the second "Game Object: Set Active" node of the duplicate set, select "Value."

    ![A screenshot ](../../media/sample-mesh-101/231-reverse-conditions-v2.png)

#### Changing the button label

1. In the **Blackboard**, go to the **Object** tab, and then create a variable named "VideoPlayerButtonLabel." The type should be TM Pro / "TextMeshPro".

For the Value, you need to add the "Label" GameObject that's a child to the "PlayVideoButton" GameObject. If you click the round button next to the **Value** field, the popup menu shows many GameObjects named "Label" and it's unclear which one you should choose. Here's a better way to ensure you're making the right choice:

1. In the **Hierarchy**, navigate to **Chapter 3** > **3.1 - Video** > **PlayerVideoButton** > **Label.**
1. Drag this **Label** GameObject from the **Hierarchy** and drop it in the **Value** field of your new variable.

    ![A screenshot ](../../media/sample-mesh-101/232-label-v2.png)

1. In the graph, drag a connection from the output control port of the second "Game Object: Set Active" node in the "if: True" sequence, and then drop it in empty space to open the Fuzzy Finder.

    ![A screenshot](../../media/sample-mesh-101/233-fuzzy-finder-v2.png)

1. Search for "set text" and then select "Text Mesh Pro: Set Text."

    ![A screenshot ](../../media/sample-mesh-101/234-textmesh-pro-v2.png)

1. Drag the "VideoPlayerButtonLabel" from the **Blackboard** and drop it in the graph to create a new node.
1. Connect the outport port of the new "Get Object Variable" node to the next available input port on the "Text Mesh Pro: Set Text" node.
1. In the "Text Mesh Pro: Set Text" node text field, type in "Pause."

    ![A screenshot ](../../media/sample-mesh-101/235-label-node-v2.png)

1. Repeat the steps above to create a label for the "If: False" sequence of nodes. This time, type in the label text "Play."

    ![A screenshot ](../../media/sample-mesh-101/236-set-text-play.png)

#### Test your work

1. In Unity, save the project and then press the Unity Editor Play
    button.

1. In the **Game** window, click the **Play** button you just worked
    on. This causes a brief video about wind turbines to play on the
    screen above the button.

    ![A screenshot of a video playback Description ](../../media/sample-mesh-101/image044.jpg)

1. When you've finished watching the video, press the button you've
    been editing again (it now has the label "Stop").

1. Press the Unity Editor Play button to exit Play mode.

### Station 3.2: Trigger an info dialog

For this feature, we'll enhance an existing visual script that causes an info dialog to appear when the avatar presses a button.

1. In the **Hierarchy**, collapse the **3.1 -- Video** GameObject.
1. In the **Scene** window, note that the Info Dialog Trigger station is to the right of the **3.1 -- Video Playback** station. Adjust the view so that you can clearly see Station 3.2.

    ![A screenshot of a computer Description ](../../media/sample-mesh-101/300-info-dialog.png)

1. In the **Inspector**, expand the GameObject named **3.2 -- Info Dialog**.

1. In the **Hierarchy**, select **Information_Button**.

![A screen shot of 3.2 - Info_Dialog GameObject Hierarchy with Information_Button selected](../../media/sample-mesh-101/301-information-button.png)

1. In the **Inspector**, navigate to the **Script Machine** component with the **Show Dialog** graph and then click the **Edit Graph** button.

    ![A screen shot of the Information_Button's Inspector](../../media/sample-mesh-101/302-edit-graph-button.png)

1. In the graph, connect the "True" output control port of the "If" node to the input control port of a new "Microsoft Mesh: Show Dialog" node that you create.

    ![A screen shot showing the if node connect to the new Show Dialog node.](../../media/sample-mesh-101/303-show-dialog.png)

1. In the **Show Dialog** node, click the **Message** field and then add this sentence:

Did you know that the world's largest wind turbine has blades longer than a football field?

This is the message that will appear in the info dialog.

![A screen shot showing Show Dialog node with a message added.](../../media/sample-mesh-101/304-show-dialog-message.png)

1. Select the drop-down that currently displays **OK**, and then, in the popup list, deselect **OK** and select **Continue**. This will add a "Continue" button to the info dialog that the user can click to close the dialog and continue in the experience.

    ![A screen shot showing Show Dialog node with a message added.](../../media/sample-mesh-101/305-show-dialog-continue.png)

#### Test your work

1. In the Unity Editor, save the project and then press the Unity Editor Play button.

1. Use the navigation keys to make your avatar back away from the button. Note that when your avatar is a certain distance away, the button rotates and isn't selectable.

1. Walk towards the button. At a certain point, the button stops rotating, signaling that you can now select it.

1. Select the button. The info dialog appears and displays the message you added to the **Show Dialog** node earlier.

1. When you're finished with info dialog, click its **Continue** button. Note that after you click the button, it disappears. To use the button again, you must exit and then re-enter Play mode.

    > [!TIP]
    > The distance and triggering elements in effect here are determined by the components of the **ProximityDetector** GameObject.

    ![A screen shot showing the ProximityDetector GameObject in the Hierarchy.](../../media/sample-mesh-101/306-proximity-detector.png)

1. Press the Unity Editor Play button to exit Play mode.

### Station 3.3: Teleport to the turbine generator

For this feature, we'll add some nodes to a script graph that allows participants
in the scene to teleport. When a participant presses the button, they're
teleported from their current location at Station 3.3 to an elevated
platform that's attached to a wind turbine generator. They can then
examine the generator.

![A picture containing outdoor, text, screenshot, windmill Description automatically generated](../../media/sample-mesh-101/image050.jpg)

#### Update the script graph

1. In the **Scene** window, note that the **3.3 -** **Teleport to Turbine** station is to the right of the **3.2 -- Info Dialog  Trigger** station. Adjust the view so that you can clearly see Station 3.3.
1. In the **Hierarchy**, collapse the **3.2 - Info Dialog** GameObject, and then expand the **3.3 - Teleport** GameObject.

    ![A screen shot](../../media/sample-mesh-101/307-teleport.png)

The button is all set up for you---we just need to add the nodes in the script graph that
give it the teleport behavior.

1. In the **Hierarchy**, select the **ChapterLabel** GameObject.

    ![A screen shot](../../media/sample-mesh-101/308-chapter-label.png)

    Note that in the **Inspector**, there's a **Script Machine** component named *Teleport to Open Air Platform* that contains a script graph named *SPTeleportToOpenAir*.

    ![A screen shot](../../media/sample-mesh-101/309-teleport-graph.png)

1. Click the **Edit Graph** button. Just as in the previous chapter, our graph already have some variables and nodes set up for you.

    ![A screen shot](../../media/sample-mesh-101/310-teleport-first-nodes.png)

In the **Teleport Button Behavior** group, the logic is similar to what you saw in Chapter 3.1: "If the button is selected, do something." We don't need to anything further to this group. We're going to make our changes to the second group, **Teleport to OpenPlatform**.

#### Create a Travel Point and add a reference to it

So what's a "Travel Point", you might be asking ... ? Basically, it's a component that you can use to define a point in space to spawn or teleport to. Normally, you would first create a *Travel Group*, and then add one or more Travel Points to it. We've already created the Travel Group for you in this project, so in the steps below, we'll add a Travel Point to that group. We'll then use that Travel point as the location the avatar will go to when they click the "Teleport" button. To learn more, see our article named *Mesh object and avatar interactions*.

1. In the **Hierarchy**, create a new empty GameObject as a child object to **TravelGroup** and then rename it "TeleportLocationWindTurbine".

    ![A screen shot](../../media/sample-mesh-101/311-teleport-location.png)

1. Click the **Add Component** button and then search for and add the *Travel Point* component.
1. In the **Inspector**, in the **Transform** component, enter the following values:

    Position: X = 6, Y = 58, Z =61
    Rotation: X = 0, Y = -270, Z = 0

    The avatar will teleport to this location.

1. Make the "TeleportLocationWindTurbine" GameObject inactive by deselecting the check box next to its name. If you have more than one TravePoint object active at runtime, the system won't spawn the avatar correctly.
1. In the script graph, go to the **Blackboard** and then select the **Object** tab.
1. Create a new Object variable named "TeleportLocationWindTurbine."
1. For the variable **Type**, select *GameObject."
1. For the **Value**, select the "TeleportLocationWindTurbine" GameObject.

    ![A screen shot](../../media/sample-mesh-101/312-var-for-teleporting.png)

1. Drag the new "TeleportLocationWindTurbine" variable to the graph to add it as a node.

    ![A screen shot](../../media/sample-mesh-101/313-add-node.png)

1. Connect the "True" outport control port of the "If" node to a new "Game Object: Set Active" node that you create.

    ![A screen shot](../../media/sample-mesh-101/314-set-active-node.png)

1. Connect the output data port of the *TeleportLocationWindTurbine* node to the first available input data port of the new "Get Object: Set Active" node.

    ![A screen shot](../../media/sample-mesh-101/315-connect-to-set-active.png)

1. Click the **Value** check box in the "Game Object: Set Active" node to set its value to "True."
1. Connect the output control port of the "Game Object: Set Active" node to a new "Travel Point: Travel to Point" node.

    ![A screen shot](../../media/sample-mesh-101/316-travelpoint-node.png)

1. Connect the output data port of the "TeleportLocationWindTurbine" node to the first available data input port on the "Travel Point: Travel to Point" node.

    ![A screen shot](../../media/sample-mesh-101/317-connect-from-wind-turbine.png)

1. Connect the output control port of the "Travel Point: Travel to Point" node to the input control port of the "Set Object Variable" node located on the far right of the graph.

    ![A screen shot](../../media/sample-mesh-101/318-connect-to-teleportnow.png)

#### Test your work

1. In the Unity Editor, save the project and then press the Unity Editor Play button.

1. Go to Station 3.3 and then click the "Teleport" button to teleport up to the wind turbine generator.

    ![A screenshot](../../media/sample-mesh-101/319-teleport-button.png)

    ![A screenshot of a computer Description automatically generated](../../media/sample-mesh-101/image055.jpg)

1. In the **3.3 -- Generator** information box, select the **Show/Hide Generator** button. A window opens up in the side of the wind turbine and you can see the generator inside.

    ![A computer screen shot of a machine Description ](../../media/sample-mesh-101/image057.jpg)

Feel free to step up close to the generator and have a look. It's pretty
cool! When you've finished, navigate back out and then press the
**Show/Hide Generator** button. This closes the window.

**Go to Chapter 4**

At this point, the participant in the experience would be ready to move
on to Chapter 4 and learn about wind turbine activities related to
physics. Just like with Chapter 3, there's a Sphere Terrace that
contains the stations for Chapter 4. To get there:

1. Rotate around in the opposite direction from the wind turbine
    generator and walk towards the **3.3 -- Go to Chapter 4**
    information box.

    ![A screenshot of a computer Description ](../../media/sample-mesh-101/image058.jpg)

2. Press the **Teleport to Chapter 4** button.

    ![A screenshot of a computer Description ](../../media/sample-mesh-101/image059.jpg)

    As advertised, this places the avatar in front of the stations for Chapter 4 and Mesh Physics.

    ![A picture containing text, screenshot, multimedia software, graphics software Description automatically generated](../../media/sample-mesh-101/image060.jpg)

### Chapter 3: Summary

In this chapter, you used Mesh Visual Scripting to add features that empower participants in
your experience to do the following:

1. Press a button that causes an educational video about wind turbines
    to play.

2. Press a button that triggers the display of an info dialog
    about wind turbines.

3. Press a button that teleports the participant from the ground up to
    a platform attached to a wind turbine generator, where they can
    examine the generator up close.
