---
# required metadata

title: Connect Dropbox to Microsoft Cloud App Security | Microsoft Docs
description:
keywords:
author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 4acd93f4-b885-4e1f-a385-43b5db02a3ee

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Connect Dropbox to Microsoft Cloud App Security
  This section provides instructions for connecting Cloud App Security to your existing Dropbox account using the connector APIs.  
 
 
Because Dropbox enables access to files from shared links without signing in, Cloud App Security registers these users as Unauthenticated users. If you see unauthenticated Dropbox users, it may indicate users who are not from your organization, or they might be recognized users from within your organization who did not sign in.

## How to connect Dropbox to Cloud App Security  
  
1.  In the Cloud App Security console, click **Investigate** and then **Sanctioned apps**.  
  
2.  In the Dropbox row, click **Connect** in the **App Connector status** column, or click the **Connect an app** button followed by **Dropbox**.  
  
     ![connect dropbox](./media/connect-dropbox.png "connect dropbox")  
  
3.  In the Dropbox settings page, on the API tab, enter the admin account email address.  
  
4.  Click **Generate link**.  
  
5.  Click **Follow this link**.  
  
     This opens the Dropbox logon page. Enter your credentials to allow Cloud App Security access to your team's Dropbox instance.  
  
6.  Dropbox will ask you if you want to allow Cloud App Security access to your team information and activity log and perform any activity as any team member. To proceed, click **Allow**.  
  
7.  Back in the Cloud App Security console, you should receive a message that Dropbox was successfully connected.  
  
8.  Make sure the connection succeeded by clicking **Test API**.  
  
     Testing may take a couple of minutes. After receiving a success notice, click **Close**.  
  
  After connecting Dropbox, you will receive events for 60 days prior to connection.

> [!NOTE] 
Any Dropbox events for adding a file will be displayed in Cloud App Security as Upload file to align to all other apps connected to Cloud App Security. 
 
## See Also  
 [Control cloud apps with policies](control-cloud-apps-with-policies.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  