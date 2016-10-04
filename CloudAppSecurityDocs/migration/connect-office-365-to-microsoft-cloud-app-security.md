---
title: "Connect Office 365 to Microsoft Cloud App Security"
ms.custom: na
ms.date: "09/25/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
applies_to: 
  - "Microsoft Cloud App Security"
ms.assetid: 90340934-e883-444c-b953-e57a8b88a385
caps.latest.revision: 21
author: "Rkarlin"
ms.author: "rkarlin"
robots: noindex,nofollow
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "hu-hu"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "nl-nl"
  - "pl-pl"
  - "pt-br"
  - "pt-pt"
  - "ru-ru"
  - "sv-se"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Connect Office 365 to Microsoft Cloud App Security
  This section provides instructions for connecting [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] to your existing Microsoft Office 365 account using the app connector API.  
  
  

## How to connect Office 365 to Cloud App Security  
  
> [!NOTE]
>- You must have at least one assigned Office 365 license to connect Office 365 to Cloud App Security.
>-  Exchange administrator audit logging, which is enabled by default in Office 365, logs an event in the Office 365 audit log when an administrator (or a user who has been assigned administrative privileges) makes a change in your Exchange Online organization. Changes made using the Exchange admin center or by running a cmdlet in Windows PowerShell are logged in the Exchange admin audit log. For more detailed information about admin audit logging in Exchange, see [Administrator audit logging](http://go.microsoft.com/fwlink/p/?LinkID=619225).
>- If Office apps are enabled, groups that are part of Office 365 are also created in the specific Office apps, for example if SharePoint is enabled, Office 365 groups will be created in SharePoint.
 
1.  In the Office 365 row, click **Connect** in the **App Connector status** column, or, click the **Connect an App** button and select **Office 365**.  

2.  In the Office 365 pop-up, click Connect Office 365.

      ![connect 0365](../migration/media/connect-0365.png) 
 
3.  Click Test now to test the connection to Office 365. Testing may take a couple of minutes.
  
    ![O365 test connection](../migration/media/o365-test-connection.png) 
 
4.   After Office 365 is displayed as successfully connected, click **Close**.
  
     ![O365 connected](../migration/media/o365-connected.png) 

 >[!NOTE] After connecting Office 365, you will see data from a week back including any third-party applications connected to Office 365 that are pulling APIs. For third-party apps that weren't pulling APIs prior to connection, you will see events from the moment you connect Office 365, because Cloud App Security turns on any APIs that had been off by default.

## See Also  
 [Control cloud apps with policies](../migration/control-cloud-apps-with-policies.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  