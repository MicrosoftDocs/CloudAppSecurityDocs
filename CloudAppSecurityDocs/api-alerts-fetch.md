---
title: Fetch - Alerts API
description: This article describes the fetch request in Cloud App Security's Alerts API.
ms.date: 03/27/2020
ms.topic: reference
---
# Fetch - Alerts API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the GET request to fetch the alert matching the specified primary key.

## HTTP request

```rest
GET /api/v1/alerts/<pk>/
```

## Request URL parameters

| Parameter | Description |
| --- | --- |
| pk | The ID of the alert |

## Example

### Request

Here is an example of the request.

```rest
curl -XGET -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/alerts/<pk>/"
```

### Response

Returns the specified alert in JSON format.

```json
{
  // alert record
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
