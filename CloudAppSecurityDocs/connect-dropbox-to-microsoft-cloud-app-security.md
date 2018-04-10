---
# required metadata

title: Connect Dropbox to Cloud App Security for visibility and control over use | Microsoft Docs
description: This topic provides information about how to connect your Dropbox app to Cloud App Security using the API connector.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
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
  
1.  In the Cloud App Security console, click **Investigate** and then **Connected apps**.  
  
2.  In the **App connectors** page, click the plus button followed by **Dropbox**.  
  
     ![connect dropbox](./media/connect-dropbox.png "connect dropbox")  
  
3.  In the pop-up, enter the admin account email address.  
  
4.  Click **Generate link**.  
  
5.  Click **Follow this link**.  
  
     The Dropbox log on page opens. Enter your credentials to allow Cloud App Security access to your team's Dropbox instance.  
  
6.  Dropbox asks you if you want to allow Cloud App Security access to your team information, activity log, and perform activities as a team member. To proceed, click **Allow**.  
  
7.  Back in the Cloud App Security console, you should receive a message that Dropbox was successfully connected.  
  
8.  Make sure the connection succeeded by clicking **Test API**.  
  
     Testing may take a couple of minutes. After receiving a success notice, click **Close**.  
  
After connecting Dropbox, you will receive events for 60 days prior to connection.

> [!NOTE] 
> Any Dropbox events for adding a file are displayed in Cloud App Security as Upload file to align to all other apps connected to Cloud App Security. 
 
## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  