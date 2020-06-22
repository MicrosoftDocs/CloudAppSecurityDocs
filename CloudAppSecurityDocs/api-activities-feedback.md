---
# required metadata
title: Feedback - Activities API
description: This article describes the feedback request in Cloud App Security's Activities API.
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
# Feedback on activity - Activities API

*Applies to: Microsoft Cloud App Security*

Run the POST request to send feedback about the activity matching the specified primary key.

## HTTP request

```rest
POST /api/v1/activities/<pk>/feedback
```

## Request URL parameters

| Parameter | Description |
| --- | --- |
| pk | The ID of the activity |

## Request BODY parameters

| Parameter | Description |
| --- | --- |
| feedback | The feedback for the activity |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:<your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/activities/<pk>/feedback" -d '{
  "feedbackValue": "0",
  "feedbackText": "Irrelevant",
  "allowContact": false,
  "contactEmail": "some.contact.address"
}'
```

### Response

Returns a list of activities in JSON format.

```json
{
  "total": 5 // total number of records
  "hasNext": true // whether there is more data to show or not.
  "data": [
    // returned records
  ]
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
