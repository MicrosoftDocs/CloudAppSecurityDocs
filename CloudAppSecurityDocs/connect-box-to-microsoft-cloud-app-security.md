---
# required metadata

title: Connect Box to Cloud App Security for visibility and control over use | Microsoft Docs
description: This topic provides information about how to connect your Box app to Cloud App Security using the API connector.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/23/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: b3e4713e-986f-4a5e-9fcc-f8de94dd0df7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Connect Box to Microsoft Cloud App Security
This section provides instructions for connecting Cloud App Security to your existing Box account using the App Connector APIs.  
  
## How to connect Box to Cloud App Security  
  
> [!NOTE]  
>  Deploying with an account that is not an Admin account will lead to a failure in the API test and will not allow Cloud App Security to scan all of the files in Box. If this is a problem for you, you can deploy with a Co-Admin that has all of the privileges checked, but the API test will continue to fail and files owned by other admins in Box will not be scanned.  
  
1.  If you restrict application permission access, follow this step. Otherwise, skip to step 2.  
  
    -   In the Box Admin console, click the settings icon followed by **Business settings**.  
  
         ![box business settings](./media/box-business-settings.png "box business settings")  
  
    -   Click on the **Apps** tab.  
  
         ![box apps](./media/box-apps.png "box apps")  
  
    -   If **Unpublished Applications** is selected, in the **Except for** text box, add the Cloud App Security app serial number: `nduj1o3yavu30dii7e03c3n7p49cj2qh` and click **Save**.  
  
         ![box settings except for](./media/box-settings-except-for.png "box settings except for")  
  
    > [!NOTE]  
    >  If you are an existing Adallom customer, and your console URL is for Adallom and not Cloud App Security, use this app serial number: bwahmilhdlpbqy2ongkl119o3lrkoshc.  
  
2.  In the Cloud App Security portal, click **Investigate** and then **Connected apps**.  
  
3.  In the **App connectors** page, click the plus sign button and select **Box**.  
  
     ![connect box](./media/connect-box.png "connect box")  
  
4.  In the **Box settings** popup, click **Follow this link**.  
  
5.  This opens the Box logon page. Enter your credentials to allow Cloud App Security access to your team's Box app.  
  
6.  Box will ask you if you want to allow Cloud App Security access to your team information and activity log and perform any activity as any team member. To proceed, click **Allow**.  
  
7.  Back in the Cloud App Security portal, you should receive a message saying that Box was successfully connected.  
  
8.  Make sure the connection succeeded by clicking **Test API**.  
  
     Testing may take a couple of minutes. After receiving a success notice, click **Close**.  
  
Box is now connected to Cloud App Security.  
 
After connecting Box, you will receive events for 60 days prior to connection.
  
After connecting Box, Cloud App Security performs a full scan. Depending on how many files and users you have, completing the full scan can take awhile. To enable near real time scanning, files on which activity is detected are moved to the beginning of the scan queue, for example a file that is edited, updated, or shared is scanned right away and doesn't wait until it is reached by regular scan process. This does not apply to files that are not inherently modified, for example files that are viewed, previewed, printed or exported.
  
## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  