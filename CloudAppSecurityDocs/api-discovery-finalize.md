---
# required metadata
title: Finalize file upload - Cloud Discovery API
description: This article describes the done_upload request in Cloud App Security's Cloud Discovery API.
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
# Finalize file upload - Cloud Discovery API

*Applies to: Microsoft Cloud App Security*

After the file content upload successfully completes, notify us in order to begin the processing of the file.

## HTTP request

```rest
POST /api/v1/discovery/done_upload/
```

## Request BODY parameters

| Parameter | Description |
| --- | --- |
| uploadUrl | The URL that was returned in the initial call requesting file upload. |
| inputStreamName | The name of the data source from which data is coming in (represents the device). |
| uploadAsSnapshot | Upload the data as a snapshot report instead of uploading to a continuous report. If this parameter is set, then the report will be created with the name specified in inputStreamName. |

## Example

### Request

Here is an example of the request.

```rest
curl -XPOST -H "Authorization:<your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/discovery/done_upload/" -d "uploadUrl=<initiate_file_upload_response_url>"
```

### Response

Not applicable.

[!INCLUDE [Open support ticket](includes/support.md)]
