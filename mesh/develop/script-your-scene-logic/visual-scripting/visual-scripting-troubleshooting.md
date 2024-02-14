---
title: Visual Scripting Troubleshooting
description: Learn about some of the issues you may face with Visual Scripting and how to solve them.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 2/13/2024
ms.topic: Guide
keywords: Microsoft Mesh, scripting, visual scripting, coding, nodes, units, graphs, types, troubleshooting, macros, embedded scripts
---

# Visual Scripting troubleshooting

**Issue**: Prefabs that have a *Script Machine* component with its **Source** property set to *Embed*, as opposed to *Graph* (such "graph assets" are also called *Macros* in *Unity.VisualScripting*) often fail to correctly update in instances of the Prefab after they've been edited in the Prefab definition. This issue is common enough for the *Unity.VisualScripting* authors to supply an in-Editor warning:

![Screen shot of warning that displays when you choose the embed script graph.](../../../media/mesh-scripting/visual-scripting/008-embed-graph-warning.png).

**Solution**: 

If you open a Prefab definition, then edit the embedded visual script, and then look at any instances of that Prefab in your scene and find that they haven't updated properly, do the following:

1. Select the Prefab instance.
1. In the **Inspector**, click the **Overrides** drop-down.
1. Select the "Script Machine" entry (or entries).
1. Click Script Machine's **Revert** button.

![Screen shot of the Prefab overrides menu with script machine selected.](../../../media/mesh-scripting/visual-scripting/009-prefab-script-overrides.png).

This reverts the visual script's definition to what it currently is in the prefab's definition--in other words, the updated version of the visual script.
