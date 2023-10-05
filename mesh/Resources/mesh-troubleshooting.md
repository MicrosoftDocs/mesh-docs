---
title: Troubleshooting & FAQs - Microsoft Mesh
description: Various help guides and FAQ answers regarding Mesh events.
author: typride    
ms.author: tmilligan
ms.date: 10/4/2023
ms.topic: Troubleshooting
keywords: Microsoft Mesh, M365, events, join events, organize events, immersive spaces, documentation
---

# Troubleshooting & FAQ

## Frequently asked questions

### How to download Mesh on Quest 2 via App Lab

Microsoft Mesh (Preview) for Meta Quest devices is available through AppLab.

If you had previously downloaded the **Napili** app on your Quest 2 device, you should move to the new app available at the link below.

**Napili** will be deprecated in lieu of the new Microsoft **Mesh (Preview) app**.

1. On your PC, visit the link below to download Mesh on Quest 2.

    > [!div class="nextstepaction"]
    > [Microsoft Mesh (Preview) on Oculus Quest 2 \| Oculus](https://www.oculus.com/experiences/quest/8919580184782498/)

    If the URL doesn't work, use a new private window in your browser.

2. Sign in with your **Meta device account** (*not* your corporate AAD account). This could be your Meta ID, Facebook account, or another
    email.

    [Can't find your Meta account associated with your Quest 2 device?](#how-do-i-find-my-meta-id)

    ![Diagram Description automatically generated with medium confidence](media/image011.png)

3. Once authenticated, select the **Get** button.

    ![A black background with white text Description automatically generated with medium confidence](media/image013.png)

4. You'll see the button grey out and change from **Get** to **Purchased** which indicates that the app has been acquired.

    ![Log in with your Meta account confirmation page](media/image015.png)

    >[!Note]
    >You may need to restart your headset to ensure the app loads.

#### How do I find my Meta ID?

Log in to Oculus in a web browser, go to **Profile**, and get your email.

1. Go to the Oculus login page on your web browser: [Log in with Facebook \| Meta](https://auth.oculus.com/login/)

2. Continue with your Facebook account or log in with your Oculus account.

3. It should bring you to your **Profile** page. If not, click your **Profile** icon in the top right corner.

   ![A screenshot of profile icon](media/image017.png)

4. Select **Profile**. From there you should see your Email.

#### How to open Mesh on Quest 2

1. Start up your Quest. Use the Oculus button to open the dashboard menu.

1. Select the **App library** button.

    ![the App library button on your Quest menu](media/image020.png)

1. Find the **Microsoft Mesh (Preview)** app in the App library.

    ![A screenshot of Microsoft Mesh (Preview) in the App library](media/image022.png)

1. Select to **Install** then **Open** the app by selecting it again.

1. Complete the device login flow using the link below on your computer (*this requires a mobile phone for verification*): https://login.microsoftonline.com/common/oauth2/deviceauth

    >[!Note]
    >If the code doesn't work, quit the Microsoft Mesh app and restart it.

    You'll see a window like this when the authentication is complete:

    ![A screenshot of a video game Description automatically generated](media/image024.png)

1. Select to **Allow** any **Terms of service & Allow Diagnostic data**.

1. Accept the **Terms of service & Allow Diagnostic data**.

### What should I do if the Mesh app on Windows crashes during startup, crashes during runtime, or behaves strangely during runtime?

1. Confirm you have a license required to use Mesh as shown [here](../Setup/Content/preparing-your-organization-m365.md#verify-your-licensing).

2. Double check that your network admins have allowlisted the required endpoints as described [here](../setup/content/preparing-your-organization-m365.md#work-with-your-security-organization).

3. Gather the logs from `%USERPROFILE%\AppData\LocalLow\Microsoft Corporation\Microsoft Mesh\`.

4. If the logs are too large to share, the two most important are `Player.log` and `Player-prev.log`.

5. Open a support request by following the link [here](https://aka.ms/meshdevsupport).

### Audio setup in Mesh FAQ

#### Which audio devices work best in Mesh?

Spatial audio works best with **wired headphones**.

Using bluetooth headphones will not provide the most optimal spatial audio experience.

#### Where do I access audio input/output settings?

Audio input/output settings are available in:

**Settings** > **Display and sound**

There you can select your audio devices, choose system default speakers, adjust app volume and test speakers, choose mic device and test your microphone.

#### What are the advanced audio settings?

For advanced audio settings, you can adjust:

- Environment volume
- Effects volume
- Incoming Voices

#### Does spatial audio work with bluetooth headphones? what about wired headphones? 

Wired headphones work best for a full spatial audio experience where you will be able to detect audio distance (attenuation) and directionality.  When using a wireless or Bluetooth headphones, audio attenuation will be present but directionality will not be present.

#### Where do I go to access my audio input/output settings during an event? What are the advanced audio settings options?

1. On the bottom left corner in Mesh (Preview), find the Menu button.

1. Go to **Settings > Display & sound**. There you can select your audio devices.

    ![A screenshot of the Settings dialog](media/settings-display-sound-dialog.png)

For advanced audio settings, you can adjust:

- *Environment volume:* You can adjust the loudness of the ambient sounds up or down.

- *Effects volume:* You can adjust the loudness of the sound effects to help detect movement and activities in the immersive space.

- *Incoming Voices:* You can adjust the loudness of participant activity around you. 

Incoming Voices:* You can adjust the loudness of participant activity around you.

## Mesh error messages

#### You don't have permission to enter this space.

You don't have permission to enter this room as the event host. 

#### You have already joined this space from another location. Please disconnect and retry.

You have already joined this event from another device. Please disconnect from the other device and try again. 

#### This space is full. Please try back later!

Mesh spaces can support up to 16 people. This space is currently at full capacity. 

#### Cannot join the space since one (or more) people are using a different version of the client.

Please make sure all participants are joining the Mesh event with the same version of the Mesh app.

#### Falied to connect to Mesh session. Please try again later.

We cannot connect to Mesh services. This happens sometimes... Please try again.

#### Unable to load the environment. Please try again later.

There was an error loading the space. This happens sometimes... Please try again.

#### Unable to join the Teams meeting. Please try again later.

This error occurs when we cannot connect to Microsoft Teams services.

#### `Response Code` Failed looking up space details.

This error occurs when something goes wrong while trying to get event and space information

#### Failed to lookup Teams meeting details!

This error occurs when we fail to get information about the Teams meeting.

#### The space you were trying to reach isn't available on this device.

This error occurs when the assets in a space isn't compatiable with the current device.

#### This space requires a newer version of the Mesh app. Go to Microsoft Store to update the app.

You need to run the latest verions of the Mesh app to enter this space.

#### An unexpected error occurred when loading the environment for the space.

This is a general error message when we fail to load the asset bundle or we fail to extract the environment from the asset bundle

#### Something went wrong loading the space. Please try again later.

This error occurs When we fail to construct a scene based on the asset bundle.

#### Your app version `client version` must match the version used by others already in the space `hostClientVersion`.

This error occurs When you're trying to join the meeting or event with a different version of Mesh already being used by other participants.

#### Failed to connect. Client version could not be set or compared to other client version already in space.

The Mesh version is unavailable.

#### Failed to navigate to the destination space.  You may need to restart the application.

This is a general message when travel fails.

#### We lost connection with the space. Please retry or close to return to the main dashboard.

This is a general error message when we lose connection to one of our services while traveling to or from a space.

#### You do not have access to this space. You must be invited into a space to join it.

This error message occurs when you receive a 403 error from the Mesh service.

#### Failed to get meeting info from service. 

This error message occurs when you receive a 404 error from the Mesh service.

#### Failed to lookup event code details!

This error happens when finding a meeting failed.

#### Failed looking up space details.

This error happens when we failed to find space information from service.

#### The destination you are trying to reach is not available.

This is the generic error message you see if we don't know what specific error you're hitting. Help us diagnose this problem by using the **Report a Problem** feature in Teams.