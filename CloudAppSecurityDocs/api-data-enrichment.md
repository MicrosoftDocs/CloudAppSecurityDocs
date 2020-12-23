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

## Properties

The response object defines the following properties.

| Property | Type | Description |
| --- | --- | --- |
| name | string | The unique name of the range |
| category | int | The id of the range category. Providing a category helps you easily recognize activities from interesting IP addresses. Possible values include:<br /><br />**1**: Corporate<br />**2**: Administrative<br />**3**: Risky<br />**4**: VPN<br />**5**: Cloud provider<br />**6**: Other |
| subnets | list | An array of masks as strings (IPv4 / IPv6) |
| organization | string | The registered ISP |
| tags| list(json) | An array of tags (objects with "text" property set with the tag name) - new or existing |

| data | list | List of the existing records according to filters chosen. |
| _id | string | ip range unique id |
| name | string | ip range unique name |
| subnets | list | contains mask, address and originalString. |
| mask | int | subnet mask value |
| address | string | subnet address ipv6 |
| originalString | string | subnet value |
| location name | string | original location value |
| latitude | long | location latitude (decimal) |
| longitude | long | location longitude (decimal) |
| countryCode | string | country code (two digit) |
| countryName | string | country full name |
| organization | string | organization name |
| tags | list(json) | IP address tags list, including tag data |
| _id | string | db id of tag |
| id | string | tag unique identifier |
| name | string | tag name |
| nameTemplate | string | tag template name |
| description | string | tag description |
| _tid | int | tenant id |
| lastModified | long | timestamp of the last time the rule changed. |
| hasNext | bool | is there any additional records? |
| total | int | total record amount. |


// List or array
// _id duplicated with diff desc
// subnets diff desc
// organization diff desc
// tags diff desc

## Filters

For information about how filters work, see [Filters](api-introduction.md#filters).

The following table describes the supported filters:

| Filter | Type | Operators | Description |
| --- | --- | --- | --- |
| category | integer | eq, neq | Filter IP ranges by category. Possible values include:<br /><br />**1**: Corporate<br />**2**: Administrative<br />**3**: Risky<br />**4**: VPN<br />**5**: Cloud provider<br />**6**: Other |
| name | string | eq, neq | Filter IP ranges by name |
| tags | string | eq, neq | Filter IP ranges by tag IDs |

[!INCLUDE [Open support ticket](includes/support.md)]
