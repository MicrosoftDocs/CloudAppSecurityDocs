---
# required metadata
title: Cloud App Security Activities API
description: This article provides information about using the Activities API.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 03/27/2020
ms.topic: reference
ms.collection: M365-security-compliance
ms.service: cloud-app-security

# optional metadata
ms.suite: ems
---
# Activities API

*Applies to: Microsoft Cloud App Security*

The Activity API gives you visibility into all actions performed in your cloud apps. The data from this API can supply information regarding who logs in to which app and when, which files are being downloaded from suspicious locations, and so on.

The following is a list of activity requests:

- [List activities](api-activities-list.md)
- [Fetch activity](api-activities-fetch.md)
- [Feedback on activity](api-activities-feedback.md)

## Filters

For information about how filters work, see [Filters](api-introduction.md#filters).

The following is a list of supported filters:

| Filter | Type | Operators | Description |
| --- | --- | --- | --- |
| service | integer | eq | neq Filter activities related to the specified service appID, for example: 11770 |
| instance | integer | eq, neq | Filter activities from specified instances |
| user.orgUnit | string | eq, neq, isset, isnotset | Filter activities by the organization unit of the performing user |
| activity.eventType | string | eq, neq | Filter activities by event type |
| activity.id | string | eq | Find an activity by ID |
| activity.impersonated | boolean | eq | If set to “true”, returns only impersonated events, if set to “false”, returns non-impersonated events |
| activity.type | boolean | eq | If set to “true”, returns only admin events, if set to “false”, returns regular events |
| activity.takenAction | string | eq, neq | Filter activities by the actions taken on them. Possible values include:<br /><br />**block**: Blocked<br />**proxy**: Redirected to session control<br />**BypassProxy**: Bypass session control<br />**encrypt**: Encrypted<br />**decrypt**: Decrypted<br />**verified**: Verified<br />**encryptionFailed**: Encryption failed<br />**protect**: Protected<br />**verify**: Require step-up authentication<br />**null**: No action |
| device.type | string | eq, neq | Filter activities by device type. Possible values include:<br /><br />**DESKTOP**: PC<br />**MOBILE**: Mobile<br />**TABLET**: Tablet<br />**OTHER**: Other<br />**null**: No value |
| device.tags | string | eq, neq | Filter activities by device tag IDs |
| userAgent.userAgent | string | contains, ncontains | Filter activities that do or do not contain the given strings in the user agent |
| userAgent.tags | string | eq, neq | Filter activities containing the specified user agent tag IDs |
| location.country | string | eq, neq, isset, isnotset | Filter activities originating from the specified country/region code |
| location.organizations | string | eq, neq, isset, isnotset, contains | Filter activities originating from the specified organization |
| ip.address | string | eq, startswith, doesnotstartwith, isset, isnotset, neq | Filter activities originating from the given IP address |
| fileSelector | file | eq, neq | Filter activities containing the specified file/folder |
| office365url | string | startswith, eq, endswith | Filter activities by Office 365 URLs |
| fileId | string | eq | Find a file by ID |
| ip.category | integer | eq, neq | Filter activities with the specified subnet categories. Possible values include:<br /><br />**1**: Corporate<br />**2**: Administrative<br />**3**: Risky<br />**4**: VPN<br />**5**: Cloud provider<br />**6**: Other |
| ip.tags | string | eq, neq | Filter activities by IP tag IDs |
| text | string | eq, startswithsingle, text | Filter activities by performing a free text search |
| date | timestamp | lte, gte, range, lte_ndays, gte_ndays | Filter activities that occurred in the specified time ranges |
| policy | string | eq, neq, isset, isnotset | Filter activities related to the specified policies |
| source | string | eq, neq | Filter all activities by source type or stream ID. Example: `[{ “s:stream-id”, “t:source-type” }]` Possible source type values include:<br /><br />**0**: Access control<br />**1**: Session control<br />**2**: App connector<br />**3**: App connector analysis<br />**5**: Discovery<br />**6**: MDATP |
| activity.alertId | string | eq | Filter all activities relevant to an alert id |
| activityObject | string | eq, neq | Filter activities containing the specified Id |
| fileLabels | string | eq, neq | Filter files containing the specified file labels (tags) IDs |
| created || lte, gte, range, gt, lt, eq | |
| entity | entity pk | eq, neq, isset, isnotset, startswith | Filter activities by the entity who performed the activity. Example: `[{ “id”: “entity-id”, “saas”: 11161, “inst”: 0 }]` |
| user.username | string | eq, neq, isset, isnotset, startswith | Filter activities by the user who performed the activity |
| user.tags | string | eq, neq, isset, isnotset, startswith | Filter activities by tags belonging to the performing user. Requires group IDs |
| activity.azureSubscriptions | string | eq, neq | Filter azure subscriptions activities |
| user.domain | string | eq, neq, isset, isnotset | Filter activities by the performing user domain |

[!INCLUDE [Open support ticket](includes/support.md)]
