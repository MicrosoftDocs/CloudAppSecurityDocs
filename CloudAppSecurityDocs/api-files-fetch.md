---
# required metadata
title: Fetch - Files API
description: This article describes the fetch request in Cloud App Security's Files API.
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
# Fetch - Files API

*Applies to: Microsoft Cloud App Security*

Run the GET request to fetch the file matching the specified primary key.

## HTTP request

```rest
GET /api/v1/files/<pk>/
```

## Request URL parameters

| Parameter | Description |
| --- | --- |
| pk | The ID of the file |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:<your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/files/<pk>/"
```

### Response

Returns the specified file.

[!INCLUDE [Open support ticket](includes/support.md)]
