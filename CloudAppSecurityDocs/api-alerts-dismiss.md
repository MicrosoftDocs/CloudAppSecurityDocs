---
# required metadata
title: Dismiss - Alerts API
description: This article describes the dismiss request in Cloud App Security's Alerts API.
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
# Dismiss - Alerts API

*Applies to: Microsoft Cloud App Security*

Run the POST request to dismiss the alert matching the specified primary key.

## HTTP request

```rest
POST /api/v1/alerts/<pk>/dismiss/
```

## Request URL parameters

| Parameter | Description |
| --- | --- |
| pk | The ID of the alert |

## Request BODY parameters

| Parameter | Description |
| comment | A comment about why the alert was dismissed |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:<your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/alerts/<pk>/dismiss/" -d '{
  "comment": "Irrelevant"
}'
```

### Response

Not applicable.

[!INCLUDE [Open support ticket](includes/support.md)]
