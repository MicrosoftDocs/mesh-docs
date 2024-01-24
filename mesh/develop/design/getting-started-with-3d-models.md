---
title: Getting started with 3D models
description: Get a comprehensive overview of 3D modeling options for your Mesh experience.
author: vtieto    
ms.author: vinnietieto
ms.date: 1/23/2024
ms.topic: article
keywords: 3D, 3D models, modeling, exporting, importing
---

# Getting started with 3D models

If you want your Mesh experience to be rich in content, you'll probably want to include at least some 3D models. Thankfully, you don't have to be a 3D artist, or have one on your team, to assemble the assets you need to realize your vision. There are many ways to obtain pre-made models free, or at a reasonable cost, which we'll introduce here. We'll also discuss how you can get started on creating your own 3D models.

## Optimize and convert 3D models

For general best practices on preparing your own 3D models for use in a range of Microsoft apps including Mesh, see Microsoft's [real-time 3D model conversion and optimization guide](/dynamics365/mixed-reality/import-tool/best-practices). 

If you're looking for other tools to post-process 3D models, you can optimize any glTF 2.0 model using the [Windows Mixed Reality Asset Converter](https://github.com/microsoft/glTF-Toolkit) available on GitHub. This toolkit includes a command line tool that uses these steps in sequence in order to convert a glTF 2.0 core asset for use in the Windows Mixed Reality home. We also recommend [this Unity plugin](https://github.com/KhronosGroup/UnityGLTF); it's maintained by the creators of glTF.

Once your models are in your project, you'll want to ensure that the project as a whole will meet your performance expectations. We recommend that you regularly use the [Content Performance Analyzer](../debug-and-optimize-performance/cpa.md) (CPA) tool to keep track of your project statistics. 

## Unity Asset Store

The [Unity Asset Store](https://assetstore.unity.com/3d) is a great place to find assets that you can quickly integrate into your project. Their inventory is massive and they claim to have over 11,000 five-star assets so there's a good chance you can find what you need or something close. It's worth taking a look, especially when you consider that many of the assets are free.

## Pre-made Assets

There are numerous Web sites that offer pre-made 3D and CAD (Computer-Aided Design) models and animations at reasonable or no cost. Some of the more popular ones are:

Microsoft Paint3D:

- [Install](https://apps.microsoft.com/detail/9NBLGGH5FV99?launch=true&mode=full&hl=en-us&gl=us&referrer=bingwebsearch&ocid=bingwebsearch).

- [Loading and working with models](https://support.microsoft.com/en-au/topic/using-objects-in-paint-3d-3c50155c-db04-42e4-b600-3d97db8184b2).

[Sketchfab](https://sketchfab.com/tags/hololens)

[CAD Models HoloLens in the Microsoft store](https://www.microsoft.com/en-us/p/cad-models-hololens/9pb4ddf8fxzs?activetab=pivot:overviewtab)

[Turbo Squid](https://www.turbosquid.com/Search/3D-Models/hololens)

[CGTrader](https://www.cgtrader.com/3d-models/hololens)

[Mixamo](https://www.mixamo.com/#/) (models and animations)

[Blender Market](https://www.blendermarket.com/) (Learn more about the Blender modeling tool below)

[3DExport](https://3dexport.com/)

[3D Warehouse](https://3dwarehouse.sketchup.com/)

You might also want to consider "kitbashing", where you download a "kit" of pre-made 3D parts. This allows you to assemble a complex model without the need for advanced modeling skills. Note that in many cases the 3D parts won't have UV maps set up--you'll have to take care of that part. You can find many kits here:

[www.artstation.com](https://www.artstation.com/marketplace/game-dev/resources/3d-models/props/kitbash?page=2)

## Make your own 3D Models

If you can't find pre-made 3D models that fulfill your needs, it may be worth your while to develop some 3D modeling skills or have someone on your team do so. At its highest level, 3D modeling is a vast, complex skill that encompasses numerous subdisciplines. The Unity documentation has good information on various related topics:

- [Rigging and animating](https://docs.unity3d.com/Manual/AnimationOverview.html)
- [Shaders](https://docs.unity3d.com/Manual/Shaders.html)
- [Particles](https://docs.unity3d.com/Manual/class-ParticleSystem.html)
- [Materials](https://docs.unity3d.com/Manual/Materials.html)
- [Optimization](https://learn.unity.com/tutorial/introduction-to-optimization-in-unity#)
- [Textures](https://docs.unity3d.com/Manual/Textures.html)
- [Lighting](https://docs.unity3d.com/Manual/LightingInUnity.html)

As you can imagine, it requires considerable time and effort to become a highly proficient 3D modeler. The good news is that you don't have to become an expert to reap some benefits; just having a few basic skills in your toolbox, such as the ability to change materials on a model or convert a high-poly model to a low-poly one, can result in significant improvements to your experiences.

Here are some of the more popular 3D modeling programs.

[Autodesk Maya](https://www.autodesk.com/products/maya/overview?term=1-YEAR&tab=subscription)

[Blender](https://www.blender.org/)

Blender is a popular choice partly because 3D modeling tools tend to be expensive and Blender is free. In past years, Blender was viewed as less capable than the high-end tools in this category. However, it has undergone substantial improvements in the last few versions and is now considered by many to be a fully professional  tool.

[3ds Max](https://www.autodesk.com/products/3ds-max/overview?term=1-YEAR&tab=subscription)

[Houdini](https://www.sidefx.com/)

[ZBrush](http://pixologic.com/features/about-zbrush.php)

**CAD (Computer-Aided Design)**

CAD programs also let you build 3D models and may offer you advanced domain-specific features that you won't get in one of the programs listed above. For example, if your Mesh experience will contain objects related to infrastructure, buildings, circuits, telecommunications networks, thermodynamics, mechanical parts, medical devices, or manufacturing, then a CAD program may be the best choice for you. You can create models in the CAD program and then convert them into a format that can be used in Unity.

Here are some of the more popular CAD programs. 

[SketchUp](https://www.sketchup.com/): Web-based building app.

Autodesk:

- [AutoCAD](https://www.autodesk.com/products/autocad/overview?term=1-YEAR&tab=subscription)  
- [Inventor](https://www.autodesk.com/products/inventor/overview?term=1-YEAR&tab=subscription)  
- [Fusion](https://www.autodesk.com/ca-en/products/fusion-360/overview?term=1-YEAR&tab=subscription)
- [Revit](https://www.autodesk.com/ca-en/products/revit/overview?term=1-YEAR&tab=subscription)

[Siemens NX](https://www.plm.automation.siemens.com/global/en/products/nx/)

[Catia](https://www.3ds.com/products-services/catia/?wockw=card_content_cta_1_url%3A%22https%3A%2F%2Fblogs.3ds.com%2Fcatia%2F%22)

[SolidWorks](https://my.solidworks.com/try-solidworks?mktid=13825&utm_campaign=202007_nam_sw_BINGSWOPT_en_XOP2062_rise_brand_nam_us_exact&utm_medium=cpc&utm_source=bing&utm_content=search&utm_term=1970a52062131481b383c4a1cb107268&gclid=1970a52062131481b383c4a1cb107268&gclsrc=3p.ds&msclkid=1970a52062131481b383c4a1cb107268)

[Tinkercad](https://www.tinkercad.com/): Web-based building app.

## Scanning a space

[Polycam](https://poly.cam/): Android and Apple iOS app. You can use it for free to export to Blender or to take measurements. There's also a pay version.

More scanning apps:

[Scaniverse](https://scaniverse.com/)

[Metascan](https://metascan.ai/)

## Learning Resources

The best place to start looking for tutorials, videos, and other learning resources is on the Web site of your chosen tool. Large streaming video sites like YouTube have many tutorials about 3D modeling, but since anyone can post a video, the quality can vary widely. Some tools have dedicated YouTube channels--two examples are [Blender](https://www.youtube.com/user/BlenderFoundation) and [Maya](https://www.youtube.com/c/MayaHowTos).

Another free, worthwhile resource may be your local public library. Many libraries offer streaming eLearning videos on their Web sites, and there tend to be many computer articles from high-quality sources. For example, the San Francisco public library offers [videos from LinkedIn Learning](https://www.linkedin.com/learning-login/go/sfpl).

If you're willing to pay, here are some of the more popular video tutorial sites:

[Udemy](https://www.udemy.com).

[Udacity](https://www.udacity.com/)

[Coursera](https://www.coursera.org/)

[edX](https://www.edx.org/)

## Next steps

[3D modeling tips](./3d-modeling-tips.md)

### Resources

* [Download glTF Viewer](https://www.microsoft.com/p/gltf-viewer/9mwmgknx8fkh)
* [Download mixpace](https://www.microsoft.com/p/mixpace/9ph50tf4jvlv)
* [Download droppar.io](https://www.microsoft.com/p/droppario/9nf4hq5gr82d)
* [Download SketchUp Viewer](https://www.microsoft.com/p/sketchup-viewer/9ngf868jkvm3)
* [Download 3skeng AR](https://www.microsoft.com/p/3skeng-ar/9mvmq3dz3p71)