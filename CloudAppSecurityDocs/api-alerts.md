---
title: Cloud App Security Alerts API
description: This article provides information about using the Alerts API.
ms.date: 10/20/2020
ms.topic: reference
---
# Alerts API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

The Alerts API provides you with information about immediate risks identified by Cloud App Security and require attention. Alerts can result from suspicious usage patterns or from files containing content that violates company policy.

The following lists the supported requests:

- [List alerts](api-alerts-list.md)
- [Close benign](api-alerts-close-benign.md)
- [Close false positive](api-alerts-close-false-positive.md)
- [Close true positive](api-alerts-close-true-positive.md)
- [Fetch alert](api-alerts-fetch.md)
- [Mark alert as read](api-alerts-mark-read.md)
- [Mark alert as unread](api-alerts-mark-unread.md)

## Deprecated requests

The following table lists the requests deprecated as obsolete, and the requests that replace them.

| Obsolete request | Alternative |
| --- | --- |
| Bulk dismiss | [Close false positive](api-alerts-close-false-positive.md) |
| Bulk resolve | [Close true positive](api-alerts-close-true-positive.md) |
| Dismiss alert | [Close false positive](api-alerts-close-false-positive.md) |

> [!NOTE]
> The deprecated requests have been mapped to their alternatives to avoid disruption. However, if you are using obsolete requests in your environment, we recommend updating them to their alternatives.

## Filters

For information about how filters work, see [Filters](api-introduction.md#filters).

The following table describes the supported filters:

| Filter | Type | Operators | Description |
| --- | --- | --- | --- |
| entity.entity | entity pk | eq,neq | Filter alerts related to specified entities. Example: `[{ "id": "entity-id", "saas": 11161, "inst": 0 }]` |
| entity.ip | string | eq, neq | Filter alerts related to specified IP addresses |
| entity.service | integer | eq, neq | Filter alerts related to the specified service appId, e.g: 11770 |
| entity.instance | integer | eq, neq | Filter alerts related to the specified instances, e.g: 11770, 1059065 |
| entity.policy | string | eq, neq | Filter alerts related to the specified policies |
| entity.file | string | eq, neq | Filter alerts related to specified file |
| alertOpen | boolean | eq | If set to "true", returns only open alerts, if set to "false", returns only closed alerts |
| severity | integer | eq, neq | Filter by severity. Possible values include:<br /><br />**0**: Low<br />**1**: Medium<br/>**2**: High |
| resolutionStatus | integer | eq, neq | Filter by alert resolution status, possible values include:<br /><br />**0**: Open <br />**1**: Dismissed (legacy status)<br />**2**: Resolved (legacy status)<br />**3**: Closed as false positive<br />**4**: Closed as benign<br />**5**: Closed as true positive |
| read | boolean | eq | If set to "true", returns only read alerts, if set to "false", returns unread alerts |
| date | timestamp | lte, gte, range, lte_ndays, gte_ndays | Filter by the time when an alert was triggered |
| resolutionDate | timestamp | lte, gte, range | Filter by the time when an alert was resolved |
| risk | integer | eq, neq | Filter by risk |
| alertType | integer | eq, neq | Filter by alert type |
| ID | string | eq, neq | Filter by alert IDs |
| source | string | eq | The alert's origin, either built-in or policy |

[!INCLUDE [Open support ticket](includes/support.md)]
