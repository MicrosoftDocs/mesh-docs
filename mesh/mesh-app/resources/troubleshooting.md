---
title: Troubleshooting
description: Troubleshooting information for the Mesh app.
ms.prod: mixed-reality
author: qianw211
ms.author: v-qianwen
ms.date: 06/28/2021
ms.topic: troubleshooting
keywords: mixed reality, development, getting started, documentation, guides, features, holograms
---

# Troubleshooting Common Error Messages

While running the Mesh app, you may run into the following errors.

## Connection and loggin

### WelcomeScreen_Message_NetworkError

*Failed to connect to server.*

Message shown when you failed to connect since your servers couldn't be reached.

### WelcomeScreen_Message_LoginFailed

*Login failed.*

Message shown when login fails.

### WelcomeScreen_Message_LoginFailed_Format

*Login failure: `{0}`*

Message shown when login fails. `{0}` will be an error message

### WelcomeScreen_Message_PermissionsDenied

*Microphone access is required to use this application. Please go to settings to enable microphone access.*

Message shown when your app is denied permission to access the microphone, since it is required for app functionality.

### WelcomeScreen_Message_SpaceLoadError

*Loading user information failed.*

Message shown when we failed to get the user information we need to initially connect.

### WelcomeScreen_Message_UpdatesError

*Update failed.*

Message shown when we failed to get or install updates.

## Joining a call

### HoloCallMedallion_ErrorText_Default

*Something went wrong.*

This message is displayed when a call join fails.

### HoloCallMedallion_ErrorText_Booted

*The space has been deleted or you have been removed.*

Text that is displayed when a call join fails.

### HoloCallMedallion_ErrorText_CheckConnection

*{0}&#xA;&#xA;Check your network connection*

Text that is displayed when a connection error has likely occurred. {0} is details about the error.

## Scene apps

### Apps_Error_ConnectionFailed

*Something went wrong when trying to run {0}.*

Description when we fail to connect to an app. {0} will be the name of the app.

### Apps_Error_UnsupportedVersion

*{0} requires a newer version of Microsoft Mesh App.*

Description when we fail to connect to an app since it doesn't support our client version. {0} will be the name of the app.

## General issue in the spaces panel

### Spaces_Error

*Contacts error: {0}*

Displayed when an error occurs in the spaces panel. {0} is the error description.

## Custom content loading

### Content_Error_Size

*Model exceeds the recommended size of {0} MB.*

Shown when a loaded model file is too large. {0} is the file size limit.

### Content_Error_Load

*Failed to load model, do you want to retry?*

Shown when a model fails to load.

## Remote Rendering (ARR)

### RemoteModels_ConfigParseError

*Failed to parse json configuration for remote rendered models. Check formatting and try again.*

Message prompt when remote models configuration is not formatted correctly.

### RemoteModels_UriParseError

*Failed to parse model Uri from the remote models configuration. Check the Uri and try again.*

Message prompt when remote models configuration is not formatted correctly.

## Colocation

### Colocation_Failure

*There was a problem trying to co-locate. Please leave the space and try rejoining again.*

Error message when colocation fails.