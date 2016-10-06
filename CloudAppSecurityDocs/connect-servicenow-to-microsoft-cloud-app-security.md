---
title: "Connect ServiceNow to Microsoft Cloud App Security"
ms.custom: na
ms.date: "09/25/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
applies_to: 
  - "Microsoft Cloud App Security"
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
caps.latest.revision: 11
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
# Connect ServiceNow to Microsoft Cloud App Security
  This section provides instructions for connecting [!INCLUDE[Adallom](./includes/adallom_md.md)] to your existing ServiceNow account using the app connector API.  
  
## How to connect ServiceNow to Cloud App Security  
  
> [!NOTE]  
>  [!INCLUDE[Adallom](./includes/adallom_md.md)] supports ServiceNow versions of Eureka and Fiji. In order to connect ServiceNow with [!INCLUDE[Adallom](./includes/adallom_md.md)], you must have admin-level permissions and make sure the ServiceNow instance supports API access.  
  
1.  Log on with an Admin account to your ServiceNow account.  
  
2.  Create a new service account for [!INCLUDE[Adallom](./includes/adallom_md.md)] and attach the Admin role to the newly created account.  
  
3.  Make sure the REST API plug-in is turned on.  
  
     ![servicenow account](./media/servicenow-account.png "servicenow account")  
  
4.  In the [!INCLUDE[Adallom](./includes/adallom_md.md)] portal, click **Investigate** and then **Sanctioned apps**.  
  
5.  In the ServiceNow row, click **Connect** in the **App Connector status** column, or click the **Connect an app** button and then **ServiceNow**.  
  
     ![connect servicenow](./media/connect-servicenow.png "connect servicenow")  
  
6.  In the ServiceNow settings page, on the API tab, add your ServiceNow username, password and instance URL in the appropriate boxes.  
  
7.  Click **Connect**.  
  
     ![servicenow update password](./media/servicenow-update-password.png "servicenow update password")  
  
8.  Make sure the connection succeeded by clicking **Test API**.  
  
     Testing may take a couple of minutes. After receiving a success notice, click **Close**.  
  
  After connecting ServiceNow, you will receive events for 60 days prior to connection.
  
## See Also  
 [Control cloud apps with policies](../migration/control-cloud-apps-with-policies.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  