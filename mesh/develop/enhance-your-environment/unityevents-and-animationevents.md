---
title: UnityEvents and AnimationEvents
description: Learn about how to use UnityEvents and AnimationsEvents in your project.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 10/23/2023
ms.topic: Guide
keywords: Microsoft Mesh, Unity, environments, scenes, events, animations, timelines, unityevents, animationevents, scripting, script graph
---

# UnityEvents and AnimationEvents

This article contains a brief tutorial on how to use UnityEvents with Visual Scripting. **IMPORTANT**: UnityEvents can *only* be used in script graphs; they're not available in cloud scripting.

## UnityEvent in a basic script

1. Drag the Console window into the right side of the Scene window.
1. On the menu bar, select **GameObject** > **UI** > **Legacy** > **Button.**
1. Ensure that **Button** is selected, and then, in the **Inspector**, rest **Button** so that its **Rect Transform** component's XYZ values are all set to zero.

    ![Screenshot of a button in the Scene window.](../../media/enhance-your-environment/unityevents/001-button.png)

1. Scroll down to the bottom of the **Inspector** and note that **Button** has an **On Click()** UnityEvent attached. 

    Right now, there are no events to trigger--we'll add something here in a moment. First, let's create the event. We'll keep it simple and set things up so that when you click the button, a message appears in the **Console**.

1. On the menu bar, select **GameObject** > **Create Empty**.
1. Change the empty's name to *MessageHolder*.
1. In the **Inspector**, select the **Add Component** button and then search for and add **Script Machine**.
1. In the **Script Machine**, select the **Source** drop-down and then select **Embed**.
1. Select the **Edit Graph** button, and then, in the script graph, delete the two default nodes.
1. Right-click in the graph and then add the **UnityEvent Event** node.

    ![Screenshot of the UnityEvent event node.](../../media/enhance-your-environment/unityevents/002-unityevent-event.png)

1. Name the **UnityEvent Event** node: in the text field in the node, add the name *ShowClickMessage*.

    ![Screenshot of the UnityEvent event node with a name in its text field.](../../media/enhance-your-environment/unityevents/005-unityevent-event-node-with-name.png)

1. Drag the control output port of the **UnityEvent Event** node and then, in the Fuzzy Finder, search for and add the **Debug Log Message** node.

    ![Screenshot of the Debug Log Message node attached to the UnityEvent Event node.](../../media/enhance-your-environment/unityevents/003-debug-log.png)

1. Drag the data input port of the **Debug Log Message** node and then, in the Fuzzy Finder, search for and add the **String Literal** node.
1. In the **String Literal** node, add the text: "You clicked the button!"

    ![Screenshot of the String Literal node with the message you clicked the button.](../../media/enhance-your-environment/unityevents/006-string-node-with-message.png)

    That's all we need for the script. Let's connect the UnityEvent in the button to the script.

1. In the **Hierarchy**, select **Button (Legacy)** and then navigate to its **On Click()** UnityEvent.
1. Click the plus sign ("+") in the UnityEvent.
1. Drag the **MessageHolder** GameObject from the **Hiearchy** and then drop it in the field in the **On Click()** that says **None (Object)**.

    ![Screenshot of the button's on click event with a link to the Message Holder object.](../../media/enhance-your-environment/unityevents/007-messageholder-in-onclick-event.png)

1. Select the **No Function** drop-down, then point to **Script Machine**, and then select **TriggerUnityEvent (string)**.

    ![Screenshot of the menu item trigger unity event string.](../../media/enhance-your-environment/unityevents/008-trigger-unity-event-string.png)

    The final step here is to add the *name* of the UnityEvent you want to trigger to the **On Click()** event. In a more complex script graph, you might have several to choose from, each with a different name; in our simple example, there's only one.

    ![Screenshot of the UnityEvent node name added to the On Click event.](../../media/enhance-your-environment/unityevents/009-add-node-name-to-onclick.png)

1. Click the Unity editor Play button.
1. In the **Game** window, click the button. This causes the "You clicked the button!" message from the String node in the script graph to appear in the **Console**.

    ![Screenshot of the Console with the you clicked the button message displayed.](../../media/enhance-your-environment/unityevents/010-message-appears-in-console.png)

**Notes**

- You can't pass any parameters into the script flow.


## UnityEvents and Timeline Signals

You can trigger a UnityEvent from a Timeline by adding a Signal Emitter, then creating a Signal Asset and connecting it to the Signal emitter, and then creating a Signal Receiver component. Inside the Signal Receiver, you select a Signal Asset and then choose the function you wish you call (in other words, the UnityEvent). This is similar to how the UnityEvents work in the Button example explained above--the same event callback, *ScriptMachine.TriggerUnityEvent*, is used.

In this example, we created a Signal Asset named *Clicks*.

![Screenshot of a signal emitter in the inspector with the signal receiver component showing a Unityevent that will be triggererd.](../../media/enhance-your-environment/unityevents/011-signal-emitter.png)

To learn more about using Signals in the Timeline, [see this Unity Blog](https://blog.unity.com/engine-platform/how-to-use-timeline-signals).

## AnimationEvents





