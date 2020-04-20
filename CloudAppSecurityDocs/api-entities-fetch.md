---
# required metadata
title: Fetch - Entities API
description: This article describes the fetch request in Cloud App Security's Entities API.
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
# Fetch - Entities API

*Applies to: Microsoft Cloud App Security*

Run the GET request to fetch the entity matching the specified primary key.

## HTTP request

```rest
GET /api/v1/entities/<pk>/
```

## Request URL parameters

| Parameter | Description |
| --- | --- |
| pk | The ID of the entity |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:<your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/entities/<pk>/"
```

### Response

Returns the specified entity in JSON format.

```json
{
  // entity record
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
