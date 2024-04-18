---
title: Release notes for Mesh
description: Mesh release notes
ms.service: mesh
author: typride  
ms.author: tmilligan
ms.date: 04/16/2024
ms.topic: Guide
keywords: Microsoft Mesh, M365, Unity, API, reference, documentation, features, performance, powershell, Microsoft Purview
---

# Audit logging in Mesh

## Overview

> [!NOTE]
> Currently, all audit logging is queried using Exchange Online PowerShell. Soon audit logs will be available in Microsoft Purview portal.

<!---
Microsoft Purview auditing solutions provide an integrated solution to help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations.
--->
Audit logging help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations. This article summarizes how to query and request audit logs for Microsoft Mesh operations and events. Some operations are Mesh specific, while others are associated with other M365 operations, such as M365: Exchange, SharePoint, Microsoft Entra (Azure AD) operations, Microsoft Teams, etc. with audit logging for Mesh, an admin can gather insights into individual or bulk operations that relate to User Activity or operations which result from interactions with M365 services for Microsoft Mesh.

Audit logging for Mesh can be done using [Exchange Online Powershell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).

> [!NOTE]
> Microsoft Mesh has two main offerings for users:  Immersive spaces in Teams and custom immersive spaces. Audit logging does not treat these offerings as independent and thus the events in the audit may refer to either offering or both offerings, depending on the event you edit.

Examples of user activity and operations that an admin may be interested in for Mesh are:

- **End-users** in Mesh in Teams / Mesh Browser - joining Mesh sessions.

- **Mesh Administrators** and Users creating Events on Mesh Portal.

- **Content Creators** using Mesh Toolkit (Mesh Uploader) to create and upload artifacts.

### Prerequisites

In order to conduct audit logging for Mesh operations, the following prerequisites are required:

- Access and familiarity with [Microsoft Purview for audit logging](/purview/purview)
- Access and familiarity with [PowerShell Exchange cmdlet](/purview/audit-log-search-script)
- Administrator permissions [required to run cmdlet commands](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
- Microsoft Excel or another data analysis tool to analyze the data once it's gathered
- PowerShell v7

The audit events that are currently available are listed below. Events are generated based on user activity in Mesh Admin portal, or session/template customization activity in the Mesh application.

| Event name                     | Description                                           |
|--------------------------------|-------------------------------------------------------|
| EnvironmentDeleted             | Delete a Mesh Environment.                            |
| EnvironmentPublished           | Publish a new version of a Mesh Environment.          |
| ComponentCreated               | Create a session component for a given Mesh session.  |
| ComponentDeleted               | Delete a session component of a given Mesh session.   |
| TemplateCreated                | Create a new Mesh World Template.                     |
| TemplateDeleted                | Delete Mesh World Template contents and metadata.     |
| WorldCreated                   | Create a Mesh World.                                  |
| WorldDeleted                   | Delete a Mesh World.                                  |
| WorldUpdated                   | Update a Mesh World.                                  |
| WorldMembersAdded              | Add members to the Mesh World.                        |
| WorldOwnersAdded               | Add owners of a Mesh World.                           |
| WorldMembersRemoved            | Remove a member from a Mesh World.                    |
| WorldOwnersRemoved             | Remove an owner from a Mesh World.                    |
| EnvironmentStorageCreated      | Create a new storage location for a Mesh Environment. |
| SessionMetadataCreated         | Create Mesh World Session Metadata.                   |
| SessionMetadataDeleted         | Delete Mesh World Session Metadata.                   |
| SessionMetadataUpdated         | Update Mesh World Session Metadata.                   |
| SessionMetadataTemplateCreated | Create a template customization for Mesh World.       |
| SessionEnvironmentSet          | Set the environment for a collaboration session.      |

Some clarification on what the terminology in these events refers to:

- **Session**: refers to sessions when certain things are configured for environments or meetings. There are three types of sessions that are captured by audit logs:
  - *Template Customization Session*: logs are captured when a user customizes an event template and saves changes in the Mesh application.
  - *Event Customization Session*: logs are captured when a user customizes a single event and saves changes in the Mesh application.
  - *Event Session*: logs are captured when a Mesh event occurs. Typically, the configuration is immutable since components cannot be placed by users in a live event, for example.

- **World** : refers to Collections in Mesh on the web. Collections is a bucket that holds environments and templates of environments that are used in Mesh events. Audit logs capture when a user creates a Collection, deletes a Collection, adds members to a Collection, adds Owners to a Collection, or removes Owners from a collection.

- **Component**: refers to the Objects that are rendered in an environment when a session is started for an event, template, or customization session. If a user attempts to enter an environment, the components in that environment are loaded and captured by component logs.

## Gather audit logs for Mesh

### Connect to Exchange Online PowerShell

In PowerShell, load the Exchange Online PowerShell module

`Import-Module ExchangeOnlineManagement`

Connect and authenticate

`Connect-ExchangeOnline -UserPrincipalName maxgolov@meshrp.onmicrosoft.com`

For more information, see [how to connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).

### Verify that audit logging is on

Audit logging is turned on by default for Microsoft 365 organizations. However, when setting up a new Microsoft 365 organization, you should verify the auditing status for your organization. For instructions, see how to [turn auditing on or off](/purview/audit-log-enable-disable).

> [!TIP]
> To check the permissions required for each cmdlet, please visit [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/find-exchange-cmdlet-permissions?view=exchange-ps).

### Search for Unified AuditLog events

Once you've verified that audit logging is turned **on** and you have the proper permissions to run cmdlets, you can now search for log records using the [Search-UnifiedAuditLog command](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) with various filters.

> [!IMPORTANT]
> There are a wide array of parameters for `Search-UnifiedAuditLog`. Please review [Search-UnifiedAuditLog documentation | Microsoft Learn](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) for more info.

The audit record contents contain the following fields:

- **RecordType** - workload type, e.g. SharePoint or *MeshWorlds*
- **CreationDate**
- **UserIds** - users performing an operation.
- **Operations** - typically Operation Name or Operation Names.
- **AuditData** - JSON-encoded detailed event data. Contents differ depending on workload type.
- **ResultIndex** - index of a row in a result returned by PowerShell script (1-N...).
- **ResultCount** - total count of rows returned by PowerShell script.
- **Identity** - Azure ID/Microsoft Entra GUID of the user.

#### Search-UnifiedAuditLog example 1

A basic query for audit logs with `-StartDate` and `-EndDate`.

`Search-UnifiedAuditLog -StartDate 2024-04-01 -EndDate 2024-05-01 | Export-Csv -Path .\export-all.csv -NoTypeInformation`

> [!TIP]
> `-NoTypeInformation` is [a PowerShell utility](/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7.4) to make .csv exports cleaner.

#### Search Search-UnifiedAuditLog example 2

A basic query for all audit logs with `-Operations` that include the `World` string.

`Search-UnifiedAuditLog -StartDate 2024-04-01 -EndDate 2024-05-01 -Operations World* | Export-Csv -Path .\export-all-world.csv -NoTypeInformation`

#### Search Search-UnifiedAuditLog example 3

A basic query for all audit logs with `-UserIds` that include the `[email@company.com]` string.

`Search-UnifiedAuditLog -StartDate 2024-04-01 -EndDate 2024-04-10 -UserIds [email@company.com] | Export-Csv -Path .\export-all-Max.csv -NoTypeInformation`

### Record contents analysis

The audit log record contents return in a JSON format. AuditData analysis may require a familiarity with [parsing text as JSON or XML](https://support.microsoft.com/en-us/office/parse-text-as-json-or-xml-power-query-7436916b-210a-4299-83dd-8531a1d5e945).

