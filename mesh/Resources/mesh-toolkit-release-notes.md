---
title: Release notes for Mesh Toolkit
description: Mesh Toolkit release notes
author: qianw211    
ms.author: qianwen
ms.date: 10/23/2023
ms.topic: Guide
keywords: Microsoft Mesh, Mesh Toolkit, Mesh Developer
---

# Mesh Toolkit release notes

**Release notes and known issues for Microsoft Mesh Toolkit**

For purposes of this document, there are two categories of users:

* Creators: Technical artist and developers building with the Mesh Toolkit
* IT admins: Managers working in Azure

## Version 23.13

>[!Caution]
>This is a preview release of the Mesh Toolkit noted by a **-preview** tag at the end of the version number.  Environments published with this preview version of the Mesh Toolkit will only work with the preview version of Mesh, and **are not compatible with the stable version of Mesh**. If you don't have access to Mesh preview, do not upgrade to this version of the Mesh Toolkit until a stable version is released.  Stable versions will not have a **-preview** tag at the end of the version number.  
> 
> **Be careful that you don't overwrite environments currently in use by your company with the preview version.**

### Version list and dates

These are the offerings and packages currently available. There may be slight differences in the list you see here and the packages you have or see. We are working to create better transparency and standardization of versions of offerings and packages to make upgrading easier.

>[!Note]
>The version number for Mesh (PC or Quest) **must** match the Mesh Toolkit Authoring package version you're using otherwise you may get errors or unexplained behavior. Please hold off on upgrading the Mesh Toolkit Authoring package until the Mesh client version for your target platform (PC or Quest) is available.

| Mesh offering/package   | Version | Date released
| ----------- | ----------- | ----------- |
| Mesh Toolkit Package      |   5.2313.0     | 2023-10-23  |
| Mesh (PC/Quest)   |  5.2313.0       |  2023-10-23  |

### What's new

#### Scripting

**Restrictions on UnityEvents and animation events in Unity**

UnityEvents and animation events must call into visual scripts. They are not allowed to directly manipulate properties or invoke methods. This restriction applies to the following:

* in a Timeline `SignalReceiver`
* in Animation Events

Here's what to do for UnityEvent in a `SignalReceiver` as the starting point:

1. For Animation Events, it's the same except you can use the **Animation Event** visual script trigger and the corresponding `TriggerAnimationEvent` function on the `ScriptMachine` object, where the *Function* in the Animation Event and the `Float`, `Int`, `String` parameters can be used or filled arbitrarily.

1. Create a `ScriptMachine` for a visual script that uses an UnityEvent trigger and that performs the action you'd like to do.
 
1. Choose a descriptive name for the UnityEvent trigger, for example `DoThing`:

    ![Dialog box for UnityEvent and `TriggerAnimationEvent`](media/unity-event-dialog.png)
 
1. In the `SignalReceiver`, set up the UnityEvent by the following steps:

    1. Target the `ScriptMachine` you've created for the visual script.

    1. For the function to call, select `ScriptMachine > TriggerUnityEvent (string)`.
    1. In the parameter field, enter the name you've chosen (for example, `DoThing`).

    ![Dialog box for `SignalReceiver`](media/signal-receiver-box.png)

#### WebSlate

* We fixed an issue where it would allow scripting ([Visual scripting](/mesh/develop/script-your-scene-logic/visual-scripting/visual-scripting-overview) and [Cloud scripting](/mesh/develop/script-your-scene-logic/cloud-scripting/cloud-scripting-basic-concepts)) to correctly control WebSlate at start-up.

    Before this fix, if the scripting navigate or push HTML content to WebSlates at start-up, it would not show up correctly due to a race-condition.

#### Uploader

* The `ContentVersion` has been incremented to 1.20.0: Newly published content will only be visible in the recent MeshBrowsers.

* Fixed a rendering issue at World List and Environment dropdowns.

* Fixed a bug where create tab UI will draw incorrectly when the text overflowed out of the window boundaries.

* Fixed a bug where the Uploader was throwing regex exceptions after a failed build.

* Added a check for potential null reference exception when publishing assets.