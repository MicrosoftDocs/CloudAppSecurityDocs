---
# required metadata

title: How to block access to cloud apps from unmanaged devices | Microsoft Docs
description: This topic describes the scenario for protecting your organization against access to cloud apps from unmanaged devices.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/15/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 9aec9c6f-c9e2-4a4b-8b6a-2f8e4465ee3f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Blocking access to cloud apps from unmanaged devices

In the corporate world, bring-your-own-device is great for employees who want to make the most of their personal phones and tablets in the workplace. However, many IT admins, aware of the threats this poses to an organization's data and network, want to be able to block access from these unmanaged devices to some or all of the company's cloud apps. 

## How does Cloud App Security detect unmanaged devices?
.

>[!NOTE]
> This use case applies to .

## THE THREAT
An sales manager in your organization has a managed device that she uses regularly, but on occasion, wants to check something in Salesforce on her personal mobile phone. The phone isn't managed by your organization, meaning that it may be infected with viruses, malware or may not be password protected and anyone who picks it up will be able to access your Salesforce account.

## THE SOLUTION
Protect your organization by monitoring cloud app use in Cloud App Security, and creating an Access policy to govern and block activities from unmanaged devices.

## Prerequisites

[Deploy](proxy-deployment.md) the Cloud App Security Proxy for Salesforce.

## Set up unmanaged device detection


## Create an Access policy
Access policies allow you to monitor attempts made by your users to log into cloud apps and, if necessary, block them from accessing the app.


1.  In the console, click on **Control** followed by **Policies**.  
  
2.  Click **Create policy** and select **Access policy**.  
  
3.  Give your policy a name and description, such as **Block access to Salesforce from unmanaged devices**.  
  
3. Give your policy a **Policy severity**. If you have set Cloud App Security to send you notifications on policy matches for a specific policy severity level, this will be used to determine whether this policy's matches will trigger a notification.

4.  You can leave the **Category** setting as **Access control**.  
  
7. Under **Activity source**, click **Select apps from the list below** and select **Salesforce**.

8. In the activity filters section, select **Device type** and then **does not equal** and select **Compliant**, **Domain joined** and **Valid client certificate**.
  
10. At this stage, under **Actions** to be taken when the policy is matched, select either :
    - Allow: If you select allow, users will be allowed to download the files. 
    or
    
 
 >[!WARNING]
 >It is highly recommended that you do not **Block** downloads before first running the policy in **Allow** mode and checking that the results are as expected and only after you have determined that the policy does not block anyone unintended, switch the policy to **Block** downloads.
 
 9. Set the alerts you want to receive when the policy is matched. You can set a limit so that you won't receive too many alerts, and you can select whether to get the alerts as an email message or text message or both.

10. To view Access policy matches, click **Control** and then **Policies**. Filter the results to display only the Access policies using the **Type** filter at the top. For more information about the matches for each policy, click on a policy. Click the **History** tab to see a history back to up to 6 months of policy matches.     
  
## Validate your policy

1. To simulate an alert, from an unmanaged device, try to log into Salesforce.
3. Go to the policy report. An Access policy match should appear shortly. 
4. You can click on the match to see who tried to log into Salesforce and from what device. 

## Blocking access

After you've validated it and fine-tuned the policy, remove possible false positives that may have matched your policy. Then, do the following: 

1. When an Access policy is matched, you can remediate it by setting automated [governance actions](governance-actions.md).

2. To do this, edit the policy you created above and set **Actions** to **Block** downloads when the policy is matched. The user will not be ato access Salesforce from any device that is not managed.
  
 
 ## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  