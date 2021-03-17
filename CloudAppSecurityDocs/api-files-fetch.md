---
title: Fetch - Files API
description: This article describes the fetch request in Cloud App Security's Files API.
ms.date: 03/27/2020
ms.topic: reference
---
# Fetch - Files API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

> [!NOTE]
>
> - This API will soon be deprecated. Microsoft Cloud App Security is developing a new solution for identifying and acting upon files that violate policies.
> - This API is not available for Office 365 Cloud App Security.

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
curl -XPOST -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/files/<pk>/"
```

### Response

Returns the specified file.

[!INCLUDE [Open support ticket](includes/support.md)]
