---
# required metadata
title: Bulk resolve - Alerts API
description: This article describes the bulk resolve request in Cloud App Security's Alerts API.
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
# Bulk resolve - Alerts API

*Applies to: Microsoft Cloud App Security*

Run the POST request to resolve multiple alerts matching the specified filters.

## HTTP request

```rest
POST /api/v1/alerts/resolve/
```

## Request BODY parameters

| Parameter | Description |
| --- | --- |
| filters | Filter objects with all the search filters for the request, see [alert filters](api-alerts.md#filters) for more details |
| comment | A comment about why the alerts are resolved |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:<your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/alerts/resolve" -d '{
  "comment": "Irrelevant",
  "filters": {
    "id": {
      "eq": [
        "55af7415f8a0a7a29eef2e1f",
        "55af741cf8a0a7a29eef2e20"
      ]
    }
  }
}'
```

### Response

Not applicable.

[!INCLUDE [Open support ticket](includes/support.md)]
