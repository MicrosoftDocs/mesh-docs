---
title: Mesh 201 Pt. 5':' Get live weather data
description: Learn how to set up an interactive globe you can click to get live weather data.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 6/14/2024
ms.topic: tutorial
keywords: Microsoft Mesh, getting started, Mesh 201, tutorial, GitHub, WebSlates, web, cloud scripting
---

# Mesh 201 Tutorial Chapter 5: Get live weather data

In this chapter, we move forward to Station 4 where you'll learn how to use Mesh Cloud Scripting to get data from internal or public sources and then visualize it in a 3D context in your scene. As we discussed in Chapter 1, the premise here is that attendees in your experience can use this station to learn about weather conditions in three locations where they're considering building a wind farm. The attendees will be able to click an interactive globe and view live weather data from the three locations.

Stations 4 and 5 are located on the other end of the Sphere Terrace from the previous stations.

![__________________________________](../../../media/mesh-201/073-stations-4-and-5.png)

## Setting up for this station

In order to complete this station, you'll need to insert a *key* into some code that'll enable you to access the weather data API. Let's get this key now so that you don't have to interrupt your workflow later on.

1. Navigate to the [weatherapi.com sign-up page](https://www.weatherapi.com/signup.aspx).
1. On that page, follow the instructions to sign up for the trial plan.

    ![__________________________________](../../../media/mesh-201/080-weatherapi-com-signup.png)

    You'll need to open the email they send you, activate your account, and then log in on their site.

1. On the **Welcome Back** page, click "Pro Plus Plan".

    ![__________________________________](../../../media/mesh-201/081-weatherapi-welcome-back-page.png)

1. For this tutorial, it's not necessary to have a paid plan. Click the **Downgrade** button under "Free", and then in the dialog that pops up, click **Close**.

    ![__________________________________](../../../media/mesh-201/082-weatherapi-pick-plan.png)

1. In the left-side menu under **Dashboard**, select **API**.

    ![__________________________________](../../../media/mesh-201/083-API.png)

1. Select the **Copy** button next to the **API Key** field, then paste the key into a text editor, and then save the text file.

    ![__________________________________](../../../media/mesh-201/084-copy-key.png)

    If the copy operation is successful, the text on the *Copy* button changes to **Copied**.

## Add the Mesh Cloud Scripting prefab

1. Open the *StartingPoint* scene.
1. In the **Hierarchy**, right-click in an empty space and then, in the context menu, select **Mesh Toolkit** > **Set up Cloud Scripting**.

    ![__________________________________](../../../media/mesh-201/075-set-up-cloud-scripting.png)

    This adds a GameObject named **Mesh Cloud Scripting** which has a component with the same name attached.

    ![__________________________________](../../../media/mesh-201/076-cs-component.png)

    Any GameObject that you intend to have under the control of cloud scripting must be added as a child to the **Mesh Cloud Scripting** GameObject.

## Add the prefab for Station 4

1. In the **Project** folder, navigate to **Assets** > **MeshCloudScripting** and then drag **4 - GlobeWithCloudScripting** to the **Hierarchy** and place it as a child object to **Mesh Cloud Scripting**.

    ![__________________________________](../../../media/mesh-201/077-drag-prefabs.png)

    This prefab provides the text information box and a nested prefab named **Earth** that contains the model for the globe.

    ![__________________________________](../../../media/mesh-201/103-earth-model.png)

1. Adjust your view so that you're directly in front of and looking at Station 4.

    ![__________________________________](../../../media/mesh-201/123-station-4-front-view.png)

## Insert the API key for weatherapi.com

1. In the **Hierarchy**, select the **Mesh Cloud Scripting** GameObject.
1. In the **Inspector**, navigate to the **Mesh Cloud Scripting** component and then click **Open application folder**.

    ![__________________________________](../../../media/mesh-201/078-open-app-folder.png)

    This opens the folder that contains the files for Mesh Cloud Scripting in the Windows File Explorer.

1. Open the file named *appsettings.UnityLocalDev.json* in your code editor. The last four lines of code in the file contain configuration settings.

    ![__________________________________](../../../media/mesh-201/085-config-code.png)

    You don't need to do anything for this first line ...

    `"WEATHER_API_URI": "http://api.weatherapi.com/v1/current.json?key="`

    ... but in the next line, replace the "Paste Weather API key here" text with the API key you copied earlier.

    ![__________________________________](../../../media/mesh-201/086-api-key-pasted.png)

    You can ignore the last two lines--we'll be working with those in the next chapter.

1. Save and close the JSON file.

## Update the csproj file

1. In the File Explorer window that displays the Mesh Cloud Scripting files, open the file named *StartingPoint.csproj* in your code editor.

    ![__________________________________](../../../media/mesh-201/087-csproj-file.png)

1. Copy the following text: 

    `<ItemGroup>  
   	<Folder Include="WeatherAPI\" />  
   </ItemGroup>`

    ... and then paste it into the file just above `</Project>` at the end of the file.

    ![__________________________________](../../../media/mesh-201/104-itemgroup-weatherapi.png)

   This ensures that we include some scripts from the local *WeatherAPI* folder.

    ![__________________________________](../../../media/mesh-201//105-weatherapi-folder.png)

1. Save and close the file.

## Add code that makes the globe interactive

1. In the File Explorer window that displays the Mesh Cloud Scripting files, open the file named *App.cs* in your code editor.

    ![__________________________________](../../../media/mesh-201/089-app-dot-cs-highlighted.png)

    The first thing we'll do is ensure that when an attendee clicks on the globe, the displays of the weather data are refreshed.

1. In the App.cs file, find the first "Paste code here" comment located inside the `StartAsync()` method.

    ![__________________________________](../../../media/mesh-201/135-paste-code-for-weather-station.png)

1. Copy the code below.

    ```
        var refreshButton = _app.Scene.FindFirstChild("Earth", true) as TransformNode;
        var refreshButtonNode = refreshButton?.FindFirstChild<InteractableNode>(true);

        if (refreshButtonNode != null)
        {
            refreshButtonNode.Selected += async (_, _) =>
            {
                await GetCurrentWeather(_latlong);
            };
        }
    ```

1. Replace the "Paste code here" comment you just found with the code you copied.

    ![__________________________________](../../../media/mesh-201/091-pasted-code.png)

    The code does the following:
    
    - Initializes the *refreshButton* variable with the *Earth* GameObject in the scene.
    - Initializes the *refreshButtonNode* variable with the *InteractableNode* attached to the *Earth* GameObject. (If a GameObject in the scene hAs a *Mesh Interactable Setup* component attached, which *Earth* does, the component adds a Mesh Cloud Scripting [InteractableNode](../../script-your-scene-logic/cloud-scripting/cloud-scripting-programmers-guide.md#interactablenode)).
    - When an attendee clicks on the globe, it fires the InteractableNode's *Selected* event and calls the *GetCurrentWeather* method. This generates an [HTTP request](https://learn.microsoft.com/dotnet/fundamentals/networking/http/httpclient) to get the weather data.

1. Save the file.

## Test your work

1. In the Unity Editor, save the project and then press the Play button.

1. Your avatar is spawned on the side of the Sphere Terrace that contains the first three stations. Navigate to the opposite side of the Sphere Terrace and then position yourself in front of Station 4.

    ![__________________________________](../../../media/mesh-201/092-station-4-in-play-mode.png)


1. To see the weather data, click anywhere on the globe. The temperature, average wind speed, and peak wind speed are shown for three cities: 1) Lagos, Nigeria, 2) Dublin, Ireland, and 3) Redmond, WA.

    ![__________________________________](../../../media/mesh-201/093-weather-data-displayed.png)

1. When you're finished, press the Play button again to exit Play mode.

## Next Steps

> [!div class="nextstepaction"]
> [Chapter 6: Get answers to questions using Azure OpenAI](./mesh-201-06-open-ai.md)
