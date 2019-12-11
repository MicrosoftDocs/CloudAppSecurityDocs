---
# required metadata

title: Troubleshooting content inspection errors - Cloud App Security | Microsoft Docs
description: This article provides a list of content inspection statuses and their meanings.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Troubleshooting content inspection

*Applies to: Microsoft Cloud App Security*

This article provides a list of content inspection statuses and their meanings.

## Content inspection status

The table lists each content inspection status and its description.

|Content inspection status|Description|
|----|----|
|Completed|The content inspection completed successfully.|
|Not applicable|Content inspection wasn't applicable for this file. This status might appear because no policy requires content inspection of this file or because the file type isn't supported.|
|Pending|The file is currently in the content inspection queue.|
|Failed: Download error|Microsoft Cloud App Security couldn't download the file for inspection.|
|Failed: File is encrypted|The file couldn't be decrypted.|
|Failed: File is corrupted|The file is corrupted in some way and couldn't be inspected.|
|Failed: Internal error|Something undetermined went wrong when trying to inspect the file.|
|Failed: External DLP error|Something in your external DLP went wrong causing Cloud App Security to fail inspecting the content.|
|Failed: File size exceeded|The file limit varies depending on the file size and the number of characters.|
|Failed: File access denied|The file is external to your cloud and couldn't be accessed by Cloud App Security.|
|Failed: File was deleted|The file no longer exists in your cloud and couldn't be inspected.|
|Failed: Unsupported file type|Cloud App Security can't perform content inspection on this file type. This status may appear because the file type isn't supported or because the file isn't actually in the format of the expected file type.|

> [!NOTE]
> If you see a dash in the scan status, this means that the file is not queued to be scanned. See [File policies](data-protection-policies.md) for information on setting content inspection policies.

## Next steps

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[!INCLUDE [Open support ticket](includes/support.md)]
