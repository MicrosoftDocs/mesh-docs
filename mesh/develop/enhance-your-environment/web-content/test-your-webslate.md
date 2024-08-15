---
title: Test your WebSlate
description: Learn how to test a WebSlate in your Mesh environment.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 8/14/2024
ms.topic: Guide
keywords: Microsoft Mesh, Web content, Web, webslate, URL, video, streaming video, whiteboard, test, troubleshooting
---

# Test your WebSlate

## Ensure that your WebSlate is readable

It's important to ensure that all the attendees in a Mesh experience can read all the content on a WebSlate comfortably. We recommend that you create some empty floor space in front of a WebSlate so that attendees can move closer to it and adjust their position for a better view. If your experience contains seats, view the WebSlate from each seat to ensure that an attendee sitting in that seat can read the text on the WebSlate. If you have control over the content that will appear on a WebSlate, experiment with various font sizes for the text to determine the optimal size for viewing. In the example experience below, the "Microsoft Teams" text in the middle of the WebSlate is more than large enough for comfortable viewing, but the much smaller text in the corners is difficult to read. In this type of scenario, you wouldn't have control over the text in the streaming video so you should consider moving the seats closer. Also, seats that are more centered and looking straight at the WebSlate will provide a better view than seats that are off to the sides.

![A view inside a Mesh experience that contains a WebSlate with large and small text.](../../../media/enhance-your-environment/web_content/004-webslate-large-and-small-text.png)

## Preview your WebSlate in Play Mode with Mesh Emulation

To view a URL displayed in your WebSlate more quickly, you can use Play Mode with Mesh Emulation. Aside from testing in this mode, the only other way to see your WebSlate is to upload it using the Mesh toolkit Uploader and view it in a Mesh experience.

To add Play Mode with Mesh Emulation to your project, follow the instructions in the [Mesh Emulator article](../debug-and-optimize-performance/mesh-emulator.md).

**To view your Web page in the WebSlate**:  
Press the Unity editor Play button.

![Showcase both webslate prefabs in the Mesh Emulator.](../../../media/webview-developer-guide/image011.png)

### Enable WebSlate interaction for Play Mode with Mesh Emulation

To enable interaction in the WebSlate, you have to set up a few things.

1. Add the [Mesh Emulator](../../debug-and-optimize-performance/mesh-emulator.md) to your scene to enable Play Mode with Mesh Emulation.

1. Create a new **Plane** GameObject. This will be your floor. Ensure the GameObject is positioned at the origin (0,0,0):

   ![A screenshot of the Plane menu item.](../../../media/webview-developer-guide/image015.png)

1. Position the WebSlate so it sits in front of the _MeshEmulatorSetup_ character:

   ![A screenshot of the Mesh Emulator Setup character placed in front of and facing two WebSlates.](../../../media/webview-developer-guide/image016.png)

1. Click the Play button, and then double-click to interact with the Web page displayed in the WebSlate:

   ![A screenshot of two WebSlates displayed while in Play Mode with Mesh Emulation.](../../../media/webview-developer-guide/image017.png)

Great job! You added a custom WebSlate to your Unity scene and tested the interaction in Play Mode with Mesh Emulation.

Now you're ready to upload the Environment to Mesh and share your creation with the world!

## Next steps

> [!div class="nextstepaction"]
> [WebSlates and Mesh Scripting](./webslates-and-mesh-scripting.md)
