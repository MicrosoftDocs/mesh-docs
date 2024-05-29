---
title: Customize your event in Mesh overview
description: Guide to customizing and event in Mesh
ms.service: mesh
author: typride
ms.author: tmilligan
ms.date: 9/07/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, events, hosting, event producer, event organizer, customize
---

# Customize your event

Mesh enables no-code customization of 3D environments that help your organization create experiences tailored to your business goals.

## Why customize an event?

As a host for a Mesh event, you have many tools at your disposal to orchestrate an experience for attendees.

Along with [tools to interact with and manage attendees](../produce-event.md#event-producers-tools), you have a **Control Panel** to manage aspects of the environment.

With the Control panel, you can control individual objects like playing a video when people enter the event, or execute a pre-planned sequence of actions like queuing a video, displaying images, and showing a Screenshare simultaneously.

If you're using a custom environment or there are [**Controllable** objects in your environment that have been added through Unity](../../develop/enhance-your-environment/multi-room-sync.md#controllables), these will also show up in the Control panel as well.

### Types of customizations

* Add objects through the **Editor** like Screenshares, Images, or Videos. Drag and resize the these objects easily by selecting the objects and moving them around the environment.

    :::image type="content" source="../../media/mesh-event-producer-guide/Customize-event-editor-catalog.png" alt-text="Screenshot of Editor catalog in the Microsoft Mesh application.":::

* Use the **Control Panel** to granularly adjust or configure Objects that you have in your environment using the **Controls** tab.

    :::image type="content" source="../../media/mesh-event-producer-guide/Control-panel.png" alt-text="Screenshot of control panel showing the objects in an environment.":::

* Use the **Control Panel** > **Action Groups** tab to control multiple objects at once for an experience such as displaying photos of your team, or showing a company logo and playing a video.

    :::image type="content" source="../../media/mesh-event-producer-guide/Action-groups-gif.gif" alt-text="Gif of an avatar in the Mesh app using action groups to display imaes, a video and company logo, and screenshare.":::

## Considerations before starting your event

* To ensure the event runs smoothly, ensure that you customize and save customizations at least **30 minutes before** the event start time. Once someone joins the event, saving customizations is not available.

* Anyone who has been invited as a **Co-organizer** can customize an event. Do this with caution, knowing that any edits you make will directly alter the Event or Template that event attendees will join.

## How to customize an event

## Customization flow

At a high level, this is the flow you can expect to follow when customizing your event:

1. Once your event is created using [https://mesh.cloud.microsoft/](https://mesh.cloud.microsoft/), open the Mesh app to find and start customizing your event.

1. **Enter a Customization session** for your Event or Template.

1. **Add content** using the **Editor**.

1. **Configure** content with the **Control panel** to be used in your live event. You can edit the Controls of each object individually or group them together in **Action Groups**.

1. **Save changes** in the **Event Customization** window.

## Enter a Customization session for a template or event

# [Template](#tab/template)

### Customize a Template

To learn more about creating a Template, see how to [Create Template](create-template.md).

1. In the Microsoft Mesh app, select the **Manage Templates** button.

    :::image type="content" source="../../media/mesh-event-producer-guide/Select-manage-event-templates.png" alt-text="Screenshot of Mesh app dashboard showing Manage event templates button highlighted.":::

1. Find your **Template** draft.

    :::image type="content" source="../../media/mesh-event-producer-guide/Template-selection.png" alt-text="Screenshot of Mesh app Manage Templates window, draft events highlighted.":::

1. Select the **Customize event experience** button to start customizing the Template.

    :::image type="content" source="../../media/mesh-event-producer-guide/Select-customize-template.png" alt-text="Screenshot of Mesh app showing Customize template button highlighted.":::

# [Event](#tab/event)

### Customize a single Event

1. Open the Mesh app on your computer or use the link in the calendar invite.

1. Look for the event in the **Upcoming** category and select it.

    :::image type="content" source="../../media/mesh-event-producer-guide/Select-event-details-blurred.png" alt-text="Screenshot of Mesh app showing an upcoming event highlighted to indicate that you should select it.":::

1. In the Event details window, select **Customize**.

    :::image type="content" source="../../media/mesh-event-producer-guide/Select-customize-button.png" alt-text="Screenshot of Mesh app showing Customize button for an event highlighted.":::

---


#### Edit object controls

Once you've added an object, you can maneuver it around the spaces and select the it to edit the controls.

1. Select an added object and adjust the controls to suit your preferences.

    :::image type="content" source="../../media/mesh-event-producer-guide/image-environment-editor-open-controls-window.png" alt-text="Controls window showing for object that has been added to an environment":::

1. Configure the controls for the object. For example, you can add the URL for your video:

    :::image type="content" source="../../media/mesh-event-producer-guide/Configure-controls-artifact-larger.gif" alt-text="Add objects and update url":::

    > [!TIP]
    > Use the **Share** or the **Copy Link** functionality in SharePoint to copy the link of the video or image that you want to share and paste it in the Video player or Image object URL field.
    > :::image type="content" source="../../media/mesh-event-producer-guide/SharePoint-link.png" alt-text="Sharepoint link copied in sharepoint":::

### Control objects with the Control Panel

   > [!div class="nextstepaction"]
   > [Control objects with the Control Panel](Using-control-panel.md)
