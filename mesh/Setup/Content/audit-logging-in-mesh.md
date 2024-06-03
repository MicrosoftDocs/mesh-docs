---
title: Audit logging for Microsoft Mesh
description: As an admin, use audit logging to investigate events for the Mesh application and associated Azure or M365 events, and immersive spaces in Teams.
ms.service: mesh
author: typride  
ms.author: tmilligan
ms.date: 04/22/2024
ms.topic: Concept
keywords: Microsoft Mesh, M365, Unity, API, reference, documentation, features, performance, powershell, Microsoft Purview, Exchange Online PowerShell
#customer intent: As a admin, I want to perform audit logging for Mesh so that organizations can respond to and track down events that occur with Mesh resources.
---

# How to perform audit logging for Mesh

Audit logging help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations. This article summarizes how to query and request audit logs for Microsoft Mesh operations and events. Some operations are Mesh specific, while others are associated with other M365 operations, such as M365: Exchange, SharePoint, Microsoft Entra (Azure AD) operations, Microsoft Teams, etc.

With audit logging for Mesh, an admin can gather insights into individual or bulk operations that relate to User Activity or operations which result from interactions with M365 services for Microsoft Mesh.

Audit logging for Mesh can be done using Microsoft Purview or Exchange Online PowerShell.

> [!NOTE]
> Microsoft Mesh has two main offerings for users:  Immersive spaces in Teams and custom immersive spaces. Audit logging does not treat these offerings as independent and thus the events in the audit may refer to either offering or both offerings, depending on the event you query.

Examples of user activity and operations that an admin may be interested in for Mesh are:

- **End-users** in Mesh in Teams / Mesh Browser - joining Mesh sessions.

- **Mesh Administrators** and Users creating Events on Mesh Portal.

- **Content Creators** using Mesh Toolkit (Mesh Uploader) to create and upload artifacts.

## Auditable events for Microsoft Mesh

The audit events that are currently available are listed below. Events are generated based on user activity in Mesh Admin portal, or session/template customization activity in the Mesh application.

|Event Name| Description|
| ------------------------------ | -----------------------------------------------------------|
| EnvironmentDeleted             | Delete a Mesh Environment.                                 |
| EnvironmentPublished           | Publish a new version of a Mesh Environment.               |
| ComponentCreated               | Create a session component for a given Mesh session.       |
| ComponentDeleted               | Delete a session component of a given Mesh session.        |
| TemplateCreated                | Create a new Mesh World/Collection Template.               |
| TemplateDeleted                | Delete Mesh World Template contents and metadata.          |
| TemplateUpdated                | Update an existing Mesh World/Collection Template.         |
| WorldCreated                   | Create a Mesh World/Collection.                            |
| WorldDeleted                   | Delete a Mesh World/Collection.                            |
| WorldUpdated                   | Update a Mesh World/Collection.                            |
| WorldMembersAdded              | Add members to the Mesh World/Collection.                  |
| WorldOwnersAdded               | Add owners of a Mesh World/Collection.                     |
| WorldMembersRemoved            | Remove a member from a Mesh World/Collection.              |
| WorldOwnersRemoved             | Remove an owner from a Mesh World/Collection.              |
| EnvironmentStorageCreated      | Create a new storage location for a Mesh Environment.      |
| SessionMetadataCreated         | Create Mesh World/Collection Session Metadata.             |
| SessionMetadataDeleted         | Delete Mesh World/Collection Session Metadata.             |
| SessionMetadataUpdated         | Update Mesh World/Collection Session Metadata.             |
| SessionMetadataTemplateCreated | Create a template customization for Mesh World/Collection. |
| SessionEnvironmentSet          | Set the environment for a collaboration session.           |
| SessionJoin                    | Mesh service provisioned the necessary system resources and provided the client application with the information required to join a Mesh session. |

Some clarification on what the terminology in these events refers to:

- **Session**: refers to sessions when certain things are configured for environments or meetings. There are three types of sessions that are captured by audit logs:
  - *Template Customization Session*: logs are captured when a user customizes an event template and saves changes in the Mesh application.
  - *Event Customization Session*: logs are captured when a user customizes a single event and saves changes in the Mesh application.
  - *Event Session*: logs are captured when a Mesh event occurs. Typically, the configuration is immutable since components cannot be placed by users in a live event, for example.

- **World** : refers to Collections in Mesh on the web. Collections is a bucket that holds environments and templates of environments that are used in Mesh events. Audit logs capture when a user creates a Collection, deletes a Collection, adds members to a Collection, adds Owners to a Collection, or removes Owners from a collection.

- **Component**: refers to the Objects that are rendered in an environment when a session is started for an event, template, or customization session. If a user attempts to enter an environment, the components in that environment are loaded and captured by component logs.

## [Microsoft Purview](#tab/microsoft-purview)

Microsoft Purview auditing solutions provide an integrated solution to help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations.

### Prerequisites for Purview audit logging solutions

[See how to get started with Microsoft Purview audit logging solutions](/purview/audit-get-started).

### Get started with search

[See how to search the audit log in Microsoft Purview](/purview/audit-search?tabs=microsoft-purview-portal).

### Export, configure, and view audit log records

[How to export, configure, and view audit log records](/purview/audit-log-export-records).

## [Exchange Online PowerShell](#tab/exchange-online-powershell)

### Prerequisites for using Exchange Online PowerShell

In order to conduct audit logging for Mesh operations, the following prerequisites are required:

- Access and familiarity with [Microsoft Purview for audit logging](/purview/purview)
- Access and familiarity with [PowerShell Exchange cmdlet](/purview/audit-log-search-script)
- Administrator permissions [required to run cmdlet commands](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)
- Microsoft Excel or another data analysis tool to analyze the data once it's gathered
- PowerShell v7

### Gather audit logs for Mesh

#### Connect to Exchange Online PowerShell

In PowerShell, load the Exchange Online PowerShell module

```powershell
Import-Module ExchangeOnlineManagement
```

Connect and authenticate

```powershell
Connect-ExchangeOnline -UserPrincipalName [USER]@[AADDOMAIN].com
```

For more information, see [how to connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

#### Verify that audit logging is on

Audit logging is turned on by default for Microsoft 365 organizations. However, when setting up a new Microsoft 365 organization, you should verify the auditing status for your organization. For instructions, see how to [turn auditing on or off](/purview/audit-log-enable-disable).

> [!TIP]
> To check the permissions required for each cmdlet, please visit [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/find-exchange-cmdlet-permissions?view=exchange-ps&preserve-view=true).

#### Search for Unified AuditLog events

Once you've verified that audit logging is turned **on** and you have the proper permissions to run cmdlets, you can now search for log records using the [Search-UnifiedAuditLog command](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps&preserve-view=true) with various filters.

> [!IMPORTANT]
> There are a wide array of parameters for `Search-UnifiedAuditLog`. Please review [Search-UnifiedAuditLog documentation | Microsoft Learn](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps&preserve-view=true) for more info.

The audit record contents contain the following fields:

- **RecordType** - workload type, e.g. SharePoint or *MeshWorlds*
- **CreationDate**
- **UserIds** - users performing an operation.
- **Operations** - typically Operation Name or Operation Names.
- **AuditData** - JSON-encoded detailed event data. Contents differ depending on workload type.
- **ResultIndex** - index of a row in a result returned by PowerShell script (1-N...).
- **ResultCount** - total count of rows returned by PowerShell script.
- **Identity** - Azure ID/Microsoft Entra GUID of the user.

##### Search-UnifiedAuditLog example 1

A basic query for audit logs with `-StartDate` and `-EndDate`.

```powershell
Search-UnifiedAuditLog -StartDate 2024-04-01 -EndDate 2024-05-01 | Export-Csv -Path .\export-all.csv -NoTypeInformation
```

The record contents will come in a format that may be hard to parse initially, but once formatted it should be understandable.

Example response:

```json
"AzureActiveDirectory","4/9/2024 6:49:03 PM","[XXXXXXX]@[XXXXX].com","Update group.","{""CreationTime"":""2024-04-09T18:49:03"",""Id"":""871d4a2e-8e38-488e-a83e-b7a7c6c65228"",""Operation"":""Update group."",""OrganizationId"":""05e05ab5-f8a3-409d-bfa5-01edb8cecf82"",""RecordType"":8,""ResultStatus"":""Success"",""UserKey"":""10032002CCA9134A@meshrp.onmicrosoft.com"",""UserType"":0,""Version"":1,""Workload"":""AzureActiveDirectory"",""ClientIP"":""20.171.55.147"",""ObjectId"":""Group_1ae6e759-85e0-4f8f-b6b5-691b72ca1ba7"",""UserId"":""[XXXXXXX]@[XXXXX].com"",""AzureActiveDirectoryEventType"":1,""ExtendedProperties"":[{""Name"":""additionalDetails"",""Value"":""{\""GroupType\"":\""Unified\"",\""User-Agent\"":\""kiota-dotnet\/1.3.4\""}""},{""Name"":""extendedAuditEventCategory"",""Value"":""Group""}],""ModifiedProperties"":[{""Name"":""Description"",""NewValue"":""[\r\n  \""New collection of stuff for M365 Audit feature testing\""\r\n]"",""OldValue"":""[\r\n  \""New collection of stuff\""\r\n]""},{""Name"":""MailNickname"",""NewValue"":""[\r\n  \""MyCollectionofStuff2272\""\r\n]"",""OldValue"":""[\r\n  \""MyCollectionofStuff2\""\r\n]""},{""Name"":""Included Updated Properties"",""NewValue"":""Description, MailNickname"",""OldValue"":""""},{""Name"":""TargetId.GroupType"",""NewValue"":""Unified"",""OldValue"":""""}],""Actor"":[{""ID"":""[XXXXXXX]@[XXXXX].com"",""Type"":5},{""ID"":""10032002CCA9134A"",""Type"":3},{""ID"":""Microsoft Mesh Services"",""Type"":1},{""ID"":""3016d0ce-47cc-4005-b11d-5fcabb1b643d"",""Type"":2},{""ID"":""User_c7e95ea2-64f6-4743-b8e6-52ce520cba81"",""Type"":2},{""ID"":""c7e95ea2-64f6-4743-b8e6-52ce520cba81"",""Type"":2},{""ID"":""User"",""Type"":2}],""ActorContextId"":""05e05ab5-f8a3-409d-bfa5-01edb8cecf82"",""ActorIpAddress"":""20.171.55.147"",""InterSystemsId"":""2cd62b4e-4744-4c55-8a88-e64771393266"",""IntraSystemId"":""0b9fe72c-eca5-4ad5-a9c5-5986e8bc963d"",""SupportTicketId"":"""",""Target"":[{""ID"":""Group_1ae6e759-85e0-4f8f-b6b5-691b72ca1ba7"",""Type"":2},{""ID"":""1ae6e759-85e0-4f8f-b6b5-691b72ca1ba7"",""Type"":2},{""ID"":""Group"",""Type"":2},{""ID"":""My Collection of Stuff 2"",""Type"":1}],""TargetContextId"":""05e05ab5-f8a3-409d-bfa5-01edb8cecf82""}","4","2148","871d4a2e-8e38-488e-a83e-b7a7c6c65228","True","Unchanged"
```

> [!TIP]
> `-NoTypeInformation` is [a PowerShell utility](/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7.4&preserve-view=true) to make .csv exports cleaner.

##### Search Search-UnifiedAuditLog example 2

A basic query for all audit logs with `-Operations` that include the `World` string.

```powershell
Search-UnifiedAuditLog -StartDate 2024-04-01 -EndDate 2024-05-01 -Operations World* | Export-Csv -Path .\export-all-world.csv -NoTypeInformation
```

##### Search Search-UnifiedAuditLog example 3

A basic query for all audit logs with `-UserIds` that include the `[email@company.com]` string.

```powershell
Search-UnifiedAuditLog -StartDate 2024-04-01 -EndDate 2024-04-10 -UserIds [email@company.com] | Export-Csv -Path .\export-all-Max.csv -NoTypeInformation
```

### Record contents analysis

The audit log record contents return in a JSON format. AuditData analysis may require a familiarity with [parsing text as JSON or XML](https://support.microsoft.com/en-us/office/parse-text-as-json-or-xml-power-query-7436916b-210a-4299-83dd-8531a1d5e945).

The set of records can be imported to Excel for analysis. For more info, see [how to import data from sources into Excel](https://support.microsoft.com/en-us/office/import-data-from-data-sources-power-query-be4330b3-5356-486c-a168-b68e9e616f5a).

---
