---
# required metadata
title: Fetch entity tree - Entities API
description: This article describes the fetch entity tree request in Cloud App Security's Entities API.
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
# Fetch entity tree - Entities API

*Applies to: Microsoft Cloud App Security*

Run the GET request to fetch all entities related to the entity matching the specified primary key. If the entity is a user, fetches all accounts associated with the user. If the entity is an account, fetches the entity's parent and siblings.

## HTTP request

```rest
GET /api/v1/entities/<pk>/retrieve_tree/
```

## Request URL parameters

| Parameter | Description |
| --- | --- |
| pk | The ID of the entity |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:<your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/entities/<pk>/retrieve_tree/"
```

### Response

Returns the specified entity tree in JSON format.

```json
{
  // entity tree record
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
