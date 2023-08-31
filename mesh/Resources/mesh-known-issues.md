---
title: Known issues for Mesh
description: Active known issues for Mesh
author: qianw211    
ms.author: qianwen
ms.date: 8/31/2023
ms.topic: Guide
keywords: Microsoft Mesh, M365, Unity, API, release notes, reference, documentation, features, performance
---

# Active known issues - Mesh

## Version 2023-8-31

* When downloading the Mesh app from Microsoft Store, some users will get a blank screen in the web browser. To search for the most current data on the server, press the **CTRL + F5** keys to clear your browser cache.  The latest version of the Microsoft store webpage will then load. (14921)
* On Quest, users will see a black lobby screen background after they leave the headset idle in a meeting. (54774)
* Buttons in the **Manage events** dialog can occasionally fail to respond. Scrolling with the scrollbar on the right will fix the problem. (53895)
* Mesh avatars are not visible in the Teams Admin Center. This issue occurs when the tenant is in a different ring than the Teams admin, making policy configuration for the Mesh avatars impossible. Those managing tenants in Ring 4 cannot manage apps that are only deployed as far as Ring 3, and unfortunately that includes Mesh avatars. (40971)

    *Workaround*: Mesh avatars is a *Microsoft app published by Microsoft Corporation*, not a *Third-party app* nor *a Custom app*. Some customers have shared that their policies are set up to allow all Microsoft apps and, in some cases, explicitly for their Ring 1.5 and/or Ring 3 users only. This has allowed them to use Mesh avatars but with some control over who in their tenants can use them.

    We fully appreciate that this is less control than we expect our customers to have, and that some customers may not be able to use similar policies due to respective corporate policies. Still, we’re sharing this as a potential workaround.

    In the meantime, we are working on a better solution to this issue. 

