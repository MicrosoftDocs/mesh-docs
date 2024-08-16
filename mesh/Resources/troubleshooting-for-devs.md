---
title: Troubleshooting for Mesh Developers
description: Answers to issues facing Microsoft Mesh developers.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 8/16/2024
ms.topic: troubleshooting
keywords: Microsoft Mesh, M365, events, join events, organize events, immersive spaces, documentation, troubleshooting, issues, problems, FAQ
---

# Troubleshooting for Mesh Developers

**I want to enable URP post-processes for PC. I created custom URP configuration files and set the project to use them, but I get an error when running or building the scene. Modifying quality levels or setting URP assets to my own resets them to default settings during the build. Most options in existing URP asset files are grayed out. Is this expected behavior?**

 Yes, it's expected. We don't support the addition of post-processing to any uploaded environment. We enforce URP assets and configurations to ensure that your content looks as expected when it appears in Mesh.

 
