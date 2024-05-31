---
title: Mesh 201 Load a local non-shared HTML file into a WebSlate
description: Learn about loading a local non-shared HTML file into a WebSlate.
author: vtieto
ms.author: vinnietieto
ms.date: 5/21/2024
ms.topic: Tutorial
ms.service: mesh
keywords: Microsoft Mesh, getting started, Mesh 101, tutorial, scripting, visual scripting, code, coding, interactivity, webslates, HTML
---

# Mesh 201 Tutorial Chapter 2: Load a local non-shared HTML file into a WebSlate

Now that you're all set up and have had a chance to try out the project, let's move on to scripting web content in WebSlates! A WebSlate is basically a big interactive screen. You can use it to view dashboards, web pages, photos and videos or interact with maps, diagrams, and data. At Station 1, we'll load a local non-shared HTML file into a WebSlate.

## Add the WebSlate to the scene

1. Open the **StartingPoint** scene.
1. In the **Scene** window, ensure that you're positioned so you're in front of and looking at Station 1, pictured below.

    ![A screenshot of a computer Description ](../../../media/mesh-201/014-station-one-front-view.png)

    The Station already has an object in place that has some descriptive text and a **Load** button. We'll complete the station by adding a WebSlate below the button and then updating a script graph attached to the **Load** button so that when the user clicks the button, a non-shared HTML file loads into the WebSlate.

    All the WebSlates that we'll be adding and/or working with are contained within the hierarchy of the **MeshWebSlates** GameObject. 

    ![A screenshot of a computer Description ](../../../media/mesh-201/011-mesh-webslates.png)

1. In the **Hierarchy**, collapse the **staticSceneObjects** object, if needed.
1. Expand **MeshWebSlates** and then expand its child object named **1 - LocalWebslate**.

    ![A screenshot of a computer Description ](../../../media/mesh-201/012-webslates-expanded.png)

1. In the **Project** window, search for the **WebSlateFramed** prefab. Make sure you choose **All** or **In Packages** for the Search filter.

    ![A screenshot of a computer Description ](../../../media/mesh-201/013-search.png)

1. Drag **WebSlateFramed** from the **Project** window and then, in the **Hierarchy**, drop it in the space between **2 - LocalWebslate** and **ChapterLabel** so that it's the first child object of **2 - LocalWebSlate**.  
 
    ![A screenshot of a computer Description ](../../../media/mesh-201/015-webslateframed-in-hierarchy.png)

    **Note**: You have two options when choosing a WebSlate prefab: **WebSlate**, which is a simple design with no extra components, and **WebSlateFramed**, which has a stylized frame and extra features.

    Our WebSlate is now in the scene, but it doesn't have the size or position we want.

    ![A screenshot of a computer Description ](../../../media/mesh-201/016-slate-wrong-size-and-location.png)

    Let's change that.

1. In the **Hierarchy**, ensure that **WebSlateFramed** is selected, and then, in the **Inspector**, update the **Scale** values in the **Transform** component to the following:

    **Scale**: X = 2.5, Y = 1.5, Z = 1

    This is much better!

    ![A screenshot of a computer Description ](../../../media/mesh-201/017-slate-after-adjustments.png)

## Change the URL of the WebSlate

1. In the **Hierarchy**, expand the **WebSlateFramed** prefab.
1. Select the child object of **WebSlateFramed** named **WebSlate**.
1. In the **Inspector**, navigate to the **WebSlate** component and note that the **Current URL** property is set to the home page for all of Microsoft.

    ![A screenshot of a computer Description ](../../../media/mesh-201/029-default-url.png)

    Let's change the URL so it points to the home page for Microsoft Mesh.

1. Add "mesh" to the end of the URL in the **Current URL** text box.

    ![A screenshot of a computer Description ](../../../media/mesh-201/072-mesh-url.png)

## Open the button script

1. In the **Hierarchy**, expand **ChapterLabel**, then expand **Actions**, and then select **LoadButton**.

    ![A screenshot of a computer Description ](../../../media/mesh-201/018-loadbutton-selected.png)

    In the **Inspector**, you can see that that **LoadButton** has a **Script Machine** component containing an embedded script named **Load HTML**, and a variable that we'll be using in the script.

    ![A screenshot of a computer Description ](../../../media/mesh-201/019-button-components.png)

    > [!TIP]
    > The **Source** property for the script has two options: *Graph* and *Embed*. Each have advantages and disadvantages; you can learn more about them in the [Unity Script Machine article](https://docs.unity3d.com/Packages/com.unity.visualscripting@1.8/manual/vs-graph-machine-types.html). We use the *Embed* option here because, among other things, you can directly reference your scene nodes without making intermediate Object variables.

1. In the **Script Machine** component, click the **Edit Graph** button.
1. Park the **Script Graph** window next to the **Project** and **Console** tabs. Click its tab to see its contents.

    ![A screenshot of a computer Description ](../../../media/mesh-201/020-script-graph.png)

**Tip**: If you want more space in the **Script Graph** window, you can click its three-dot button and then select **Maximize**, or click the **Full Screen** button in the upper right corner of the window.

**Important**: Note that the second node in the script is named **Mesh Interactable Body: Is Selected Locally**. There are two available "Mesh Interactable Body" nodes; these nodes let you use [*Mesh interactables*](../../enhance-your-environment/avatar-and-object-interactions/interactables.md) with Visual Scripting, such as with interaction events or to modify the manipulable target transform through the visual script. If you want only the person triggering an event to experience it, use the node that says "Is Selected *Locally*". If you want *all* attendees in the event to experience it, select the node that simply says "Is Selected." See the differences in the image below. The text above each node can help you to confirm the behavior.

![A screenshot of a computer Description ](../../../media/mesh-201/027-is-selected-local-or-global.png).

In our current script, we use the node with "Is Selected Locally". This means that when the attendee clicks the Load button, only they will see the new HTML page that loads into the attached WebSlate.

## Get the HTML page

The script graph has already been started for you. We'll complete the tasks needed to enable the **Load** button at Station 1 to load the HTML page.

The first thing we need to do is get access to the **WebSlate** component that's attached to the **WebSlate** object.

![A screenshot of a computer Description ](../../../media/mesh-201/021-webslate-component.png)

We have a node in the script graph set up for this--**Get Component in Children**--so ...

1. Drag the **WebSlateFramed** object from the **Hierarchy** and then drop it in the first field in the **Get Component in Children** node.

    ![A screenshot of a computer Description ](../../../media/mesh-201/022-drag-slate-object.png)

1. Click the Control Output port of the **Get Component in Children** node, and then drag to the right. This opens the Fuzzy Finder. **WARNING**: Once you open the Fuzzy Finder, don't click anywhere outside of the Unity interface. This closes the Fuzzy Finder and causes unpredictable behavior in the Script Graph.
1. In the Fuzzy Finder, search for "Web Slate: Load HTML Content (Html Asset)" and then select it. **Note** that there are two nodes with very similar names. 

    ![A screenshot of a computer Description ](../../../media/mesh-201/023-load-html-content.png)

    You want the one that says **Html Asset**, not **Html Content**.

    ![A screenshot of a computer Description ](../../../media/mesh-201/024-node-content-or-asset.png)

1. Drag a connector from the Data Output port of the **Get Component in Children** node and then connect it to the Data Input port of the **Load HTML Content** node.

    ![A screenshot of a computer Description ](../../../media/mesh-201/026-connector-to-html-content.png)

1. We already have the web page we want to load in a **Get Variable** node in the script graph. Drag a connector from the Data Output port of the **Get Variable** node and then connect it to the Data Input port of the **Load HTML Content** node.

    ![A screenshot of a computer Description ](../../../media/mesh-201/025-connect-variable-node.png)

## Test your work

1. In Unity, save the project.

    **WARNING**: There's a currently a bug in the project where saving it may cause the text in the information text boxes to disappear.

    ![A screenshot of a computer Description ](../../../media/mesh-201/120-no-text-bug.png)

    The text reappears when you enter Play mode. Keep this in mind as you work through the other stations.

1. Press the Unity Editor Play button.
1. Position yourself in front of Station 1, and notice that the WebSlate is displaying the Microsoft Mesh home page.

    ![A screenshot of a computer Description ](../../../media/mesh-201/028-webslate-with-default-page.png)

1. Click the **Load** button. The WebSlate loads and displays a page from the variable you connected in the Scrip Graph that says "Hello World."

    ![A screenshot of a computer Description ](../../../media/mesh-201/030-webslate-with-loaded-page.png)

    This page comes from the **HTMLAsset** variable in the button's script graph.

    ![A screenshot of a computer Description ](../../../media/mesh-201/031-hello-world-page.png)

    **TIP**: To get some extra insights into how the script works, watch it in the **Script Graph** as you click the **Load** button. The connectors between the nodes display informational tips and animations.

    ![A screenshot of a computer Description ](../../../media/mesh-201/119-runtime-connector-tips.png)

1. When you're finished, click the Unity Editor Play button to exit Play mode.

## Next steps

> [!div class="nextstepaction"]
> [Chapter 3: Load a local shared HTML file into a WebSlate.](./mesh-201-03-webslate-2.md)


