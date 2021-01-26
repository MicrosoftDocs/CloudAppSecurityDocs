---
title: Delete app tag - Cloud Discovery API
description: This article describes the delete app tag request in Cloud App Security's Cloud Discovery API.
ms.date: 01/07/2021
ms.topic: reference
---
# Delete app tag - Cloud Discovery API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the POST request to delete an app tag.

## HTTP request

```rest
POST api/v1/discovery/discovery_app/{service}/remove_tag/
```

## Request BODY parameters

| Parameter | Description |
| --- | --- |
| tagName | The unique name of the tag |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/discovery/discovery_app/<service>}/remove_tag/" -d {
  "tagName": <tag name>
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
