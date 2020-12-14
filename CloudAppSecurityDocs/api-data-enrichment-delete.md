---
title: Delete IP address range - Data Enrichment API
description: This article describes the delete IP address range request in Cloud App Security's Data Enrichment API.
ms.date: 12/13/2020
ms.topic: reference
---
# Delete IP address range - Data Enrichment API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the DELETE request to delete an IP address range.

## HTTP request

```rest
DELETE /api/v1/subnet/<ip_range_id>/
```

## Example

### Request

Here is an example of the request.

```rest
curl -X DELETE -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/subnet/<ip_range_id>/"
```

[!INCLUDE [Open support ticket](includes/support.md)]
