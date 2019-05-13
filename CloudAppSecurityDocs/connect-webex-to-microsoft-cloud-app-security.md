---
# required metadata

title: Connect WebEx to Cloud App Security
description: This article provides information about how to connect your WebEx app to Cloud App Security using the API connector  for visibility and control over use.
keywords:
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 04/16/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: c43271fd-9a61-4727-9945-de1c6ea5422c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Connect Cisco WebEx to Microsoft Cloud App Security

*Applies to: Microsoft Cloud App Security*

This article provides instructions for connecting Microsoft Cloud App Security to your existing Cisco WebEx account using the connector APIs. This connection gives you visibility into and control over WebEx users, activities, and files. 
 
## Prerequisites

- We suggest that you create a dedicated service account for the connection. This enables you to see that governance actions performed in WebEx as being performed from this account, such as delete messages sent in WebEx. Otherwise, the name of the admin who connected Cloud App Security to WebEx will appear as the user who performed the actions.  
- You must have Full administrator **and** Compliance administrator permissions in WebEx.


## How to connect WebEx to Cloud App Security  
  
1.  In the Cloud App Security console, click **Investigate** and then **Connected apps**.  
  
2.  In the **App connectors** page, click the plus button followed by **Cisco WebEx**.  
  
     ![connect WebEx](./media/cisco-webex.png "connect WebEx")  
  
3.  In the pop-up, enter the instance name of this connector.  
  
4.  Click **Connect Cisco Webex**. The WebEx sign in page opens. Enter your credentials to allow Cloud App Security access to your team's WebEx instance.  
  
6.  WebEx asks you if you want to allow Cloud App Security access to your team information, activity log, and perform activities as a team member. To proceed, click **Allow**.  
  
7.  Back in the Cloud App Security console, you should receive a message that WebEx was successfully connected.  
  
8.  Make sure the connection succeeded by clicking **Test API**.  
  
     Testing may take a couple of minutes. After you receive a success notice, click **Close**.  
  
After connecting WebEx, you'll receive events for 7 days prior to connection. Cloud App Security scans events over the past three months. To increase this, you must have a Cisco WebEx pro license and open a ticket with Cloud App Security support.

 
## Next steps 
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
