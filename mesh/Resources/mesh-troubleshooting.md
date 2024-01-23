---
title: Troubleshooting & FAQs - Microsoft Mesh
description: Various help guides and FAQ answers regarding Mesh events.
ms.service: mesh
author: qianw211
ms.author: qianwen
ms.date: 10/12/2023
ms.topic: Troubleshooting
keywords: Microsoft Mesh, M365, events, join events, organize events, immersive spaces, license requirements, licensing, permissions, Oculus, Quest, download, ID, Meta ID, collection, environments, templates, sharding, provisioning, audio, spatial audio, error messages
---

# Troubleshooting & FAQ

## Frequently asked questions

## What are the license requirements for immersive spaces in Mesh?

[!INCLUDE [The include file for the license requirements in Mesh](../Includes/license-requirements-for-Mesh.md)]

### What if I limit user permissions with corporate policies?

If you do not *allow* users with Teams and Office licenses to create Groups, Sharepoint/OneDrive sites, or use Mailbox/Calendar, the user may notice the following:

1. You cannot create a Collection (formerly called a "Mesh World") since you do not have the ability to do M365 Group creation in your organization.

1. You cannot create an event since you do not have access to M365 Calendar in your organization.

1. One or more people cannot be invited to the event because they do not have access to Outlook.

1. User cannot be added to collection membership since they do not have the ability to access M365 Groups in your organization.

1. You cannot create a template since you do not have access to SharePoint in your organization.

### Will there be support added in future to use an existing M365 Group?

We currently have no plans to support this feature. Right now, when Mesh creates an M365 Group, some additional data is added to the group to identify it as being a Mesh Collection.

### When an M365 Group is created through Mesh, can it still be enabled for Teams after? Just like any other M365 Group?

All M365 Groups created are normal M365 groups. A unique identifier is added to the group for the Mesh Portal to identify which Groups are associated with specific Mesh Collection groups.

### Can we script or automate the creation of an M365 Group for use with Mesh?

We currently don't support this feature.  

## What are the license requirements for Immersive spaces in Teams?

[!INCLUDE [The include file for license reqs for immersive spaces in Teams](../Includes/license-requirements-for-immersive-spaces-in-teams.md)]

## What are the data handling standards for Mesh?

Mesh is a part of M365, and it operates within the [M365 compliance framework](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview), including with respect to security and privacy commitments.

## How to download Mesh on Quest 2 via App Lab

Microsoft Mesh for Meta Quest devices is available through AppLab.

If you had previously downloaded the **Napili** app on your Quest 2 device, you should move to the new app available at the link below.

**Napili** will be deprecated in lieu of the new Microsoft **Mesh (Preview) app**.

1. On your PC, visit the link below to download Mesh on Quest 2.

    > [!div class="nextstepaction"]
    > [Microsoft Mesh on Oculus Quest 2 \| Oculus](https://www.meta.com/experiences/6750166401689690/)

    If the URL doesn't work, use a new private window in your browser.

2. Sign in with your **Meta device account** (*not* your corporate AAD account). This could be your Meta ID, Facebook account, or another
    email.

    [Can't find your Meta account associated with your Quest 2 device?](#how-do-i-find-my-meta-id)

    ![Log in to meta account](media/log-in-meta.png)

3. Once authenticated, select the **Get** button.

    ![Screenshot of the Meta Mesh page on Meta](media/mesh-meta-quest-get.png)

4. You'll see the button grey out and change from **Get** to **Purchased** which indicates that the app has been acquired.

    ![Log in with your Meta account confirmation page](media/mesh-meta-purchased.png)

    >[!Note]
    >You may need to restart your headset to ensure the app loads.

### How do I find my Meta ID?

Log in to Oculus in a web browser, go to **Profile**, and get your email.

1. Go to the Oculus login page on your web browser: [Log in with Facebook \| Meta](https://auth.oculus.com/login/)

2. Continue with your Facebook account or log in with your Oculus account.

3. It should bring you to your **Profile** page. If not, click your **Profile** icon in the top right corner.

   ![A screenshot of profile icon](media/meta-profile.png)

4. Select **Profile**. From there you should see your Email.

#### How to open Mesh on Quest 2

1. Start up your Quest. Use the Oculus button to open the dashboard menu.

1. Select the **App library** button.

    ![the App library button on your Quest menu](media/meta-menu.png)

1. Find the **Microsoft Mesh (Preview)** app in the App library.

1. Select to **Install** then **Open** the app by selecting it again.

1. Complete the device login flow using the link below on your computer (*this requires a mobile phone for verification*): https://login.microsoftonline.com/common/oauth2/deviceauth

    >[!Note]
    >If the code doesn't work, quit the Microsoft Mesh app and restart it.

    You'll see a window like this when the authentication is complete:

    ![A screenshot of the Mesh startup page as you verify the Quest device on your Microsoft webpage](media/mesh-startup-page.png)

1. Select to **Allow** any **Terms of service & Allow Diagnostic data**.

1. Accept the **Terms of service & Allow Diagnostic data**.

### What should I do if the Mesh app on Windows crashes during startup, crashes during runtime, or behaves strangely during runtime?

1. Confirm you have a license required to use Mesh as shown [here](../setup/content/preparing-your-organization.md#verify-your-licenses-and-policies).

1. Double check that the machine has the latest Operating System and security updates.

1. Double check that your network admins have allowlisted the required endpoints as described [here](../setup/content/preparing-your-organization.md#work-with-your-organizations-security-team).

1. Gather the logs from your device: `%USERPROFILE%\AppData\LocalLow\Microsoft\Microsoft Mesh\`.

1. If the logs are too large to share, the two most important are `Player.log` and `Player-prev.log`.

1. Open a support request by following the link [here](https://admin.microsoft.com) (this support link may only be available to M365 admins).

### How to get a list of signed-in users to Mesh?

Admins may desire a list of users that have signed in to Mesh. You can use the Microsoft Azure portal get a list of users that have signed-in to Mesh due to the fact that all users sign into Mesh with their Microsoft Entra ID (formerly known as Azure Active Directory).

#### Prerequisites

Before you begin, make sure you have the following:

- A Microsoft Azure administrator account with an active Microsoft Entra ID.

Follow these steps to get a list of signed-in users to Mesh from the Azure portal:

1. Open your web browser and go to [https://portal.azure.com/](https://portal.azure.com/).

1. Sign in with your Microsoft Azure administrator account credentials.

1. Click on the menu button in the upper left corner to open the portal menu.

1. In the portal menu, select **Microsoft Entra ID**.

    :::image type="content" source="media/list-users-azure-entra-id.png" alt-text="Screenshot of Azure portal showing Entra idea selected in the list of resources.":::

1. On the Microsoft Entra ID page menu, click **Sign-in logs** under the **Monitoring** section.

    :::image type="content" source="media/list-users-sign-in-logs.png" alt-text="Screenshot of Azure portal showing Sign in logs highlighted.":::

1. Update the filter to find only Mesh users:
    - Date: Last 1 month (or choose the time period you’re interested in)
    -Show dates as: Local
    - Time aggregate: 24 hours
    - Add filters
        - Resource (filter by Resource name: Microsoft Mesh Services)
    - **OPTIONAL**: filter to Immersive spaces for Teams usage only:
        - Add filters
            - Application (filter by app name: Microsoft Teams)
    - **OPTIONAL**: filter to Microsoft Mesh PC standalone and Quest VR usage only:
        - Add filters
            - Application (filter by app name: Microsoft Mesh)

1. Switch to the **User sign-ins (non-interactive)** page:

    :::image type="content" source="media/list-users-date-resource-filters.png" alt-text="Screenshot of user sign ins page in Azure portal showing filters date, user sign ins non-interactive, mesh service highlighted.":::

1. Verify the list of **User sign-ins (non-interactive)** looks accurate and then click the **Download > Download JSON** menu item to open the Download pane.

    :::image type="content" source="media/list-users-date-download-JSON.png" alt-text="Screenshot of Azure portal showing Download JSON highlighted.":::

1. Click the **Download** button underneath the file named **NonInteractiveSignIns…** to save the records locally.

    :::image type="content" source="media/list-users-date-download-button.png" alt-text="Screenshot of Azure portal showing download button highlighted.":::

### What should I do with issues relating to M365?

You'll need to first reproduce the problem, and then follow the steps below to collect all information related to Mesh:

1. Click the **?** help icon in the M365 header.

    ![A screenshot of the About Mesh dialog in the Mesh Portal](media/m365-about-mesh.png)

1. Click the **About Mesh** link in the **Other resources** section. You may need to scroll down to the bottom of the screen to see this option.
1. Click the **Copy all** button.
1. Share that data with [Microsoft support](https://admin.microsoft.com) (this support link may only be available to M365 admins).

The data should be your version of the following: 

- **Portal host:**
- **Portal version:**
- **Session ID:**
- **Tenant ID:**
- **Trace ID:**
- **Date:**

**I recently created an environment collection and can't create environments or templates yet. What's causing this?**

The M365 backend takes a certain amount of time to fully initialize every required dependency for content creation. This can result in your newly created collection not being available yet when you try to create an environment with the Mesh Uploader or create a template in the Mesh app or Mesh on the web. For example, the OneDrive backend not being fully initialized yet would prevent environment or template creation, but eventually it will resolve. For newly created collections, you can monitor progress by navigating to the **Collections** page in Mesh on the web and clicking the **View details** button for your collection.

![A screen shot of the Mesh on the web Collections page with the View details button highlighted.](media/001-collections-view-details.png)

Environment collections that are still initializing will show the spinner "progress" animation and status message as shown here:

![A screen shot of the message stating that the collection was successfully created.](media/002-collection-creation-progress-spinner.png)

**I was recently added as a member to a collection and can't create environments or templates yet.**

Unfortunately, there's no easy way for you to track your permission sync progress. We estimate that this process can take up to 30 minutes, so we recommend that you try again after that period of time. This might require several attempts since the precise waiting period isn't known. **Tip**: This is related to the underlying M365 group permissions/SharePoint.

[Learn more about setting up your organization and provisioning your tenant](../Setup/Content/preparing-your-organization.md#consider-which-tenant-to-provision-for-mesh).

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
