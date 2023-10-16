---
title: Mesh Visual Scripting programmer's guide
description: Learn about how to create scripts using Visual Scripting in Mesh.
ms.service: mesh
author: typride
ms.author: vinnietieto
ms.date: 10/3/2023
ms.topic: Guide
keywords: Microsoft Mesh, scripting, visual scripting, coding, nodes, units, graphs
---

# Mesh Visual Scripting Programmer's Guide

Go to the [Visual Scripting overview article](visual-scripting-overview.md)

## Limitations

- Only a subset of Unity functionality is exposed to visual scripts.
- Variables and properties with non-simple types (including object references) aren't automatically shared. See [Sharing and networking](#sharing-and-networking) below to learn more about this.

## Hello World

The simplest visual script you can create is one that just opens a message box:

![Screen shot of the visual script graph of the Hello World sample](../../../media/mesh-scripting/visual-scripting/helloworld-script.png)

This is how it looks in Mesh:

![Mesh browser window with a popup dialog displaying Hello World and an OK button](../../../media/mesh-scripting/visual-scripting/helloworld-runtime-browser.png)

![Screen shot of the Unity Editor with the Mesh Visual Scripting Hello World scene open.](../../../media/mesh-scripting/visual-scripting/helloworld-editor.png)

## Testing your scripts

Before you upload your scene to Mesh, you can develop and test visual scripts, even with multiple clients in split screen mode, in Mesh Playmode.

## Visual script diagnostics in the Editor

When a GameObject with a Script Machine is selected in the transform hierarchy, Mesh displays the _Mesh Visual Scripting Diagnostics_ panel at the bottom of the Inspector panel:

![Screen shot of the Mesh Visual Scripting diagnostics panel](../../../media/mesh-scripting/visual-scripting/helloworld-diagnostics.png)

The diagnostics panel gives immediate feedback on any warnings or errors that might prevent your scripts from working well in Mesh.

**_Current limitation:_** Future versions of the diagnostics panel may also give insight into the visual script's use of shared variables and properties and display additional diagnostics and warnings.

## Uploading to Mesh

Use the _Mesh Uploader_ to upload scenes that contain visual scripts. To open the Uploader, on the **Mesh Toolkit** menu, select **Environments**.

**Note**: Mesh Uploader validates visual scripts before upload and refuses to upload when there are any validation errors in any visual scripts. Detailed diagnostics are output to the **Console**.

## Sharing and networking

### Shared and local script state

Mesh uses Unity Visual Scripting, which is designed to work without networking. Visual scripts run on each client independently. However, the users' Mesh experience is shared; all users experience a single shared scene that looks the same on all clients.

The effect of a visual script's execution is how it changes the scene's state.

By default, Mesh automatically replicates scene changes done by visual scripts on one client to all other clients. Aside from everything that's shared in a scene, some state remains independent on each client (in other words, local).

Local changes temporarily take precedence over changes coming in from clients. Example: If you keep animating an object locally, your local animation isn't compromised by changes coming in from other clients.

There's some automatic update rate limiting. A client doesn't send additional updates while one is still in flight; there's one update sent per roundtrip through the server. This amounts to approximately five to six updates per second in practical situations. This means that a smooth animation driven by one client won't look smooth on other clients. The best practice is to do smooth animations locally, ideally not through visual scripts but through the normal Unity animation system.

Eventual consistency of shared state is guaranteed (even if clients' states can temporarily be different).

Local state:

- Natural local state – sounds, UI, rendering.
- User-controlled local state – sub-scenes marked with the **Local Script Scope** component.
- Technical local state – objects that aren't part of the scene hierarchy (for example, renderer materials, assets).

Shared state:

- Limited to visual script variables and the properties of GameObjects and scene components that are part of the scene hierarchy.
- Only variables and properties of simple types can be replicated: integers, floating-point numbers, booleans, strings, `Color`, `Vector2`/`3`/`4`, `Quaternion`, `Matrix4x4`, and `Rect`.

Any change to shared state is sent over the network. This increases network traffic and, if used carelessly, can consume significant bandwidth.

### Shared and local script triggers

All visual script flows start in response to an event.

- If the event originates on a single client (for example, the user clicks a button), the visual script executes only on that client.
- If the event occurs on all clients, the visual script executes on all clients (for example, timer event, shared property change, shared variable update, avatar enters trigger, physics body touches collider).

If a local script sets a shared variable and a second script listens to changes to this variable (using the **On State Changed** trigger; see below), the second script will be executed on all clients.

Mesh offers some special script nodes:

- **On Interval** triggers at regular intervals synchronously on all clients.
- **On State Changed** triggers when its inputs change (for example, shared properties, shared variables, local).
- **Show Dialog** displays a message dialog with custom text that may optionally provide buttons as response options.

Mesh makes certain trade-offs in favor of simplicity:

- If more than one client tries to change the same data, the last client wins (instead of using a transaction-based data update model).
- To ensure data consistency, visual scripts that run on all clients must not read and then write shared properties or variables. If this occurs, it triggers a runtime error and aborts the script flow's execution.

## Best practices

Visual scripts are significantly slower than native C# code. In addition, Mesh augments visual scripts with network and other integration features, and seemingly low-overhead visual script actions may result in network traffic.

Performance issues in visual scripts are almost always caused by the scripts doing high-frequency updates of variables or component properties that are shared by default.

- Do use **Local Script Scope** components liberally to make sure only variables and component properties that _need_ to be synchronized across clients incur networking overhead. Anything animated locally with a visual script should not be shared.

- Do use the **On State Changed** script trigger to start script flows in response to changing variables or component properties. This works both for local and shared state. It's also the recommended way to synchronize local animations.

- Do use the **On Interval** script trigger instead of a high-frequency trigger like **On Update** to start script flows in controllable, regular intervals.

Things to be aware of:

- Avoid triggering visual scripts every frame (for example, **On Update**). Instead, use **On State Changed** or **On Interval** if possible.

- Avoid triggering visual scripts every frame on many objects.

- Don't update shared properties at high frequency. Instead, consider making high-frequency updated properties local by using the **Local Script Scope** component. Remember that visual script variables are also shared by default!

- Don't use object variables if flow variables would work.

- Avoid updating shared properties or variables in visual scripts that are triggered simultaneously on all clients.

- Avoid setting physics properties (transform and velocity) on the same physics body on multiple clients at the same time. This can easily happen by accident in visual scripts that respond to shared scene change triggers.

- Don't try to fix performance problems by consolidating several script flows that work on individual objects into a single script flow that works on many objects. The overhead of starting a script flow is negligible, and the added complexity you have to add to consolidate your script may very well negate any slight performance benefit you might get from reducing the number of ScriptMachines.

**Tips**

- Component properties and visual script variables that have simple types are automatically shared across clients in a session.
- To exclude parts of your scene from this automatic sharing, add a **Local Scene Scope** component. Everything underneath that transform won't be shared automatically.
- To do something in regular time intervals in sync across clients, use the **On Interval** trigger node.
- To do something in response to certain component properties or visual script variables changing (for example, because this or some other client was setting them in a visual script), use the **On State Changed** trigger
- There are additional Visual Scripting functions provided by Mesh&#8212;see the _Microsoft_ > _Mesh_ and _Microsoft_ > _Events_ > _Mesh_ sections in the Fuzzy Finder.

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

## Mesh integration

**_Current limitation:_** This section describes a preview of features that are still works in progress.

Generally, integration with other components is often done by changing and listening to component property changes. For example:

- Interactables: observe "Is Hovered" and "Is Selected" properties.
- Physics interactions: observe bodies in trigger volume or in contact with collider.

- Avatars: read avatar position, view rotation, and name plate. **_(Not available yet.)_**
- Session state: list participants and read participant info. **_(Not available yet.)_**
- Cloud Scripting: operate in tandem with cloud scripts that can read and write variables and component properties. **_(Not available yet.)_**

Some components provide local actions:

- Audio Manager
- Timeline
- Animators
- Rendering: read and write material and shader properties

Physics is handled specially because simulation for any given physics object is always authoritatively done by one client only: its owner. To make this work, setting physics properties triggers an automatic ownership transfer to the client that applies the change.

## Next steps

> [!div class="nextstepaction"]
> [Node reference](visual-scripting-node-reference.md)



