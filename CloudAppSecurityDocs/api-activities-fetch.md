---
title: Fetch - Activities API
description: This article describes the fetch request in Cloud App Security's Activities API.
ms.date: 03/27/2020
ms.topic: reference
---
# Fetch - Activities API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the GET request to fetch the activity matching the specified primary key.

## HTTP request

```rest
GET /api/v1/activities/<pk>/
```

## Request URL parameters

| Parameter | Description |
| --- | --- |
| pk | The ID of the activity |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/activities/<pk>/"
```

### Response

Returns the specified activity in JSON format.

```json
{
  // activity record
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
