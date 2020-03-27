---
# required metadata
title: Cloud App Security Cloud Discovery API
description: This article provides information about using the Cloud Discovery API.
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
# Cloud Discovery API

*Applies to: Microsoft Cloud App Security*

Cloud Discovery parses system logs provided by the user to detect new and unknown applications in your cloud environment. Use the Cloud Discovery API to automate the uploading of your company's discovery log files. The file upload process consists of 3 API calls which must be called consecutively.

Additionally, Cloud App Security enables you to block access to unsanctioned apps by using your existing on-premises security appliances. Use the Generate block script call to get a dedicated block script and import it to your appliance.

The following is a list of discovery requests:

- **upload_url:** Initiate file upload
- **<initiate_file_upload_response_url>:** Perform file upload
- **done_upload:** Finalize file upload
- **discovery_block_scripts:** Generate block script

[!INCLUDE [Open support ticket](includes/support.md)]
