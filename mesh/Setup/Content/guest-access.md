---
# Required metadata
# For more information, see https://review.learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata?branch=main
# For valid values of ms.service, ms.prod, and ms.topic, see https://review.learn.microsoft.com/en-us/help/platform/metadata-taxonomies?branch=main

title:       # Add a title for the browser tab
description: # Add a meaningful description for search results
author:      Sean-Kerawala # GitHub alias
ms.author:   sekerawa # Microsoft alias
ms.service:  # Add the ms.service or ms.prod value
# ms.prod:   # To use ms.prod, uncomment it and delete ms.service
ms.topic:    # Add the ms.topic value
ms.date:     10/28/2024
---

# Invite guest attendees to Mesh events

> [!NOTE]
> **Guest access is currently limited to Mesh Technology Adoption Program (Mesh TAP) customers.** The capability is rolling out to broader audiences starting in November 2024, in accordance with the **[Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?msockid=36ab16f6af646d611d69025aaede6c56&filters=&searchterms=guest%2Caccess)**, Feature ID: 413713
Mesh events allow for even better collaboration for more people by supporting guest user attendees into the Mesh PC app. Event organizers can invite guest users outside their organization, providing an opportunity for broader collaboration and networking in Mesh events. Guests can sign in to the Mesh app to join events, participate in discussions, and experience the same interactive features as internal users, all while maintaining secure access control. Guest user creation follows the existing process for tenant guest user creation (outside of Mesh). 

- Admins (Global Admins, User Admins, Guest Inviters) add Guests via the Microsoft Admin Center 

- Guests need licenses (any Teams Premium prerequisite + Mesh Trial, or Teams Premium) 

- Guests log in securely and enter a deep join link in the Mesh app 

- Base tenant user must join before Guest 

- No prompt is needed to accept joining users

**Invite an external guest user to a Mesh event**

1. Add a Guest user Follow the existing process for [tenant guest user creation using Microsoft Entra ID](/entra/external-id/b2b-quickstart-add-guest-users-portal).

1. 1. x

For this release, guest users would require a Teams Premium license, just like regular tenant attendees, to collaborate within Mesh.

Limitations

- Organizers must share event links with Guests 

- Guests can only be Attendees, not Organizers 

- Guests cannot schedule or customize events 

- Guests won't see Mesh events in their calendar 

- Guest access not supported on WebGL or Quest 

- Images and Video links must be properly permissioned for Guest

- Guest users may need to sign in twice 

