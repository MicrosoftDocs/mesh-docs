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

**I want to enable some URP post-processes for the PC. I created my own URP configuration files and set the project to use them, but then I get an error when I try to run or build the scene. Modifying quality levels or setting URP assets to my own resets them to default settings when I build. Most of the options in existing URP asset files are grayed out. Is this expected behavior?**

 Yes, it's expected. We don't support the addition of post-processing to any uploaded environment. We enforce URP assets and configurations to ensure that your content looks as expected when it appears in Mesh.

 
