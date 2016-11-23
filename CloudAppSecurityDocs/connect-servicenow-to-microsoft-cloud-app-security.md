---
# required metadata

title: Connect ServiceNow to Microsoft Cloud App Security | Microsoft Docs
description: This topic provides information about how to connect your ServiceNow app to Cloud App Security using the API connector.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Connect ServiceNow to Microsoft Cloud App Security
This section provides instructions for connecting Cloud App Security to your existing ServiceNow account using the app connector API.  
  
## How to connect ServiceNow to Cloud App Security  
  
> [!NOTE]  
>  Cloud App Security supports ServiceNow versions of Eureka and Fiji. In order to connect ServiceNow with Cloud App Security, you must have admin-level permissions and make sure the ServiceNow instance supports API access.  
  
1.  Log on with an Admin account to your ServiceNow account.  
  
2.  Create a new service account for Cloud App Security and attach the Admin role to the newly created account.  
  
3.  Make sure the REST API plug-in is turned on.  
  
     ![servicenow account](./media/servicenow-account.png "servicenow account")  
  
4.  In the Cloud App Security portal, click **Investigate** and then **Connected apps**.  
  
5.  In the **App connectors** page, click the **Connect an app** button and then **ServiceNow**.  
  
     ![connect servicenow](./media/connect-servicenow.png "connect servicenow")  
  
6.  In the popup, add your ServiceNow username, password and instance URL in the appropriate boxes.  
  
7.  Click **Connect**.  
  
     ![servicenow update password](./media/servicenow-update-password.png "servicenow update password")  
  
8.  Make sure the connection succeeded by clicking **Test API**.  
  
     Testing may take a couple of minutes. After receiving a success notice, click **Close**.  
  
After connecting ServiceNow, you will receive events for 60 days prior to connection.
  
## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  