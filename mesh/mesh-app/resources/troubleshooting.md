---
title: Troubleshooting common Error Messages
description: Troubleshooting information for the Mesh app.
ms.prod: mixed-reality
author: qianw211
ms.author: qianwen
ms.date: 4/21/2022
ms.topic: troubleshooting
keywords: mixed reality, development, getting started, documentation, guides, features, holograms
---

# Troubleshooting common Error Messages

While running the Mesh app, you may run into the following errors.

## Connection and loggin

### WelcomeScreen_Message_NetworkError

*Failed to connect to server.*

This message is shown when you failed to connect since your servers can't be reached.

Mesh network uses the following ports and IP addresses.

For normal port 80 and 443 for HTTP traffic, we use an application service that may connect on: 843/tcp 4520/tcp 4530/tcp 4531/tcp 4533/tcp 5055/udp 5056/udp 5058/udp 6060/tcp 6061/tcp 6063/tcp 9090/tcp 9091/tcp 9093/tcp 19090/tcp 19091/tcp 19093/tcp.

Hosts can be any of the following: fnx-pht-prod-mstr.westus2.azurecontainer.io, fnx-pht-prod-gs0.westus2.azurecontainer.io, fnx-pht-prod-gs1.westus2.azurecontainer.io.

We'll also be using TCP and UDP on ports 30000-31000 and IP Addresses matching the AzureCloud service tag: [Download Azure IP Ranges and Service Tags – Public Cloud from Official Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=56519).

### WelcomeScreen_Message_LoginFailed

*Login failed.*

This message is shown when you failed to login.

### WelcomeScreen_Message_LoginFailed_Format

*Login failure: `{0}`*

This message is shown when login fails. `{0}` will be a detailed error message.

### WelcomeScreen_Message_PermissionsDenied

*Microphone access is required to use this application. Please go to settings to enable microphone access.*

This message is shown when your app is denied permission to access the microphone.  Microphone acces is required for the Mesh app to function.

### WelcomeScreen_Message_SpaceLoadError

*Loading user information failed.*

This message is shown when we failed to get the user information we need to initially connect.

### WelcomeScreen_Message_UpdatesError

*Update failed.*

This message is shown when we failed to get or install updates.

## Joining a call

### HoloCallMedallion_ErrorText_Default

*Something went wrong.*

This message is displayed when a call join fails.

### HoloCallMedallion_ErrorText_Booted

*The space has been deleted or you have been removed.*

This message is displayed when a call join fails.

### HoloCallMedallion_ErrorText_CheckConnection

*{0}&#xA;&#xA;Check your network connection*

This message is displayed when a connection error has likely occurred. {0} is details about the error.

## Scene apps

### Apps_Error_ConnectionFailed

*Something went wrong when trying to run {0}.*

This message is displayed when we fail to connect to an app. {0} will be the name of the app.

### Apps_Error_UnsupportedVersion

*{0} requires a newer version of Microsoft Mesh App.*

This message is displayed when we fail to connect to an app because it doesn't support our client version. {0} will be the name of the app.

## General issue in the spaces panel

### Spaces_Error

*Contacts error: {0}*

This message is displayed when an error occurs in the spaces panel. {0} is the error description.

## Custom content loading

### Content_Error_Size

*Model exceeds the recommended size of {0} MB.*

This message is shown when a model file is too large. {0} is the file size limit.

### Content_Error_Load

*Failed to load model, do you want to retry?*

This message is shown when a model fails to load.

## Remote Rendering (ARR)

### RemoteModels_ConfigParseError

*Failed to parse json configuration for remote rendered models. Check formatting and try again.*

This message is displayed when the remote model's configuration is not formatted correctly.

### RemoteModels_UriParseError

*Failed to parse model URI from the remote models configuration. Check the URI and try again.*

This message is shown when the remote model's configuration is not formatted correctly.

## Colocation

### Colocation_Failure

*There was a problem trying to co-locate. Please leave the space and try rejoining again.*

This error occurs when colocation fails. 