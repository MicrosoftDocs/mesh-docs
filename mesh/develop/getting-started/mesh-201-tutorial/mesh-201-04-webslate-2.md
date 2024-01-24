---
title: Mesh 201 Load a local shared HTML file into a WebSlate
description: Learn how to load a local shared HTML file into a WebSlate.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 1/23/2024
ms.topic: Tutorial
keywords: Microsoft Mesh, getting started, Mesh 101, tutorial, scripting, visual scripting, code, coding, interactivity, webslates, HTML
---

# Mesh 201 Tutorial Chapter 4: Load a local shared HTML file into a WebSlate

In the previous chapter of this tutorial, you enabled a button to load a local non-shared HTML file into a WebSlate. In this chapter, we'll also set up an HTML page load, but this time it will have the capability to be shared among all attendees in the experience.

## Navigate to the buttons

1. In the **Scene** window, change your view so that you're looking at Station 1.1, pictured below.

![A screenshot of a computer Description ](../../../media/mesh-201/032-station-one-one.png)

Just as in the previous chapter, there's already a GameObject in place with some descriptive text but this time there are two buttons: **LoadButton1** and **LoadButton2**.  a **Load** button. We'll complete the station by adding a WebSlate below the buttons and then updating script graphs attached to the buttons. When an attendee clicks a button, a web page is loaded and is *shared* among all other attendees in the experience. Each button loads a slightly different type of content.

1. In the **Hierarchy**, collapse the GameObject named **1.0 - LocalWebslate**.
1. Expand **1.1 - StaticContentWebslate**. In the previous chapter, you were required to add a WebSlate prefab, but in this chapter we've already done it for you.

![A screenshot of a computer Description ](../../../media/mesh-201/033-slate-in-hierarchy.png)

1. Expand **ChapterLabel** and its child object **Actions**. The buttons we'll be working with, **LoadButton1** and **LoadButton2**, are located here.

![A screenshot of a computer Description ](../../../media/mesh-201/034-buttons-in-hierarchy.png)

## Edit the script graph

1. In the **Hierarchy**, select **LoadButton1**.

    In the **Inspector**, you can see that that **LoadButton1** has a **Script Machine** component containing an embedded script named **Load HTML on a Shared Webslate** and a variable that we'll be using in the script.

    ![A screenshot of a computer Description ](../../../media/mesh-201/035-loadbutton1-script-graph.png)

1. In the **Script Machine** component, click **Edit Graph**. 

As in the previous chapter, the script graph has already been started for you.

    ![A screenshot of a computer Description ](../../../media/mesh-201/037-loadbutton1-script-graph.png)

### Add the *Mesh Interactable Body: Is Selected* node

Our first task is to add a *Mesh Interactable Body: Is Selected* node. As discussed in the previous chapter, you have a choice of *two* "Mesh Interactable Body: Is Selected" nodes. The text above each node can help you to confirm the behavior.

    ![A screenshot of a computer Description ](../../../media/mesh-201/027-is-selected-local-or-global.png)

For Station 1.0, we wanted only the person triggering the event to experience it, so the script contained the node that says "Is Selected *Locally*. This time, we want *all* attendees to share the event, so we'll select the other node for this--the one that simply says "Is Selected".

1. Click and hold on the Data Output port of the **Game Object** node, and then release the mouse button. This opens the Fuzzy Finder. **WARNING**: Once you open the Fuzzy Finder, don't click anywhere outside of the Unity interface. This closes the Fuzzy Finder and causes unpredictable behavior in the Script Graph.
1. In the Fuzzy Finder, search for "Mesh Interactable Body: Is Selected" and then select it. 

    ![A screenshot of a computer Description ](../../../media/mesh-201/038-is-selected-menu-item.png)

    This adds the node to the graph.

1. Drag a connector from the Data Output port of the **Mesh Interactable Body: Is Selected** node and then connect it to the Data Input port of the **Microsoft Mesh: On State Changed** node.

    ![A screenshot of a computer Description ](../../../media/mesh-201/039-connect-to-on-state-changed.png)

## Add the *Web Slate: Load HTML Content (HTML Asset)** node

The **Get Component in Children** node already contains the target we want--**WebSlateFramed**--so we can move forward and add the next node.

1. Drag a connector from the Control Output port of the **Mesh Interactable Body: Is Selected** node and then create a new *Web Slate: Load HTML Content (HTML Asset)* node. **Note** that there are two nodes with very similar names. 

    ![A screenshot of a computer Description ](../../../media/mesh-201/023-load-html-content.png)

    You want the one that says "HTML **Asset**", not "HTML **Content**.

    ![A screenshot of a computer Description ](../../../media/mesh-201/024-node-content-or-asset.png)

1. Drag a connector from the Data Output port of the **Get Component in Children** node and then connect it to the Data Input port of the **Web Slate: Load HTML Content** node.

1. We already have the web page we want to load in a **Get Variable** node. Drag a connector from the Data Output port of the **Get Variable** node and then connect it to the Data Input port of the **Web Slate: Load HTML Content** node.

    ![A screenshot of a computer Description ](../../../media/mesh-201/041-connect-variable-node.png)

## Test your work

1. In Unity, save the project and then press the Unity Editor Play button.

1. Position yourself in front of Station 1.1. As in the previous chapter, WebSlate is displaying some information about Microsoft because the default URL in the **WebSlate** component is set to the Microsoft home page.

    ![A screenshot of a computer Description ](../../../media/mesh-201/042-station-one-one-with-default-homepage.png)

1. Click the **Load 1** button. The WebSlate loads and displays a page that says "Hello World."


## Placing an image on a WebSlate











## Next steps

> [!div class="nextstepaction"]

> [________________________________](TBD)

