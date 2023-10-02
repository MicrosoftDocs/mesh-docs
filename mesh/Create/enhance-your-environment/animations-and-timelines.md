---
title: Animations and timelines
description: Learn how to add timelines that trigger events such as animations to your Environment.
author: typride
ms.author: vinnietieto
ms.date: 8/31/2023
ms.topic: Guide
keywords: Microsoft Mesh, Unity, environments, scenes, events, animation, timelines, templates
---

# Animations and Timelines

An Event Producer can control animations that you set up in your Environment using Timelines.

## Animate Timelines in Unity for Mesh

If you're unfamiliar with how **Timelines** work in Unity, we recommend that you watch this
Unity Tutorial series on using [**Timelines**](https://learn.unity.com/project/up-to-speed-with-timeline)

#### To create a Timeline for Mesh

1. In the **Hierarchy**, add an empty GameObject and then rename it
    "Timelines."

2. Add another empty GameObject, make it a child to **Timelines**, and
    then rename it "Timeline1."

![___](../../media/enhance-your-environment/image033.png)

**Notes**:

- We suggest that you give this GameObject a more descriptive
    name---for example, *1_Entrance_Doors*. For this scenario, we'll
    stick with the name "Timeline1."

- If you have a door-opening animation, selecting the Play button will
    open the door in your scene. Selecting the Stop button will reset
    the animation back to its original position. A Playable will *not*
    animate in reverse; to do this, you'll need to create a different
    animation.

**IMPORTANT**: Multiple timelines on a single GameObject will *not*
work and will cause issues in events.

3. In the **Project** tab, navigate to the **Assets** folder and then
    create a new folder named *Animations*.

4. In the **Hierarchy**, select **Timeline1**, and then select **Window
    Sequencing >Timeline**.

5. We recommend that you move the **Timeline** tab next to the
    **Project** and **Console** tabs. This allows you to view the
    **Timeline** and the **Scene** or **Game** windows simultaneously.

![A screen shot of a video Description automatically generated with low
confidence](../../media/enhance-your-environment/image034.jpg)

6. Select **Create**.

![Graphical user interface, website Description automatically
generated](../../media/enhance-your-environment/image035.png)

7. In the **Save** window, change the name of the Playable to
    *Open_Doors* and then save it to the **Assets Animations**
    folder**.
    **

![A screenshot of a computer Description automatically generated with
medium confidence](../../media/enhance-your-environment/image036.png)

8. You can now animate or customize your Timeline---for example, add
    animation clips, activation clips, and more. For more on how to do
    this, watch this tutorial series:

A Timeline with several tracks might look something like this:

![](../../media/enhance-your-environment/image037.jpg)

9. Once you're done animating, in the **Hierarchy**, select the
    **Timeline1** GameObject, and then in the **Inspector**, navigate to
    the **Playable Director** component.

10. In most cases you'll want to choose these settings:

**Play On Awake** = not selected

The timeline will be active when you upload it.

**Wrap Mode = Hold**

The last frame of your animation will be on hold indefinitely;
otherwise, your timeline will reset to the start. There's also a
**Wrap Mode** option named **Loop** which you may want to use in some
instances.

![Graphical user interface, application Description automatically generated](../../media/enhance-your-environment/image038.jpg)

Now you can upload your content to Mesh using the **Mesh Toolkit
Uploader** and then see how it looks in your Mesh space. To learn more,
see the document named *Mesh Event Producer Guide.pdf*, section: "All
Content with the Control Panel."

## Controlling an Animation in an Event

As a Producer in an Event, you can select *play* to start your
animation, *pause* it, and select *play* again to resume the animation.
You can also select *stop* to reset the animation to the beginning or
set your animation to *loop*.

![___](../../media/enhance-your-environment/image039.png)

For example, if you have a door-opening animation, selecting the *play*
button will open the door in your scene. Selecting *stop* will reset the
animation back to its original position. A Playable will not animate in
reverse; to do this, you'll need to create a different animation.

For more information, see our document titled *Mesh Event Producer
Guide*.

## Save your work as a template

If you create an Environment + Event features combination that you think
Event Producers may want to repeat in the future, you can save the
combination as a template. To learn more about templates, see our
document named *Mesh Event Producer Guide*, section: *Event Templates*.

## Next steps

   > [!div class="nextstepaction"]
   > [Web content](webcontent.md)
