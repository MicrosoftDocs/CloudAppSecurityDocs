---
# required metadata

title: How to block downloads of sensitive data from unmanaged devices using Azure AD proxy capabilities| Microsoft Docs
description: This topic describes the scenario for protecting your organization against downloads of sensitive data by unmanaged devicesusing Azure AD proxy capabilities.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/9/2017
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

Today's IT admin is stuck between a rock and hard place: on the one hand, you want to enable your employees to be productive, and that means enabling employees to access apps so they can work at any time, from any device. On the other hand, you want to protect the company's assets, and that includes proprietary and privileged information. How can you enable your employees to access your cloud apps, while protecting your data? **This use case allows you to block downloads by users who have access to your sensitive data in enterprise cloud apps from either unmanaged devices or off-corporate network locations.**


## THE THREAT
An account manager in your organization wants to check something in Salesforce from home over the weekend, on his personal laptop. The Salesforce data may include client credit card information or personal information. The home PC is unmanaged, meaning that if he downloads documents from Salesforce onto it, it may be infected with malware or if it is lost or stolen, it may not be password protected and anyone who finds it will have access to sensitive information. 

## THE SOLUTION
Protect your organization by monitoring cloud app use using Azure AD conditional access and the Cloud App Security proxy.  

## Prerequisites

- Configure a cloud app for SSO in Azure AD  
- Make sure the [app is deployed to Cloud App Security](proxy-deployment-aad.md)

## Create a block download policy for unmanaged devices  

Cloud App Security proxy policies allow you to further restrict a session based on device state. When you want to control a session using its device as a condition, you must create both a conditional access policy AND as session policy to accomplish this.  

### Step 1: Create a conditional access policy

1. Create a conditional access policy with assigned users and app.
2. Select **Use proxy enforced restrictions** under session controls within the conditional access policy. After completing this task, proceed to the Cloud App Security portal and create a session policy to monitor and control file downloads in the session.  

 ![AAD conditional access policy](./media/aad-conditional-access.png)

### Step 2: Create a session policy

1. In the Cloud App Security portal, select **Control** followed by **Policies**. 

2. In the **Policies** page, click **Create policy** followed by **Session policy**.
 
 ![create session policy](./media/create-session-policy.png)

2. In the **Create session policy** page, give your policy a name and description for example, **Block downloads from Salesforce for unmanaged devices**.

3. Assign a **Policy severity** and **Category**.

 ![New session policy](./media/new-session-policy.png)

4. Under **Session control type**, select **Monitor all activities and control file download**. This will give you the ability to monitor everything your users do within a Salesforce session, and will give you control to block and protect downloads in real time. You will also be able to filter file content based on the Cloud App Security built-in DLP or an external DLP. 

 ![session policy control type](./media/session-policy-control-type.png)

5. Under **Activity source,** and **Activity filters** select the following: 
    - **Device tag**: Select **Compliant**,  **Domain joined**, or **Valid client certificate** as needed. 
    - **App**: Select the app you want to control. 

 > [!NOTE]
 > This is not required if you want to block download across all apps sent from Azure AD. If you want the policy to apply to a specific app, it will apply to the app you select here.

7. Alternatively, if you want to block the downloads for locations that are not part of your corporate network, under **Activity source,** and **Activity filters** select the following: 

  - **IP address** or **Location**: You can use either of these two parameters to identify non-corporate, or unknown locations, from which a user might be trying to access sensitive data.

  If you want to block downloads from BOTH unmanaged devices and non-corporate locations, you will have to create two session policies, one that sets the **Activity source** using hte location and one that sets the **Activity source** to unmanaged devices.
 
 ![session policy activity source](./media/session-policy-activity-filters.png)

6. Under **Activity source,** and **File filters** select the following: 
    - **Classification labels**: If you use Azure Information Protection classification labels and want to filter the files based on a specific Azure Information Protection Classification label.
    - Select **File name** or **File type** to apply restrictions based on these.
 
 ![session policy file filters](./media/session-policy-file-filters.png)

7. Enable **Content inspection** to enable the internal DLP to scan your files for sensitive content. 

 ![session policy content inspection](./media/session-policy-content-inspection.png)

8. Under **Actions**, select **block**. Customize the blocking message that your users will get when they are unable to download files.  

 ![session policy actions](./media/session-policy-actions.png)

9. Set the alerts you want to receive when the policy is matched. You can set a limit so that you won't receive too many alerts, and you can select whether to get the alerts as an email message, text message, or both.

 ![session policy alerts](./media/session-policy-alerts.png)


10. Click **Create**  
 

## Validate your policy 

1. To simulate an alert, from an unmanaged device or a non-corporate network location, log into app and attempt to download a file. 
2. The file should be blocked and you should receive the message you set for **Download restricted**. 
3. In the Cloud App Security portal, go to the policy report. A session policy match should appear shortly. 
4. You can click on the match to see which files were downloaded. The match itself will be masked to protect the sensitive data. 

