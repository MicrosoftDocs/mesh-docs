---
title: Project structure
description: Learn about naming and folder structures when setting up a project for Mesh.
ms.service: mesh
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

![Some examples using the naming convention for Materials, Textures, FBX, and other formats](../../media/3d-design-performance-guide/image009.png)

### Unity folder structure

![Some examples of the Unity folder structure](../../media/3d-design-performance-guide/image010.png)

### Perforce folder structure

![Some examples of the perforce folder structure](../../media/3d-design-performance-guide/image011.png)

## Unity file hierarchy

Keep the **Hierarchy** clean by removing disabled objects.

**Disabled objects still add to the file size of the root object/project.**

![A screenshot of the Unity Hierarchy window](../../media/3d-design-performance-guide/image030.png)

Embedding Prefabs into Prefabs is okay, especially if multiple people are working within a workstream.

![A screenshot of the example Geo_Prefab hierarchy window in Unity](../../media/3d-design-performance-guide/image031.png)