---
# required metadata

title: Modifying the ftp password for the Cloud Discovery docker | Microsoft Docs
description: This topic describes the process for modifying the Cloud Discovery ftp password.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 26/11/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 776e834f-3c20-4d5f-9fab-4c5b975edb06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Changing the FTP password


1. Connect to the log collector host.

2.	Run `docker exec -it <collector name> pure-pw passwd <ftp user>`

    1. Enter the new password.
    2. Enter the new password again for confirmation.
 
3.	Run `docker exec -it <collector name> pure-pw mkdb` to apply the change.


  ![change ftp password](./media/ftp-connect.png)

## See Also
[Working with Cloud Discovery
data](working-with-cloud-discovery-data.md)  
[For technical support, please visit the Cloud App Security assisted support
page](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier customers can also choose Cloud App Security directly from the Premier
Portal](https://premier.microsoft.com/)

