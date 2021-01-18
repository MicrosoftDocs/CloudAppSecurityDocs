---
title: List app tags - Cloud Discovery API
description: This article describes the list app tags request in Cloud App Security's Cloud Discovery API.
ms.date: 01/07/2021
ms.topic: reference
---
# List app tags - Cloud Discovery API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the POST request to fetch a list of app tags associated with a stream.

## HTTP request

```rest
POST api/v1/discovery/app_tags/
```

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/discovery/app_tags/"
```

### Response

Returns a list of app tags in JSON format.

```json
[
  {
    "name": "test",
    "target": 6,
    "id":"test",
    "_tid":39661153,
    "appIds": [11161,11522]
  }
]
```

The response object defines the following properties. Properties marked as *optional* may not appear for some streams.

| Field name | Field type | Field description |
|--|--|--|
| id (*optional*) | string | The id of the tag |
| name | string | The name of the tag |
| appIds | list | An array of apps id where the tag is applied |
| builtIn (*optional*) | boolean | **true** is the tag is built-in |

[!INCLUDE [Open support ticket](includes/support.md)]
