---
title: Design for Mesh overview
description: An overview for technical artists and developers for how to design for Mesh.
author: typride
ms.author: vinnietieto
ms.date: 9/26/2023
ms.topic: Guide
keywords: Microsoft Mesh, unity, design, models, modeling
---

# Project Structure

### Naming conventions

*ProjectName_category_assetName_subcategory_iteration_type.format*

*Here are some naming convention examples:*

![Graphical user interface, text Description automatically
generated](../../media/3d-design-performance-guide/image009.png)

### Unity folder structure

![Graphical user interface, text, application Description automatically
generated](../../media/3d-design-performance-guide/image010.png)

### Perforce folder structure

![Graphical user interface, text, timeline Description automatically
generated](../../media/3d-design-performance-guide/image011.png)

## Unity file hierarchy

Keep the **Hierarchy** clean by removing disabled objects.

**Disabled objects still add to the file size of the root
object/project.**

![](../../media/3d-design-performance-guide/image030.png)


Embedding Prefabs into Prefabs is okay, especially if multiple people
are working within a workstream.

![](../../media/3d-design-performance-guide/image031.png)