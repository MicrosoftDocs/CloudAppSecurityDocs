---
title: List stream categories - Cloud Discovery API
description: This article describes the list stream categories request in Cloud App Security's Cloud Discovery API.
ms.date: 01/07/2021
ms.topic: reference
---
# List stream categories - Cloud Discovery API

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Run the POST request to fetch a list of categories associated with a stream.

## HTTP request

```rest
POST api/v1/discovery/discovered_apps/categories/
```

## Request BODY parameters

| Parameter | Description |
| --- | --- |
| filters (*optional*) | Filter objects with all the search filters for the request by category id |
| sortDirection (*optional*) | The sorting direction. Possible values are: `asc` and `desc` |
| sortField (*optional*) | Fields used to sort entities. Possible values are:<br />- **date**: The date when then the category happened<br />- **created**: The date when then the category was created |
| skip (*optional*) | Skips the specified number of records |
| limit (*optional*) | Maximum number of records returned by the request |
| streamId | Filter records by stream ID |
| timeFrame (*optional*) | Filter records by the number of days since the stream was last used |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:Token <your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/discovery/discovered_apps/categories/" -d '{
  "filters": {
    // some filters
  },
  "skip": 5,
  "limit": 10,
  "streamId": 
}'
```

### Response

Returns a list of app tags in JSON format.

```json
[
  {
    "id": "SAASDB_CATEGORY_PRODUCT_DESIGN",
    "total": 2
  },
  {
    "id": "SAASDB_CATEGORY_SUPLLY_CHAIN_AND_LOGISTICS",
    "total": 1
  }
]
```

The response object defines the following properties. Properties marked as *optional* may not appear for some streams.

| Field name | Field type | Field description |
|--|--|--|
| id | string | The id of the category |
| total | int | The total number of services in the category |

[!INCLUDE [Open support ticket](includes/support.md)]
