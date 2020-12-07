---
title: Update IP address range - Data Enrichment API
description: This article describes the update IP address range request in Cloud App Security's Data Enrichment API.
ms.date: 12/07/2020
ms.topic: reference
---
# Update IP address range - Data Enrichment API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the POST request to update an existing IP address range.

## HTTP request

```rest
POST /api/v1/subnet/<ip_range_id>/update_rule/
```

## Request BODY parameters

| Parameter | Description |
| --- | --- |
| category | The id of the range category |
| subnets | An array of masks as strings (IPv4 / IPv6) |
| organization (Optional) | The registered ISP |
| tags (Optional) | An array of tags (objects with "text" property set with the tag name) - new or existing |

The following categories are currently supported:

| Category | Id |
| --- | -- |
| Corporate | 1 |
| Administrative | 2 |
| Risky | 3 |
| VPN | 4 |
| Cloud provider | 5 |
| Other | 6 |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/subnet/<ip_range_id>/create_rule/" -d '{
  "name":"range name",
  "category":5,
  "organization":"Microsoft",
  "subnets":[
    "192.168.1.0/24",
    "192.168.2.0/16"
  ],
  "tags":[
    "existing tag"
  ]
}'
```

### Response

Returns the updated ip range in JSON format.

```json
  // ip range record
```

[!INCLUDE [Open support ticket](includes/support.md)]
