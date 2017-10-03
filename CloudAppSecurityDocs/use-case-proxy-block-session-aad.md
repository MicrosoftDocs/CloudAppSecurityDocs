---
# required metadata

title: How to block downloads of sensitive data from unmanaged devices using Azure AD proxy capabilities| Microsoft Docs
description: This topic describes the scenario for protecting your organization against downloads of sensitive data by unmanaged devicesusing Azure AD proxy capabilities.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/3/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 06238ebc-2088-4372-9412-96cceaf3b145

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Blocking downloads on unmanaged devices using Azure AD proxy capabilities

Today's IT admin is stuck between a rock and hard place: on the one hand, you want to enable your employees to be productive, and that means enabling employees to access apps and work at any time, from any device. On the other hand, you want to protect the company's assets, and that includes proprietary and privileged information. How can you enable your employees to access your cloud apps, but protect your data? **This use case allows you to block downloads from users accessing your sensitive data in enterprise cloud apps from either unmanaged devices or off-corporate network locations.**


## THE THREAT
An account manager in your organization wants to check something in Salesforce from home over the weekend, on his personal home computer. The Salesforce data may include client credit card information or personal information. The home PC is unmanaged, meaning that if he downloads documents from Salesforce onto it, it may be infected with malware or if it is lost or stolen, it may not be password protected and anyone who finds it will have access to sensitive information. 

## THE SOLUTION
Protect your organization by monitoring cloud app use using Azure AD conditional access and the Cloud App Security proxy.  

## Prerequisites

- Configure cloud app for SSO in Azure AD  
- Ensure app is deployed to Cloud App Security (see section **Deploying Cloud App Security for your SaaS apps**  

## Create a block download policy for unmanaged devices  

Cloud App Security proxy policies allow you to further restrict a session based on device state. When you want to control a session using device as a condition, you must create both a conditional access policy AND as session policy to accomplish this.  
1. Create a conditional access policy with assigned users and app
2. Select **Use proxy enforced restrictions** under session controls within the conditional access policy. After completing this task, proceed to the Cloud App Security portal and create a session policy to monitor and control file downloads in the session.  

1. Select **Control,** then **policies,** then **create policy,** then **session policy** 
2. Give your policy a name and description (eg **Block downloads from Salesforce for unmanaged devices**) 
3. Assign a policy severity and category 
4. Under **Session control type**, select **Monitor all activities and control file download**. This will give you the ability to monitor everything your users do within a Salesforce session, and will give you control to block and protect downloads in real time 
You will also be able to filter file content based on the Cloud App Security built-in DLP or an external DLP. 
5. Under **Activity source,** and **activity filters** select the following: 
    - Device tag: utilize compliant, domain joined, or valid client certificate as needed 
    - App: select app of choice 
 > [!NOTE]
 > This is not required if you want to block download in all apps sent from Azure AD; or if you choose to invoke this per app, it will apply to the app you select here.

6. Under **Activity source,** and **file filters** select the following** 
    - Classification labels: if you’re using Azure Information Protection classification labels 
    - File name or file type to apply restrictions based on these 
7. Enable Content inspection to enable the internal DLP to scan your files for sensitive content 
8. Under **Actions** select **block**. Customize the blocking message if desired  
9. Set the alerts you want to receive when the policy is matched. You can set a limit so that you won't receive too many alerts, and you can select whether to get the alerts as an email message or text message or both 
10. Select **create**  
 
## Create a block download policy for non-corporate locations   

Follow the same procedures with the following changes: 

1. Under **Activity source,** and **activity filters** select the following: 

  - IP address or location: either can be used to identify off-corporate, or unknown locations, from which a user might be trying to access sensitive data 

## Validate your policy 

1. To simulate an alert, from an unmanaged device or an off-corporate network location, log into app of choice and attempt to download a file 
2. File should be blocked and **download restricted** message appears 
3. Go to the policy report. A session policy match should appear shortly 
4. You can click on the match to see which files were downloaded. The match itself will be masked to protect the sensitive data 

