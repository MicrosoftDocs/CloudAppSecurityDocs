---
# required metadata
title: Cloud App Security Alerts API
description: This article provides information about using the Alerts API.
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
# Alerts API

*Applies to: Microsoft Cloud App Security*

The Alerts API provides you with information about immediate risks identified by Cloud App Security and require attention. Alerts can result from suspicious usage patterns or from files containing content that violates company policy.

The following lists the supported requests:

- [List alerts](api-alerts-list.md)
- [Bulk dismiss](api-alerts-bulk-dismiss.md)
- [Bulk resolve](api-alerts-bulk-resolve.md)
- [Fetch alert](api-alerts-fetch.md)
- [Dismiss alert](api-alerts-dismiss.md)
- [Mark alert as read](api-alerts-mark-read.md)
- [Mark alert as unread](api-alerts-mark-unread.md)

## Filters

For information about how filters work, see [Filters](api-introduction.md#filters).

The following table describes the supported filters:

| Filter | Type | Operators | Description |
| --- | --- | --- | --- |
| entity.entity | entity pk | eq,neq | Filter alerts related to specified entities. Example: `[{ “id”: “entity-id”, “saas”: 11161, “inst”: 0 }]` |
| entity.ip | string | eq, neq | Filter alerts related to specified IP addresses |
| entity.service | integer | eq, neq | Filter alerts related to the specified service appId, e.g: 11770 |
| entity.instance | integer | eq, neq | Filter alerts related to the specified instances, e.g: 11770, 1059065 |
| entity.policy | string | eq, neq | Filter alerts related to the specified policies |
| entity.file | string | eq, neq | Filter alerts related to specified file |
| severity | integer | eq, neq | Filter by severity. Possible values include:<br /><br />**0**: Low<br />**1**: Medium<br/>**2**: High |
| resolutionStatus | integer | eq, neq | Filter by alert resolution status, possible values include:<br /><br />**0**: Open<br />**1**: Dismissed<br />**2**: Resolved |
| read | boolean | eq | If set to “true”, returns only read alerts, if set to “false”, returns unread alerts |
| date | timestamp | lte, gte, range, lte_ndays, gte_ndays | Filter by the time when an alert was triggered |
| resolutionDate | timestamp | lte, gte, range | Filter by the time when an alert was resolved |
| risk | integer | eq, neq | Filter by risk |
| alertType | integer | eq, neq | Filter by alert type |
| ID | string | eq, neq | Filter by alert IDs |
| source | string | eq | The alert’s origin, either built-in or policy |

[!INCLUDE [Open support ticket](includes/support.md)]
