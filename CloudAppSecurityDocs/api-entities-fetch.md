---
title: Fetch - Entities API
description: This article describes the fetch request in the Defender for Cloud Apps Entities API.
ms.date: 01/29/2023
ms.topic: reference
---
# Fetch - Entities API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

> [!NOTE]
> This request is not available for Microsoft 365 Cloud App Security.

Run the GET request to fetch the entity matching the specified primary key.

## HTTP request

```rest
GET /api/v1/entities/<pk>/
```

## Request URL parameters

| Parameter | Description |
| --- | --- |
| pk | A dictionary with the entity ID, SaaS, and instance details encoded as a base64 string. For example: `{"id":"3fa9f28b-eb0e-463a-ba7b-8089fe9991e2","saas":11161,"inst":0}` encoded as a base64 string. |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/entities/<pk>/"
```

### Response

Returns the specified entity in JSON format.

```json
{
  // entity record
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
