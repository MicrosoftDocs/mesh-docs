---
title: Display and interact with web content overview
description: Learn how to display Web content in Mesh Environments.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 8/15/2024
ms.topic: Guide
keywords: Microsoft Mesh, Web content, Web, webslate, URL, video, streaming video, whiteboard
---

# Display and interact with web content overview

You can provide Mesh event attendees with the ability to view and interact with web content by adding one or more *WebSlates* to your environment. WebSlates can display diverse content sources that can be configured by event organizers in real time. 

With WebSlates, Mesh event attendees can do the following:

- Interact with maps, diagrams, and data

   ![A screenshot of a Mesh experience with a WebSlate on the wall showing a map.](../../../media/webview-developer-guide/image003.png)

- View dashboards, web pages, photos, and videos

- Showcase content that highlights products and services, customer stories, and brand identity

For business needs, WebSlates can feature everyday productivity and information tools that bring business-critical data to events and make immersive experiences more relevant to any business.

## WebSlate features

- **Default URL:** Choose a location for the WebSlate, then add it, and then assign a URL to it. Repeat if you want multiple WebSlates in your scene.

- **Secure navigation:** Lock redirect URLs to prevent malicious redirects and unintended hyperlink navigations.

- **Visual customization:** Modify quality to optimize for users' devices. Attract users from a distance with easy-to-view content.

- **Scriptable:** With [visual scripting and cloud scripting](../../script-your-scene-logic/mesh-scripting-overview.md), you can enable toggling between pages with a button.

- **[Content Performance Analyzer tool](../../debug-and-optimize-performance/cpa.md) integration:** Measure the average time it takes for URP to render WebSlates in a frame and find content loading issues.

- **Testing in Play Mode with Mesh Emulation:** Interact with your content as a user would, directly from the Unity editor.

- **Manually authenticate in-experience:** Access secure content from within the experience by logging into your account and viewing content at runtime.

- **Change the WebSlate URL during an event:** Event organizers can change the URL of a WebSlate in real time during an event.

## Single user and collaborative WebSlate experiences

By design, a WebSlate in a Mesh event is a "single user" experience; WebSlates run individual instances of web content specific to each user, ensuring the security and privacy of any data viewed and any inputs made into the WebSlate. Most webpages (for example, Microsoft.com) are single-user experiences that are useful for asynchronous content consumption (viewing or reading). 

Collaborative web apps are an exception to this design; they're "shared" experiences. For example, Whiteboard web applications often allow multiple users accessing the same URL to collaborate in real time. However, while the interactions may be multi-user, navigation and scrolling are unique to each user's view. 

We encourage you to experiment with different types of web content in your Mesh environment, with some WebSlates providing single-user web content and others providing multi-user web apps.  
 
## Requirements/Dependencies

WebSlates depend on the _Unity.InputSystem_ and _Unity.XR.Interaction.Toolkit_ Unity packages, located in the Mesh toolkit.

## Limitations and Known Issues

### General limitations

- WebSlates are supported in the Mesh application on PC, Mac (TAP participants only) and Meta Quest devices. WebSlates are only available to preview in the Unity Editor on Windows.

- Although a WebSlate can display webpages and support interaction, it doesn't function as a browser and doesn't support bookmark, history or travel back-forth.

- WebSlates in Editor preview are missing a few input capabilities (double-click, dragging).

- When viewing from a distance on Quest, legibility is low.

- Audio isn't spatially localized.

- Web content sync is limited to applications that use web APIs to synchronize content.

### Known issues

See the [WebSlate sections in the Mesh toolkit known issues article](../../../Resources/mesh-toolkit-known-issues.md).

## Feedback for Web content in Mesh

We love feedback and bug reports! If you'd like to provide feedback, use the Feedback button inside any Mesh experience. This ensures that your feedback and bug reporting will be reviewed and incorporated quickly. For WebSlate feedback, include "**[web content]**" or **a mention of WebSlate** in your feedback.

## Next steps

> [!div class="nextstepaction"]
> [Add a WebSlate to your environment](./add-a-webslate.md)
