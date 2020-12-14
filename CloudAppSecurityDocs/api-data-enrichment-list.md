---
title: List - Data Enrichment API
description: This article describes the list request in Cloud App Security's Data Enrichment API.
ms.date: 12/13/2020
ms.topic: reference
---
# List - Data Enrichment API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the GET or POST request to fetch a list of IP ranges matching the specified filters.

## HTTP request

```rest
GET /api/v1/subnet/
```

```rest
POST /api/v1/subnet/
```

## Request BODY parameters

| Parameter | Description |
| --- | --- |
| filters | Filter objects with all the search filters for the request, see [IP range filters](api-data-enrichment.md#filters) for more details |
| sortDirection | The sorting direction. Possible values are: `asc` and `desc` |
| sortField | Fields used to sort IP ranges. Possible values are:<br /><br />**date**: The date when then the IP range was created |
| skip | Skips the specified number of records |
| limit | Maximum number of records returned by the request |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/subnet/" -d '{
  "filters": {
    // some filters
  },
  "skip": 5,
  "limit": 10
  ...
}'
```

### Response

Returns a list of IP ranges in JSON format.

```json
{
  "total": 5 // total number of records
  "hasNext": false // whether there is more data to show or not.
  "data": [
    // returned records
  ]
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
