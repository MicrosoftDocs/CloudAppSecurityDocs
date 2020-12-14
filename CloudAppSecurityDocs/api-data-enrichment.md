---
title: Cloud App Security Data Enrichment API
description: This article provides information about using the Data Enrichment API.
ms.date: 12/13/2020
ms.topic: reference
---
# Data Enrichment API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

The Data Enrichment API enables you to create identifiable IP address ranges, such as your physical office IP addresses. IP address ranges allow you to tag, categorize, and customize the way logs and alerts are displayed and investigated. For more information, see [Working with IP ranges and tags](ip-tags.md).

The following lists the supported requests:

- [List IP address ranges](api-data-enrichment-list.md)
- [Create IP address range](api-data-enrichment-create.md)
- [Update IP address range](api-data-enrichment-update.md)
- [Delete IP address range](api-data-enrichment-delete.md)

## Filters

For information about how filters work, see [Filters](api-introduction.md#filters).

The following table describes the supported filters:

| Filter | Type | Operators | Description |
| --- | --- | --- | --- |
| category | integer | eq, neq | Filter IP ranges by category. Possible values include:<br /><br />**1**: Corporate<br />**2**: Administrative<br />**3**: Risky<br />**4**: VPN<br />**5**: Cloud provider<br />**6**: Other |
| name | string | eq, neq | Filter IP ranges by name |
| tags | string | eq, neq | Filter IP ranges by tag IDs |

[!INCLUDE [Open support ticket](includes/support.md)]
