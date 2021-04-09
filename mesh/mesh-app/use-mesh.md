---
title: Use the Mesh App
description: All aspects of using the Microsoft Mesh App are covered
ms.prod: mixed-reality
author: qianw211
ms.author: v-qianwen
ms.date: 04/09/2021
ms.topic: article
keywords: mixed reality, microsoft mesh, documentation, guides, features, holograms, spaces
---

# Use the Mesh app

## The Hand Menu

When you look at the palm of either hand, you will invoke the Hand Menu. In addition to the standard HoloLens start menu on your wrist, the Hand Menu provides quick access to important tools.

![The hand menu](\media\hand-menu.png)

1. **Main Menu**: Toggles the Mesh App Taskbar on and off.
1. **Selection Tool**: Activates selection mode. In this mode, you can grab a 3D object and move it around the space.
1. **Draw Tool**: Activates the current pen and opens the annotation sub-menu with a variety of brushes and shapes. Once you've selected your tool, pinch and drag to annotate.
1. **Eraser**: Activates the eraser. With the eraser active, move the red X through a 3D object or annotation to erase it.
1. **Mute Toggle**: Toggles the microphone on and off.

## The Taskbar

The taskbar lets you access tools and spaces in the Mesh App. You can open the taskbar by tapping the top button on the Hand Menu. The taskbar buttons activate the following features, from left to right.

![The taskbar](\media\taskbar.png)

1. **Avatar**: Opens the avatar editor.
1. [**Spaces**](#collaborative-spaces): Activates the spaces pane.
1. [**Tools**](#add-annotations): Activates the annotation tools pane.
1. [**Content**](#import-content): Activates the content pane, where you can select 3D content to add to the space.
1. **Settings**: Activates the settings pane.
1. **Recenter**: Repositions the table to be in front of your current position.

## Position your table

In your home you will see a blue table. This is the origin point for the space and everything in the scene is oriented around it. Virtual objects and annotations will always move relative to this table. You should place the table in a comfortable position in the real world, preferably somewhere in an open space where you can move around.

![The table](\media\table.png)

Pinch the table (up close or at a distance) to grab and move it. When you have the table positioned comfortably, you can use the buttons on the table control panel to lock the table in place to prevent accidental movement, and snap the table to the floor. You can also tap the Recenter button on the taskbar to reposition the table in front of your current position.

The table acts as the central hub for all collaborators, so each space includes a table like the one in your home. As you move between spaces, the table remains anchored in your physical space and each virtual space is centered around it. However, the table's label and any 3D objects are specific to the current room and don't move between spaces.

## Collaborative Spaces

The Microsoft Mesh App is for collaboration. To work with others, you can create collaborative spaces and invite others to join them, or you can be invited to join spaces that others have created. Users can only enter spaces they are a member of, and each space can have a maximum of 8 concurrent users. All 3D objects and annotations are persistent and can be edited by anyone in the space. All collaboration spaces include the same table found in your home.

To work with spaces, open the taskbar from the Hand Menu, and choose the Spaces icon.

![The spaces icon](\media\spaces-pane.png)

### Your home space

You always start in your "home" space when you launch the Mesh App. This space is private, and only you can see and edit this space.

### Create a collaborative space

To create a new space for collaboration:

1. On the Spaces pane, tap **New Space**.
1. Enter a name for the space.
1. Tap **Create**.

![Create a collaborative space](\media\create-space.png)

Creating a space automatically sends you there. You are now in a collaborative space. Any other users that join that space will be able to see, talk, and collaborate with you.

### Delete or rename a collaborative space

To rename or delete a space:

1. On the Spaces pane, tap the _more_ (...) menu on the tile of the space you want to edit.
1. From the menu, choose the action you want to perform.
    - Rename Space
    - Delete Space
    - Back (no changes will be made)

![Delete a collaborative space](\media\manage-space.png)

### Invite others to join a space

You can invite others to join any space that you're a member of.

- **For Azure AD users**: All users need to be members of the same organization and have Microsoft Mesh (Preview) enabled for their accounts. Contacts will show all the users in your organization, but other users will have to set up the Microsoft Mesh App (Preview) on their HoloLens to receive calls.
- **For MSA users**: Contacts will show those currently in the email address book associated with your MSA who have also set up the Microsoft Mesh App (Preview) on their HoloLens.

To add others to the current space:

1. On the Spaces pane, select Current in the left menu.
1. Tap **Add Others**
1. Search for the user (using their Azure AD or MSA [identity](/hololens/hololens-identity)).
1. Tap the user to add them to the space.

![Add users to a space](\media\add-users.png)

- If the user is online, they will get a pop-up inviting them to join the space.
- If they are offline, the space will show up on the user's Spaces menu the next time they log in.

### Move between spaces

You can use the Spaces menu to move between any of the spaces you've created or of which you're a member.

To move between spaces:

1. From the Spaces pane, make sure Spaces is selected in the left menu.
1. Tap **Enter** on the space you want to join.

![Move between spaces](\media\switch-space.png)

## Import content

You can add 3D objects to any space. You can then pinch an object to grab, move, rotate, and scale it. In a collaborative space, all users who are a member of the space can add, manipulate, annotate, and delete any objects.

To work with 3D content, open the Taskbar from the Hand Menu, and choose the Content icon.

![The content icon](\media\content-pane.png)

In the Content pane, there are 3 places from which you can pull content into a space:

- **Samples**: This sample content is included in the app build.
- **OneDrive**: This is content that's inside of the Apps > Microsoft Mesh App (Preview) > MyContent folder on your OneDrive. Other users can't see this content. When you share it in a collaborative space, a copy is made for that space.
- **Space**: This is shared content that either you or another member added to the current space.

> [!NOTE]
> Only .glb files are supported at this time.

### Import user content

You can add your own custom 3D content to OneDrive to make it available in the OneDrive folder in the app.

To add content to the User folder:

1. Go to OneDrive for Business on your PC and log in with the same Azure AD account that you used to log in to the Microsoft Mesh App.
1. In OneDrive, go to Apps > Microsoft Mesh App (Preview) > MyContent and copy files to this directory.
1. Once your files are copied to OneDrive, open the Content > OneDrive pane again to access them.

### Share content to a collaborative space

You can share any content from the Samples or OneDrive folders to a collaborative space. This copies over the model file into your current space and shares the copy with all members of the space. Shared content for a space is stored in each users OneDrive under Apps > Microsoft Mesh App (Preview) > _spaceGUID_.space.

![Share 3D content](\media\share-content.png)

To add 3D content to a space:

1. Open the Content pane.
1. Go to the Samples folder or OneDrive folder. In the OneDrive folder, the Mesh App displays a list of all the files you added to OneDrive.
1. Select a model.
1. The model is added to the current space.

## Add annotations

The Tools pane shows you several options for interacting with content.

![Annotation tools](\media\tools-pane.png)

- Select the hand icon to enter selection mode, which let's you grab and move objects in the space.
- Use the eraser to remove content. With the eraser selected, touch the content you want to remove with the red X.
- Use the pen tools to write and draw annotations on content. Choose a pen, choose a color, and tap your finger and thumb together to draw in 3D space.
- Use the stamp tools to add quick 3D shapes.

## Additional resources

For other questions, see [Microsoft Mesh App troubleshooting and frequently asked questions](faq.md).

- [Microsoft Mesh overview](../overview.md)
- [Set up Microsoft Mesh for your organization](../provisioning.md)
- [HoloLens](/hololens/)
- [Get started with Mixed Reality](/windows/mixed-reality/discover/get-started-with-mr)