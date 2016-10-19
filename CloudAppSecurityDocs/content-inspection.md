---
# required metadata

title: Content Inspection | Microsoft Docs
description: his article describes the process Cloud App Security follows when performing DLP content inspection on data in your cloud. 
keywords:
author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 2401adbc-0011-4938-9e3a-a4c719a2f619

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Content Inspection
This article describes the process Cloud App Security follows when performing DLP content inspection on data in your cloud. 


Cloud App Security content inspection works as follows:
1. Cloud App Security performs a continuous scan of all relevant files in all drives. 
2. Cloud App Security performs Near Real-Time (NRT) scan of drives and events that are detected to be new or changed. 

Both the files in the continuous scan and the files in the NRT scan are added to the queue for inspection. The order of the files in the scan queue is set per activity on files and on the scan of your drives. Files are scanned only if the file metadata shows that it's a supported MIME type. That this scan is for files that are relevant for data scan (documents, images, presentations, spreadsheets, text and zip/archive files).  

After a file is scanned, the following occurs:

1. Cloud App Security applies all your custom policies that relate to metadata and not to the content itself. For example, a policy that alerts you when files are more than 20 MB or a policy that alerts you when docx files are saved to OneDrive. 

2. If there is a policy that requires content inspection, and the file qualifies for content inspection, the content is queued for inspection. The queue length depends on the size of the tenant and the number of files that require scan. 

3. At this point, you can view the status of the content inspection by going to **Investigate** > **Files** and clicking on a file. In the file drawer that opens with the details of the file, the **Content Inspection status** will display one of the following: 

|Content inspection status|Description|
|----|----|
|Completed|The content inspection completed successfully.|
|Not applicable|Content inspection was not applicable for this file. This can be because no policy requires content inspection of this file or because the file type is not supported.|
|Pending|The file is currently in the content inspection queue.|
|Failed: Download error|Cloud App Security could not download the file for inspection.|
|Failed: File is encrypted|The file could not be decrypted.|
|Failed: File is corrupted|The file is corrupted in some way and could not be inspected.|
|Failed: Internal error|Something undetermined went wrong when trying to inspect the file.|
|Failed: External DLP error|Something in your external DLP went wrong causing Cloud App Security to fail inspecting the content.|
|Failed: File size exceeded|The file limit varies depending on the file size and number of characters.|
|Failed: File access denied|The file is external to your cloud and could not be accessed by Cloud App Security.|
|Failed: File was deleted|The file no longer exists in your cloud and could not be inspected.|
|Failed: Unsupported file type|Cloud App Security cannot perform content inspection on this file type. This may be because the file type is not supported or because the file is not actually the in the format of the expected file type.|

## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  