---
# required metadata
title: Perform file upload - Cloud Discovery API
description: This article describes the perform file upload request in Cloud App Security's Cloud Discovery API.
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
# Perform file upload - Cloud Discovery API

*Applies to: Microsoft Cloud App Security*

Upload the file contents by performing an HTTP PUT request. You will be required to use the URL returned by the [Initiate file upload](api-discovery-initiate.md) request.

Azure and AWS have different headers and limitations when uploading files to the target URL.

> [!NOTE]
>
> - You can upload individual files of up to 5 GB. If you need to upload larger files, break the Cloud Discovery data into multiple chunks.
> - If you do not know which environment you are running, check the [Initiate file upload](api-discovery-initiate.md) request, which returns this information.

## HTTP request

```rest
PUT https://<initiate_file_upload_response_url>
```

> [!NOTE]
>
> For Azure:
> - If your file is under 64 MB, add the header "x-ms-blob-type: BlockBlob" to your request.
> - If your file size is greater than 64MB, upload it in chunks. the easiest way to do this is using the [Azure SDK](https://azure.microsoft.com/downloads/).

## Example

### Request

Here is an example of the request for Azure.

```rest
curl --request PUT --upload-file <file_to_upload> "https://<initiate_file_upload_response_url>" -H "x-ms-blob-type: BlockBlob"
```

Here is an example of the request for Azure Java SDK.

```java
File fileReference = new File("file.name");
// Create a blob using the URI that contains the shared access signature.
CloudBlockBlob sasBlob = new CloudBlockBlob(uri);

// Upload the file to the blob.
sasBlob.upload(new FileInputStream(fileReference), fileReference.length());
```

### Response

Not applicable.

[!INCLUDE [Open support ticket](includes/support.md)]
