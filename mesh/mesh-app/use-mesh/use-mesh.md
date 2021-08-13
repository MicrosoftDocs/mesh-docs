---
title: Use the Mesh app
description: All aspects of using the Microsoft Mesh app are covered
ms.prod: mixed-reality
author: qianw211
ms.author: v-qianwen
ms.date: 08/12/2021
ms.topic: article
keywords: mixed reality, microsoft mesh, documentation, guides, features, holograms, spaces
---

# Use the Mesh app
This article describes how to use features of the Microsoft Mesh app on HoloLens 2.
## The Hand Menu

When you look at the palm of either hand, you will invoke the Hand Menu. In addition to the standard HoloLens start menu on your wrist, the Hand Menu provides quick access to important tools.

![The hand menu](media\hand-menu.png)

1. **Main Menu**: Toggles the Mesh app Taskbar on and off.
1. **Selection Tool**: Activates selection mode. In this mode, you can grab a 3D object or 2D image and move it around the space.
1. **Draw Tool**: Activates the current pen and opens the annotation sub-menu with a variety of brushes and shapes. Once you've selected your tool, pinch and drag to annotate.
1. **Eraser**: Activates the eraser. With the eraser active, move the red X through content or annotation to erase it.
1. **Mute Toggle**: Toggles the microphone on and off.

## The Taskbar

The taskbar lets you access tools and spaces in the Mesh app. You can open the taskbar by tapping the top button on the Hand Menu. The taskbar buttons activate the following features, from left to right.

![The taskbar](media\taskbar.png)

1. [**Spaces**](#collaborative-spaces): Activates the spaces pane.
1. [**Tools**](#add-annotations): Activates the annotation tools pane.
1. [**Content**](./import-content.md): Activates the content pane, where you can select contents to add to the space.
1. [**Settings**](#setting-user-preferences): Activates the settings pane.
1. **Recenter**: Repositions the table to be in front of your current position.
1. **Avatar**: Opens the avatar editor.
1. Leave your current space.

## Position your table

In your home space you will see a blue table. This is the origin point for the space and everything in the scene is oriented around it. Virtual objects and annotations will always move relative to this table. You should place the table in a comfortable position in the real world, preferably somewhere in an open space where you can move around.

![The table](media\table.png)

Pinch the table (up close or at a distance) to grab and move it. When you have the table positioned comfortably, you can use the buttons on the table control panel to lock the table in place to prevent accidental movement, and snap the table to the floor. You can also tap the Recenter button on the taskbar to reposition the table in front of your current position.

The table acts as the central hub for all collaborators, so each space includes a table like the one in your home space. As you move between spaces, the table remains anchored in your physical space and each virtual space is centered around it. However, the table's label and any contents are specific to the current room and don't move between spaces.

## Collaborative Spaces

The Microsoft Mesh app is for collaboration. To work with others, you can create a collaborative space and invite others to join your space, or you can be invited to join spaces that others have created. Users can only enter spaces they are a member of, and each space can have a maximum of 8 concurrent users. All contents and annotations are persistent and can be edited by anyone in the space. All collaboration spaces include the same table found in your home space.

To work with spaces, open the taskbar from the Hand Menu, and choose the Spaces icon.

### Your home space

You always start in your home space when you launch the Mesh app. This space is private, and only you can see and edit this space.

![The Home space pannel.](media\home-space.jpg)

### Create a collaborative space

To create a new space for collaboration:

![The new space button.](media\new-space.png)

1. On the upper right corner of the Spaces pane, tap **New Space**.
1. Enter a name for the space.
1. Tap **Create**.

![Create a collaborative space](media\create-space.png)

Creating a space automatically sends you there. You are now in a collaborative space. Any other users that join that space will be able to see, talk, and collaborate with you.

### Delete or rename a collaborative space

To rename or delete a space:

1. On the Spaces pane, tap the _more_ (...) menu on the tile of the space you want to edit.
1. From the menu, choose the action you want to perform.
    - Rename Space
    - Delete Space
    - Back (no changes will be made)

    ![Delete a collaborative space](media\manage-space.png)

### Invite others to join a space

You can invite others to join any space that you're a member of.

- **For Azure AD users**: All users need to be members of the same organization and have Microsoft Mesh (Preview) enabled for their accounts. Contacts will show all the users in your organization, but other users will have to set up the Microsoft Mesh app (Preview) on their HoloLens to receive calls.
- **For MSA users**: Contacts will show those currently in the email address book associated with your MSA who have also set up the Microsoft Mesh app (Preview) on their HoloLens.

To add others to the current space:

1. On the Spaces pane, select Current in the left menu.
1. Tap **Add Others** button on the upper right corner.
1. Search for the user (using their Azure AD or MSA [identity](/hololens/hololens-identity)).
1. Tap the user to add them to the space.

    ![Add users to a space](media\add-users.png)

- If the users are online, they will get a pop-up inviting them to join the space.
- If they are offline, the space will show up on the user's Spaces menu the next time they log in.

### Colocation

Users in the same physical location can collaborate with each other and also with remote participants.  You can invite co-located or remote friends to join your space.

To ensure success with colocation: 

1. All participants should turn on their hololens and walk around the meeting place before launching mesh. 

1. Choose one person to be the host.  Once joining the space, the host is to place the center piece in the center of the room. 

1. As each participant joins the space, have the host click on this participant in the current spaces tab, and click the green button to invite them to colocate. 

1. The particiant needs to look at the host's center piece (center of the room). 

1. You are colocated when avatars disappear and nametags appearing above people's head. 

1. It's recommended that only the host does all the invites, one at a time (not group select).

To resolve any issues, participants can leave and rejoin the space.

### Move between spaces

You can use the Spaces menu to move between any of the spaces you've created or of which you're a member.

To move between spaces:

1. From the Spaces pane, make sure Spaces is selected in the left menu.
1. Tap **Enter** on the space you want to join.

    ![Move between spaces](media\switch-spaces.png)

## Add annotations

The Tools pane shows you several options for interacting with content.

![Annotation tools](media\tools-brushes.png)

- Select the hand icon to enter selection mode, which let's you grab and move objects in the space.
- Use the eraser to remove content. With the eraser selected, touch the content you want to remove with the red X.
- Use the pen tools to write and draw annotations on content. Choose a pen, choose a color, and tap your finger and thumb together to draw in 3D space.
- Use the stamp tools to add quick 3D shapes. To enable **Sticky Notes** on this tab:
    - Go to **Settings**
    - Select **Sticky Notes** on the **Experimental** tab.

    <br>

    ![Sticky notes in Experimental features](media\experimental-features-sticky.png)

## Setting user preferences

You can set user preferences under **Settings**.

1. Look at your hand to [bring up the menu](use-mesh.md#the-hand-menu), and press the **Main menu** button at the top.

1. Go to **Settings**, select **Preferences**.

    ![Screenshot of the **Settings -> Preferences** tab.](media\settings-preferences.png)

1. Adjust your microphone input level, or [enable subtitles and translation to a language of your choice](languages.md).

### Eye gaze experimental feature

![Info screen on Eye Gaze selection](media\eye-gaze-selection.png)

There is now a very comfortable way of picking up and moving objects.  In your current space, follow the steps below:

1. Look at the object of interest.
1. Raise your hand slightly will highlight this object.
1. Naturally move your hand to move the object.

To enable the eye gaze feature:

1. Look at your hand to [bring up the menu](use-mesh.md#the-hand-menu), and press the **Main menu** button at the top.

1. Go to **Settings**, select **Experimental**.

1. Select **Eye Gaze Interation**.

    ![Screenshot of the **Settings -> Preferences** tab.](media\experimental-features-eye-gaze.png)

## Additional resources

For other questions, see [Microsoft Mesh app troubleshooting and frequently asked questions](../faq.md).

- [Microsoft Mesh overview](../../overview.md)
- [Set up Microsoft Mesh for your organization](../../provisioning.md)
- [HoloLens](/hololens/)
- [Get started with Mixed Reality](/windows/mixed-reality/discover/get-started-with-mr)
- [Loading content to your space](import-content.md)
- [Loading ARR content](arr-content.md)
