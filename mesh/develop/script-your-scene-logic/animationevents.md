---
title: AnimationEvents
description: Learn about how to use AnimationsEvents in your project.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 11/27/2023
ms.topic: Guide
keywords: Microsoft Mesh, Unity, environments, scenes, events, animations, timelines, unityevents, animationevents, scripting, script graph, science building
---

# AnimationEvents

You can increase the power of animation clips with *AnimationEvents*, which allow you to employ user-driven callbacks to trigger logic from a clip at a specific point in time, or a specific frame, that you specify. This article walks you through a brief tutorial for setting up and using AnimationEvents.

**IMPORTANT:** AnimationEvents are only allowed to initiate [visual script](../script-your-scene-logic/visual-scripting/visual-scripting-overview.md) flows, which can then set properties and invoke methods. An AnimationEvent points to *ScriptMachine.TriggerAnimationEvent*. From there, corresponding visual script flows can be triggered through "Animation Event" event nodes.

> [!TIP]
> You can also create [UnityEvents](./unityevents.md) to employ user-driven callbacks.

For this example, we'll use the [ScienceBuilding sample](../getting-started/samples/science-building.md) which is contained in the [Mesh toolkit](../build-your-basic-environment/add-the-mesh-toolkit-package.md) and is already set up with assets you can use. We'll work with an animation clip where a robot points to an informational popup; we'll insert an AnimationEvent into the clip that causes the **Console** to display a message when the robot points. We're keeping this simple for learning purposes but you can use AnimationEvents to trigger a range of effects, sounds, or other actions during an animation.

1. Open the *ScienceBuilding* project, and then open the *ScienceBuilding* scene.
1. Dock the **Console** window to the right of the **Scene** window so that you can see both simultaneously.
1. In the **Hierarchy**, search for and then select the *ReceptionBot* GameObject.

    **TIP**: To easily find *ReceptionBot*, type "bot" in the **Hierarchy** search box.

1. Move the cursor over the **Scene** window and then press F on your keyboard to zoom in close to *ReceptionBot*. You may need to adjust the view further in order to see *ReceptionBot* more clearly.

### Copy ReceptionBot's animation

1. In the **Inspector**, navigate to the **Animation** component.

    Note that the component contains an animation named *ReceptionBot_clip*. This animation causes *ReceptionBot* to point to various info dialogs that pop up around it. However, the animation is set to read-only, which means you won't be able to add an AnimationEvent to it. To get around this, we can copy it and then use the editable copy.

1. In the **Project** window, search for "reception." This will return a list that includes **ReceptionBot_clip**. 

    **IMPORTANT**: There are two items in the list with the name "ReceptionBot_clip." One is an .FBX file, and the other is the  animation clip we're interested in. Make sure you select the *animation clip*, not the .FBX file, before proceeding with the next step of copying. You can confirm that you've selected the right item by viewing its full name in the status bar at the bottom of the window and ensuring that it has the *.anim* extension.

    ![Screenshot of the two similarly named items with the correct one to copy outlined in red.](../../media/enhance-your-environment/unityevents/016-anim-copy.png)

1. Select the **ReceptionBot_clip** animation clip and then press Ctrl + D to copy it.
1. Rename the copy "ReceptionBot_clip_copy."
1. In the **Hierarchy**, search for and then select the *ReceptionBot* GameObject.
1. In the **Inspector**, navigate to the **Animation** component and note that it currently points to **ReceptionBot_clip**.
1. Drag **ReceptionBot_clip_copy** from the **Project** folder and then drop it in the **Animation** component's **Animation** property, replacing the previous animation clip.

    ![Screenshot of the animation copy in ReceptionBot's Animation component.](../../media/enhance-your-environment/unityevents/017-drag-anim-copy-clip.png)

1. In the component's **Animations** section, select the **Element** that contains **ReceptionBot_clip** and click the minus ("-") button to delete it.

    ![Screenshot of the original animation clip being deleted.](../../media/enhance-your-environment/unityevents/018-delete-original-anim.png)

### Viewing the animation

1. If you haven't done so already, in the **Scene** window, adjust the view so that you can clearly see *ReceptionBot* from the front.
1. On the menu bar, select **Window** > **Animation** > **Animation**.
1. Dock the **Animation** window next to the **Project** window.
1. In the **Animation** window, move the playback head to frame 224 as show below. Note that in the **Scene** window, *ReceptionBot* is pointing to the first in a series of informational popups. We'll insert our AnimationEvent at this frame.

    ![Screenshot of ReceptionBot pointing at the first info popup and the Animation window showing the frame when this occurs.](../../media/enhance-your-environment/unityevents/012-robot-points.png)

    First, though, we'll create the visual script that we'll be calling from the animation.

**TIP**: You can scrub the Animation timeline to zero in on the precise frame that you want to add an AnimationEvent to.

### Create the Visual Script

1. With **ReceptionBot** selected in the **Hierarchy**, select the **Add Component** button in the **Inspector** and then add the **Script Machine** component.
1. Click the **Source** drop-down and then select **Embed**.
1. Click the **Edit Graph** button.
1. Dock the **Script Graph** window next to the **Animation** window and then delete the two default nodes, **On Start** and **On Update**.

    ![Screenshot of the new Script Window with the default nodes displayed.](../../media/enhance-your-environment/unityevents/013-delete-default-nodes.png)

    There are two types of AnimationEvent nodes, as shown below.
    
    ![Screenshot of the two types of AnimationEvent nodes.](../../media/enhance-your-environment/unityevents/026-animationevent-node-two-types.png)    
    
    The function called by an AnimationEvent has the option to take one parameter; it can be a float, string, int, or object reference, or an AnimationEvent object. In the node on the right, you can add a name. This is the node we'll use here.

1. Right-click in the script graph and then, in the Fuzzy Finder, search for "named anim" and then add the *Named Animation Event* node.
1. In the node, add the name "ShowMessage."

    ![Screenshot of the AnimationEvent node with the name Show Message.](../../media/enhance-your-environment/unityevents/014-node-with-name.png)

1. Drag a connector from the output control port of the **AnimationEvent** node and then create a new **Debug Log** node (in the Fuzzy Finder, search for **debug log**.)
1. Drag a connector from the data input port of the **Debug Log** node and then create a new **String** (Literal) node (in the Fuzzy Finder, search for **string literal**.)
1. In the **String** node, add this text: "Bot pointed to the first popup."

    ![Screenshot of the three nodes required for our script graph.](../../media/enhance-your-environment/unityevents/015-string-node-with-message.png)

### Add the AnimationEvent in the Animation window

1. Select the **Animation** tab.
1. In the **Animation** window, ensure that the playback head is at frame 224.
1. Click the Add Event button. This will cause an AnimationEvent marker to appear at frame 224.

    ![Screenshot of the Add Event button in the Animation window.](../../media/enhance-your-environment/unityevents/019-add-event-button.png)

1. In the **Inspector**, select the **Function** drop-down, and then select **Script Machine** > **Methods** > **TriggerAnimationEvent (Animation Event)**.

    ![Screenshot of the Animation Event's Function drop-down with Trigger Animation Event Animation Event selected.](../../media/enhance-your-environment/unityevents/020-choose-function.png)

1. Recall that when you created the script machine for *ReceptionBot* you named the **AnimationEvent** node *ShowMessage*. 

    ![Screenshot of the AnimationEvent node with the name Show Message.](../../media/enhance-your-environment/unityevents/014-node-with-name.png)

1. In the **Inspector**, add this name to the text field for the **String** property. This ensures that when the AnimationEvent in the **Animation** window fires at frame 224, it connects to the **AnimationEvent** node in the script graph and triggers the function that displays the message in the **Console**.

    ![Screenshot of the Animation Event properties with the String property set to Show Message.](../../media/enhance-your-environment/unityevents/021-string-property-filled-in.png)

### Test your work

1. Save the project and then press the Unity Editor Play button.
2. Note that after a few seconds, the message from the **String** node in the script graph, "Bot pointed to the first popup.", displays in the **Console**.

    ![Screenshot of the Console with the message Bot pointed to the first group displayed and the String node that generates that same message.](../../media/enhance-your-environment/unityevents/022-message-in-console.png)

Your [Mesh Emulation Mode](../debug-and-optimize-performance/mesh-emulator.md) avatar, with attached camera, doesn't appear in the reception area by default, so you can't initially see the synchronization between the pointing *ReceptionBot* and the display of the message in the **Console**. If you want to view this synchronization, you must navigate to the reception area and get a close-up view of *ReceptionBot*.

![Screenshot of Reception Bot pointing to the first info popup and the Console displaying the message generated at that point by the Animation Event.](../../media/enhance-your-environment/unityevents/023-view-bot-pointing.png)    

The reception area is forward and to the left of the original vantage point of the camera. You can navigate there while in Play mode.

![Screenshot of the view from the camera vantage point with the reception area highlighted.](../../media/enhance-your-environment/unityevents/025-reception-area-ground-view.png)

**Navigation tips**:

Move forward:   W  
Move back:      S  
Move left:      A  
Move right:     D  
Pan left:       Q  
Pan right:      E  

You can also pan up/down/left/right with your mouse's buttons.

**TIP**: In the **Console** window, it's easier to see the "Bot pointed to the first popup" message when the window is clear. Click the **Clear** button as needed to remove other system messages that appear. 




