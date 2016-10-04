---
title: "Connect Okta to Microsoft Cloud App Security"
ms.custom: na
ms.date: "09/25/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
applies_to: 
  - "Microsoft Cloud App Security"
ms.assetid: 34437ad1-5298-43c7-b32b-1fd6d3d8b5bb
caps.latest.revision: 8
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
# Connect Okta to Microsoft Cloud App Security
  This section provides instructions for connecting [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] to your existing Okta account using the connector APIs.  
  
## How to connect Okta to Cloud App Security  
  
1.  It is recommended that you create an admin Service Account in Okta for [!INCLUDE[Adallom](../migration/includes/adallom_md.md)].  
  
     Make sure you use an account with Super Admin permissions.  
  
     Make sure your Okta account is verified.  
  
2.  In the Okta console, click **Admin**.  
  
    -   Click on **Security** and then **API**.  
  
         ![okta api](../migration/media/okta-api.png "okta api")  
  
    -   Click **Create Token**.  
  
         ![okta createtoken](../migration/media/okta-createtoken.jpg "okta createtoken")  
  
    -   In the **Create Token** popup, name your [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] token and click **Create Token**.  
  
         ![okta token popup](../migration/media/okta-token-popup.png "okta token popup")  
  
    -   In the **Token created successfully popup**, copy the **Token value**.  
  
         ![okta token value](../migration/media/okta-token-value.png "okta token value")  
  
3.  In the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] console, click **Investigate** and then **Sanctioned apps**.  
  
4.  In the Okta row, click **Connect** in the **App Connector status** column, or click the **Connect an app** button and then **Okta**.  
  
     ![connect okta](../migration/media/connect-okta.png "connect okta")  
  
5.  In the API page, in the **Domain** field, enter your Okta domain and paste your Token into the **Token** field.  
  
6.  Click **Connect** to create the token for Okta in [!INCLUDE[Adallom](../migration/includes/adallom_md.md)].  
  
7.  Make sure the connection succeeded by clicking **Test API**.  
  
     Testing may take a couple of minutes. After receiving a success notice, click **Close**.  
  
  After connecting Okta, you will receive events for 60 days prior to connection.
  
## See Also  
 [Control cloud apps with policies](../migration/control-cloud-apps-with-policies.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  