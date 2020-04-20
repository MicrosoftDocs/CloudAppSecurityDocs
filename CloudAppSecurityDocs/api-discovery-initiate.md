---
# required metadata
title: Initiate file upload - Cloud Discovery API
description: This article describes the upload_url request in Cloud App Security's Cloud Discovery API.
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
# Initiate file upload - Cloud Discovery API

*Applies to: Microsoft Cloud App Security*

Run the GET request to initiate the upload process. This call, the first of the three, returns a URL that will later be used to perform the upload (PUT) request.

## HTTP request

```rest
GET /api/v1/discovery/upload_url/
```

## Request URL parameters

| Parameter | Description |
| --- |--- |
| filename | Name of the file you want to upload to Cloud Discovery processing |
| source | The type of Cloud Discovery log file being uploaded |

The following source types are currently supported:

- BARRACUDA
- BLUECOAT
- CHECKPOINT
- CHECKPOINT_SMART_VIEW_TRACKER
- CHECKPOINT_XML
- CISCO_ASA
- CISCO_ASA_FIREPOWER
- CISCO_FWSM
- CISCO_IRONPORT_PROXY
- CISCO_IRONPORT_WSA_II
- CISCO_SCAN_SAFE
- CLAVISTER
- FORCEPOINT
- FORCEPOINT_LEEF
- FORTIGATE
- GENERIC_CEF
- GENERIC_LEEF
- GENERIC_W3C
- I_FILTER
- IBOSS
- JUNIPER_SRX
- JUNIPER_SRX_SD
- JUNIPER_SRX_WELF
- JUNIPER_SSG
- MACHINE_ZONE_MERAKI
- MCAFEE_SWG
- MICROSOFT_ISA_W3C
- PALO_ALTO
- PALO_ALTO_LEEF
- SONICWALL_SYSLOG
- SOPHOS_CYBEROAM
- SOPHOS_SG
- SOPHOS_XG
- SQUID
- SQUID_NATIVE
- STORMSHIELD
- WEBSENSE_SIEM_CEF
- WEBSENSE_V7_5
- ZSCALER
- ZSCALER_CEF
- ZSCALER_QRADAR

> [!NOTE]
> If you can't find your file format, perform a manual upload using the portal.

## Response parameters

| Parameter | Description |
| --- | --- |
| url | The target URL that will perform your Cloud Discovery upload. |
| provider | Either "azure" or "aws", an indication whether the upload is target to Windows Azure Storage and AWS S3 storage. |

## Example

### Request

Here is an example of the request.

```rest
curl -XGET -H "Authorization:<your_token_key>" "https://<tenant_id>.<tenant_region>.contoso.com/api/v1/discovery/upload_url/?filename=my_discovery_file.txt&source=LOG_3COM"
```

### Response

Here is an example of the JSON response.

```json
{
  "url": "https://<initiate_file_upload_response_url>",
  "provider": "azure"
}
```

[!INCLUDE [Open support ticket](includes/support.md)]
