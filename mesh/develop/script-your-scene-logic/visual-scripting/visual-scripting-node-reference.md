---
title: Mesh Visual Scripting node reference
description: Learn about the Mesh nodes available for Visual Scripting in Mesh.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 10/3/2023
ms.topic: Guide
keywords: Microsoft Mesh, scripting, visual scripting, coding, nodes, units, graphs
---

# Mesh Visual Scripting node reference

Go to the [Visual Scripting overview article](visual-scripting-overview.md)

## On Interval

![On Interval event node](../../../media/mesh-scripting/visual-scripting//node-OnInterval.png)

The **On Interval** event node triggers a script flow in regular time intervals synchronized across all clients in the same room.

- **Interval**: Interval (in seconds) between events.
- **Delay**: Delay (in seconds) before the first event. You can use this to interleave events with the same **Interval** triggered by different **On Interval** nodes.

## On State Changed

![On State Changed event node connecting to a Get Variable node](../../../media/mesh-scripting/visual-scripting//node-OnStateChanged-variable.png)

The **On State Changed** event node triggers when any of its inputs changes its value. This is a powerful mechanism that lets your scripts respond to state changes caused by user interaction or other visual scripts, both locally and on other clients in the same room.

- **Values**: Specifies how many input ports you would like to observe. Up to 10 input ports can be observed simultaneously. **On State Change** triggers when any of them changes its value.
- **In 0**, **In 1**, and more in this sequence: Inputs observed for state changes. You can attach any data node to these inputs: **Get Variable** or any component property (instance or static).
- **Out 0**, **Out 1**, and more in this sequence: Outputs corresponding to the **In 0** (and so on) inputs that return the observed values.

When observing script variables or component properties, **On State Changed** usually operates by registering appropriate callbacks internally, avoiding the need to constantly re-evaluate its inputs. When an appropriate callback isn't available, like in the following example, the **On State Changed** node turns red and the _Graph Inspector_ panel warns that the input can't be observed efficiently and is therefore disabled:

![Screen shots of the On State Changed event node connecting to the result of comparing a Get Variable node to an integer literal, no polling.](../../../media/mesh-scripting/visual-scripting//node-OnStateChanged-volatile.png)

In this case, you can select **Allow Polling** in the _Graph Inspector_ panel to force **On State Changed** to detect changes by constantly re-evaluating its inputs. The node retains a yellow bar along its top to remind you that it's observing an input at an increased runtime cost.

![Screen shots of the On State Changed event node connecting to the result of comparing a Get Variable node to an integer literal, allow polling.](../../../media/mesh-scripting/visual-scripting//node-onstatechanged-allow-polling.png)

## Show Dialog

![Screen shot of the Show Dialog action node](../../../media/mesh-scripting/visual-scripting//node-ShowDialog.png)

The **Show Dialog** node displays a dialog box with custom message and one or several buttons that allow the user to dismiss the dialog.

- **Text**: Message shown in the dialog box. The message text will be word-wrapped if necessary.
- **Buttons**: Selection of buttons to present to the user. The following buttons can be shown: _OK_, _Cancel_, _Yes_, _No_, _Confirm_, _Next_, _Retry_, _Continue_, _Leave_.
- **Result**: Variable name to store the user's response in when they dismiss the dialog by selecting a button. (If left empty, the response is discarded.)
- **Target**: GameObject with a **Variables** component to store the user's response.

If a **Result** variable is defined, it will be reset to an empty string as soon as the **Show Dialog** node is entered, and set to user's response asynchronously when the user selects a button to dismiss the dialog. The stored value is the button's unlocalized label from the list above. Use an **On State Changed** event node to react to the user's response like in the following example:

![Screen shot of the Show Dialog node collecting the user response in a variable, followed by an On State Changed node responding to the variable change](../../../media/mesh-scripting/visual-scripting//node-ShowDialog-response.png)

The **Result** variable can be local or shared. If it's shared, the user's response is sent to all clients in the same room, and the **On State Changed** event node triggers on all clients to react to the user's response.

## Physics events nodes

The physics event nodes **On Trigger Enter**, **On Trigger Exit**, **On Collision Enter**, and **On Collision Exit** are reliably networked. By default, these events reliably trigger on all clients in the room; however, if the physics collider observed by these event nodes is in scope of a *Local Physics Scope* component, the events reliably trigger on exactly one client. This makes it possible for the script flows that are triggered to reliably read and write shared state (for example, update a shared score variable).

## Security

Mesh protects users from threat scenarios such as these:

- Compromised scene content&#8212;for example, malicious attempts to access sensitive local data.
- Compromised client or transport channel&#8212;for example, malicious attempts to read or write inaccessible remote data on other clients.

To achieve this, Mesh runs visual scripts in a sandbox (like JavaScript in a web browser).

At scene startup, Mesh uses a curated allowlist to validate visual scripts to limit access to certain types of Unity components and a safe subset of their properties.

At scene runtime, Mesh limits access to certain parts of the scene:

- Locally: by preventing access to Mesh internals and other sensitive data.
- Remotely: by checking that the scene's author intends this part of the scene to be modified. This is done by statically analyzing visual scripts on the receiver's side for their potential scene writes.

Examples:

- A malicious local visual script wants to give all avatars bobble heads. To that end, it attempts to scan the entire scene for GameObjects that represent avatar heads. Mesh automatically filters the scanning results to exclude the avatar system.
- A malicious remote client wants to deface the scene by flipping all GameObjects upside down. To achieve that, it sends a property update that sets the vertical scale of each GameObject in the scene. However, since no visual script on the receiving client is designed to do anything like that, the local client ignores the remote input.