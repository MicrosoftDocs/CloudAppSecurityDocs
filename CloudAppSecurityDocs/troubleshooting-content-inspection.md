---
# required metadata

title: Troubleshooting content inspection errors in Cloud App Security | Microsoft Docs
description: This topic provides a list of content inspection statuses and their meanings.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 359eb77f-e719-4c50-9b62-6ef64149a5a5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshooting content inspection
|Content inspection status|Description|
|----|----|
|Completed|The content inspection completed successfully.|
|Not applicable|Content inspection was not applicable for this file. This might be because no policy requires content inspection of this file or because the file type is not supported.|
|Pending|The file is currently in the content inspection queue.|
|Failed: Download error|Cloud App Security could not download the file for inspection.|
|Failed: File is encrypted|The file could not be decrypted.|
|Failed: File is corrupted|The file is corrupted in some way and could not be inspected.|
|Failed: Internal error|Something undetermined went wrong when trying to inspect the file.|
|Failed: External DLP error|Something in your external DLP went wrong causing Cloud App Security to fail inspecting the content.|
|Failed: File size exceeded|The file limit varies depending on the file size and the number of characters.|
|Failed: File access denied|The file is external to your cloud and could not be accessed by Cloud App Security.|
|Failed: File was deleted|The file no longer exists in your cloud and could not be inspected.|
|Failed: Unsupported file type|Cloud App Security cannot perform content inspection on this file type. This may be because the file type is not supported or because the file is not actually the in the format of the expected file type.|

> [!NOTE]
> If you see a dash in the scan status, this means that the file is not queued to be scanned. See [File policies](data-protection-policies.md) for information on setting content inspection policies.

## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  