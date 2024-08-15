---
title: Update WebSlate URLs during an event
description: Learn about how to update the URL for a WebSlate during a Mesh event.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 8/14/2024
ms.topic: conceptual
keywords: Microsoft Mesh, Web content, Web, webslate, URL, video, streaming video, whiteboard
---

## Update WebSlate URLs during an event

## Create an event in the Mesh Portal.  

1. Up to 10 minutes prior to the event (or at Start time), join the event (not Customization mode) and navigate to a WebSlate you want to edit content for.  
 
1. Open the Control Panel, find and select the WebSlate to edit, then copy/paste the URL for web content you want to display and hit Enter. 
 
 
4. (optional) Configure settings: 

- Prevent Suspension: WebSlates that are offscreen for over 30 seconds are automatically suspended to conserve memory and will reload once the user returns to the slate’s view. Turn this setting ON to disable suspension for content that needs to play for users regardless of their location in the event (e.g. for webslates running livestream content).  
- Show backplate: Adds a frame around the WebSlate for aesthetic purposes.  
- Visible: Toggles user visibility of WebSlates for all event attendees. 

*Any of these settings can be configured during events and changes will be reflected in real-time for all users.  

When anyone (users and organizers) approach the WebSlate and hover it with their cursor or VR controller, the WebSlate menu will appear. The menu contains the following:  

- Refresh button: Refreshes the WebSlate for the user who presses the button. This helps incase the user wants navigated away from the original content, or if they get an unexpected error with the web content.  
- Eye icon: Provides a tooltip explaining web content on the slate is unique to the user’s view. Some experiences may be shared, depending on the web content displayed.    
 
## Recommendations for Web content experiences in Mesh:

•	Interacting with maps, diagrams, and data  
•	Viewing dashboards and webpages  
•	Productivity apps such as Microsoft 365 apps (require manual authentication)  
•	Showcasing content that highlights products and services, customer stories, and brand identity 
 
## Limitations:  

- Web content in Mesh behaves like it would in a browser: All web content experienced in Mesh is unique to an individual user's view, meaning multiple people may see the same URL but the places they navigate to on a given page or app will not be synced. There are some exceptions to this when using apps designed for multi-user experiences - Microsoft Whiteboard and Loop (Fluid Framework apps) as examples, which show where other users are drawing or typing.  
- URL editing during customization sessions: WebSlate URLs do not persist between events or save while customizing an event before it's intended start time (before the event). Workaround: Join your event up to 10 minutes prior to start time, open the Control Panel, and change WebSlate URLs to your desired content.  
- SSO Support: Currently, WebSlate doesn’t offer SSO support for apps. For secure access content: All users must manually sign in to each web application displaying on a webslate.  
 
** Workaround**:

- For Mesh on PC, users can sign in to Microsoft Sign in-enabled apps via an account picker (also referred to as the Microsoft account manager). This is possible because Mesh leverages WebView2 on PC which is capable of recommending the user signs in via the accounts they are logged into their device with. Once logged in, subsequent apps will automatically login upon refresh without needing to sign in again. 
- For Quest, users must manually input their credentials via the keyboard. Right now, there is no option for Account picker-based sign-in.  
 
In the below example, the other attendee in the space sees their own account picker, and does not see the same view. Once both users individually log in to the content, both will see the same webpage. Subsequent navigation and scrolling will not be synced, but inputs will be synced if the webapp is capable of doing so.  