---
# required metadata

title: Connect Okta to Cloud App Security for visibility and control over use | Microsoft Docs
description: This topic provides information about how to connect your Okta to Cloud App Security using the API connector.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 9c3673b9-99bd-400c-9da1-5bf809ea5892


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Connect Okta to Microsoft Cloud App Security
This section provides instructions for connecting Cloud App Security to your existing Okta account using the connector APIs.  
  
## How to connect Okta to Cloud App Security  
  
1.  It is recommended that you create an admin Service Account in Okta for Cloud App Security.  
  
     Make sure you use an account with Super Admin permissions.  
  
     Make sure your Okta account is verified.  
  
2.  In the Okta console, click **Admin**.  
  
    -   Click on **Security** and then **API**.  
  
         ![okta api](./media/okta-api.png "okta api")  
  
    -   Click **Create Token**.  
  
         ![okta createtoken](./media/okta-createtoken.jpg "okta createtoken")  
  
    -   In the **Create Token** pop-up, name your Cloud App Security token and click **Create Token**.  
  
         ![okta token popup](./media/okta-token-popup.png "okta token popup")  
  
    -   In the **Token created successfully** pop-up, copy the **Token value**.  
  
         ![okta token value](./media/okta-token-value.png "okta token value")  
  
3.  In the Cloud App Security console, click **Investigate** and then **Connected apps**.  
  
4.  In the **App connectors page**, click the plus button and then **Okta**.  
  
     ![connect okta](./media/connect-okta.png "connect okta")  
  
5.  In the pop-up that opens, in the **Domain** field, enter your Okta domain and paste your Token into the **Token** field.  
  
6.  Click **Connect** to create the token for Okta in Cloud App Security.  
  
7.  Make sure the connection succeeded by clicking **Test API**.  
  
     Testing may take a couple of minutes. After receiving a success notice, click **Close**.  
  
After connecting Okta, you will receive events for 60 days prior to connection.
  
## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  