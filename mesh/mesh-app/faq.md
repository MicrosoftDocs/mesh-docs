---
title: Microsoft Mesh app (Preview) frequently asked questions
description: Microsoft Mesh app (Preview) frequently asked questions.
ms.prod: mixed-reality
author: qianw211    
ms.author: v-qianwen
ms.date: 8/16/2021
ms.topic: overview
keywords: mixed reality, getting started, documentation, guides, features, holograms
---
# Microsoft Mesh app (Preview) troubleshooting and frequently asked questions

## Frequently asked questions

### What languages are supported?

- Language support is currently en-us.

### What devices are supported?

- Microsoft Mesh app (Preview) requires a [HoloLens 2](/hololens/hololens2-options) with Windows 10, version 2004 (build 19041) or greater. For info about updating Windows, see [Update HoloLens](/hololens/hololens-update-hololens).

### How do I sign in to collaborate in the Microsoft Mesh app (Preview)?

- To use the Mesh app (Preview), you must sign in with either:
  - An [Azure Active Directory (Azure AD)](/azure/active-directory/) account that has been provisioned with an O365 license that includes access to OneDrive for Business.
  - A personal [Microsoft Account (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts).
- For more info about accounts, see [Manage user identity and sign-in for HoloLens](/hololens/hololens-identity).

### Who shows up in my Contacts list in the app?

- For Azure AD users, Contacts will show all the users in your organization, but other users will have to set up the Microsoft Mesh app (Preview) on their HoloLens to receive calls.
- For MSA users, Contacts will show those currently in your email address book who have also set up the Microsoft Mesh app (Preview) on their HoloLens.

### How many people can be in a collaborative space at one time?

- The maximum number of users in a session is 8.

### Where does my data go?

- User content is stored in your OneDrive storage at Apps > Microsoft Mesh app (Preview) > MyContent.
- Shared content is stored in your OneDrive storage at Apps > Microsoft Mesh app (Preview) > _spaceGUID_.space.
- Your avatar customization is stored in your OneDrive storage.
- The drawing data that gets created in a session is stored in the OneDrive account of the user that created the session initially.

### What data is shared with Microsoft?

We collect information about your organization's identity, your account ID, and usage data related to the latency and performance of the service and app. See [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).

### The app says that my account isn't configured to use Mesh. What should I do?

- In order to use the Microsoft Mesh app (Preview), you'll need to enable the service for your organization. Some companies may require you to have your admin specially enable this. You can find more information for your admin in [Set up Microsoft Mesh for your organization](../provisioning.md).

### How do I sign out of Mesh app

- Look at your hand to [bring up the menu](use-mesh/use-mesh.md#the-hand-menu), and press the **Main menu button** at the top.  Go to **Settings**, and on the **Account** tab, click **Sign out** next to your user information.  Click **Yes**.

    <img src="media\mesh-app-sign-out.png" alt="Screenshot of the **settings** tab." width=500px>

## Feedback and support

### How do I file feedback or request a feature?

- Provide your suggestions and insights through Feedback Hub. Our team looks at logs and feedback filed through the [Feedback Hub](/hololens/hololens-feedback) app, under **Windows Holographic\Collaboration**.

### How do I get support for the Mesh app?

- Please visit [Support for business](https://support.serviceshub.microsoft.com/supportforbusiness/) and file a support ticket to get in contact with a Mixed Reality Support representative.
