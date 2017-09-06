---
# required metadata

title: How to block downloads of sensitive data from unmanaged devices using Azure AD proxy capabilities| Microsoft Docs
description: This topic describes the scenario for protecting your organization against downloads of sensitive data by unmanaged devicesusing Azure AD proxy capabilities.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/6/2017
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

Today's IT admin is stuck between a rock and hard place: on the one hand, you want to enable your employees to be productive, and that means access and ability to work all the time, from any device. On the other hand, you want to protect the company's assets, and that includes proprietary and privileged information. How can you enable your employees to access your cloud apps, but protect your data? Using Azure AD with Proxy capabilities provides you with a high-level of control over what you do and don't allow in your cloud apps. 


## THE THREAT
An account manager in your organization wants to check something in Salesforce from home over the weekend, on his personal mobile phone. The account includes information may include client credit card information or personal information. The phone is unmanaged, meaning that if he downloads documents from Salesforce onto his phone, it may be infected with Malware or if the device is lost or stolen, it may not be password protected and anyone who finds it will have access to sensitive information.

## THE SOLUTION
Protect your organization by rolling out policies in Azure AD and enforcing them with the conditional access Proxy to govern and block activities from unmanaged devices.

## Prerequisites

[Deploy](link to Azure AD) policies to select which users or user groups you want to apply the restrictions to.

## Set up unmanaged device detection


## Create a Proxy session control policy

Proxy Session control policies allow you to monitor everything a user does inside a session and give you control capabilities so that you can block and protect downloading of files.


1.  After enabling Proxy control in your Azure AD policy, you will be directed to the **Create new session policy** window.  
  
3.  Give your policy a name and description, such as **Block SF downloads on unmanaged devices**.  
  
3. Give your policy a **Policy severity**. If you have set Azure AD to send you notifications on policy matches for a specific policy severity level, this will be used to determine whether this policy's matches will trigger a notification.

4.  You can leave the **Category** setting as **DLP**.  
  
6. Under **Session control type**, select **Monitor all activities and control file download**. This will give you the ability to monitor everything your users do within a Salesforce session, and will give you control to block and protect downloads in real time. You will also be able to filter file content based on the Cloud App Security built-in DLP or an external DLP.
 
7. Under **Activity source**, click **Select apps from the list below** and select **Salesforce**.

8. In the activity filters section, select **Device type** and then **does not equal** and select **Compliant**, **Domain joined** and **Valid client certificate**.
  
8. Set the policy to recognize which files and data you consider private:

    - In the file filters section, select your confidential files. If you work with Azure Information Protection, you can select **Classification label** and then select the labels you use for classified files.
    
    -  Enable **Content inspection** to enable the internal DLP to scan your files for classified content, for example you can select **Include files that match a preset expression** and then select **All countries: Finance: Credit card number**.

10. At this stage, under **Actions** to be taken when the policy is matched, select either:
    - Allow: If you select allow, users will be allowed to download the files. 
    or
    - Protect: If you select **Protect**, the user will be able to download the files but they will be encrypted with Azure RMS. You can also set a default action to be taken if encryption fails (block or allow the download).
 
 >[!WARNING]
 >It is highly recommended that you do not **Block** downloads before first running the policy in **Allow** mode and checking that the results are as expected and only after you have determined that the policy does not block anyone unintended, switch the policy to **Block** downloads.
 
 9. Set the alerts you want to receive when the policy is matched. You can set a limit so that you won't receive too many alerts, and you can select whether to get the alerts as an email message or text message or both.

10. To view session policy matches, click **Control** and then **Policies**. Filter the results to display only the Session policies using the **Type** filter at the top. For more information about the matches for each policy, click on a policy. Click the **History** tab to see a history back to up to 6 months of policy matches.     
  
## Validate your policy

1. To simulate an alert, from an unmanaged device, log into Salesforce and attempt to download a file.
3. Go to the policy report. A session policy match should appear shortly. 
4. You can click on the match to see which files were downloaded. The match itself will be masked to protect the sensitive data. 

## Blocking and protecting your sensitive information

After you've validated it and fine-tuned the policy, remove possible false positives that may have matched your policy. Then, do the following: 

1. When a session policy is matched, you can remediate it by setting automated [governance actions](governance-actions.md).

2. To do this, edit the policy you created above and set **Actions** to **Block** downloads when the policy is matched. The user will not be able to download the files, and will receive a message that they do not have permission to download the files.
  