---
title: Avatars in Teams known issues
description: Currently active known issues for Avatars in Teams
ms.service: mesh
author: qianw211    
ms.author: qianwen
ms.date: 9/18/2023
ms.topic: Guide
keywords: Microsoft Mesh, immersive spaces, Mesh, release notes
---

# Active known issues - Avatars in Teams

## February 18, 2023

* When a user with a Teams 2.1 ARM device tries to enable Avatars in Teams, the app may crash. Why? The Onnx runtime that is used for Avatars is not included in Teams 2.1.

* In the eye color customizer, users may not see the correct colors displaying on their avatar and may seem unsaturated. (34981)

## September 18, 2023

* Avatar lip sync is not working in the meeting's pre-join screen. If you have your avatar enabled in the pre-join screen and you are unmuted and speak, the avatars mouth will not move. Avatar lip sync will work as expected once you join the meeting.
