---
title: Known issues for Mesh Toolkit
description: Mesh Toolkit active known issues
author: qianw211    
ms.author: qianwen
ms.date: 9/28/2023
ms.topic: Guide
keywords: Microsoft Mesh, Mesh Toolkit, Mesh Developer
---

# Acitive known issues - Mesh Toolkit

## Version 23.12

### WebSlate

* If loading too many WebSlates at once, lower-end computers may not be able to load all WebSlates, only some WebSlates will be loaded. We recommend using the CPA tool to measure rendering time and determine the proper allocations based on your environment's features.
* After upgrading, WebSlate game objects may encounter an internal shader error. You can navigate to the **Inspector** view of your WebSlate and ensure that the selected shader is set to `UnlitWebSlate`.
* After upgrading, your visual scripting graph may still reference the legacy `WebView` type. You can manually update this reference to the correct `WebSlate` type.

### Mesh Toolkit Updating/Upgrading

* In rare instances, after you update the Toolkit package, your Unity project may become unexplainably and temporarily broken. This can result in mysterious compiler errors and missing script references despite the script file being present and clean.

    1. Close and restart Unity.

    1. If this doesn't work, on the Unity menu bar, select **Assets > Reimport All**. Note that this process can take some time.



