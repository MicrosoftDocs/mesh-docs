---
title: Get information about your Environment
description: Get information about the Environment that uploaded to the Azure Portal.
author: typride
ms.author: vinnietieto
ms.date: 8/29/2023
ms.topic: Guide
keywords: Microsoft Mesh, environment, build, publish, build and publish, uploader, Mesh uploader, Azure, Azure portal, portal, upload, asset
---

# Get information about your Environment

After you've uploaded your Environment to the Azure Portal, you may want to view information about it. You can find such information on the **Environments** page for the World you uploaded the Environment to.

![A screenshot of a computer Description automatically generated with medium confidence](../../../media/make-your-environment-available-for-events/image028.jpg)

To see more information about your Environment, select its **Details**
button. The resulting window *won't* tell you which platforms the
Environment is built for. To see that:

1. Select the name of the Environment (circled in red in the image
    above).

2. On the next page, select the **JSON View** button for the
    Environment.

    ![A screenshot of a computer Description automatically generated](../../../media/make-your-environment-available-for-events/image029.jpg)

3. In the JSON view, the information about platforms is contained in
    the *assetInfo* object.

    ![A screenshot of a computer Description automatically generated with medium confidence](../../../media/make-your-environment-available-for-events/image030.jpg)
