---
# required metadata

title: Block downloads from unmanaged devices with Cloud App Security Conditional Access App Control
description: This tutorial describes the scenario for protecting your organization against downloads of sensitive data by unmanaged devices using Azure AD reverse proxy capabilities.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 1/24/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18
#Customer intent: As a sec op, I want to block download of sensitive information so that I can control where my sensitive information is shared.
---
# Tutorial: Block download of sensitive information

*Applies to: Microsoft Cloud App Security*

>[!div class="step-by-step"]
>[« PREVIOUS: How to create an access policy](access-policy-aad.md)

Today's IT admin is stuck between a rock and hard place. You want to enable your employees to be productive. That means allowing employees to access apps so they can work at any time, from any device. However, you want to protect the company's assets including proprietary and privileged information. How can you enable employees to access your cloud apps while protecting your data? **This tutorial allows you to block downloads by users who have access to your sensitive data in enterprise cloud apps from either unmanaged devices or off-corporate network locations.**

> [!div class="checklist"]
>
> * Create a block download policy for unmanaged devices
> * Validate your policy

## The threat

An account manager in your organization wants to check something in Salesforce from home over the weekend, on their personal laptop. The Salesforce data might include client credit card information or personal information. The home PC is unmanaged. If they download documents from Salesforce onto the PC, it might be infected with malware. Should the machine be lost or stolen, it may not be password protected and anyone who finds it has access to sensitive information.

## The solution

Protect your organization by monitoring and controlling cloud app use using Azure AD conditional access and Microsoft Cloud App Security Conditional Access App Control.

## Prerequisites

* A valid license for Azure AD Premium P1
* Configure a cloud app for SSO in Azure AD
* Make sure the [app is deployed to Cloud App Security](proxy-deployment-aad.md)

## Create a block download policy for unmanaged devices

Cloud App Security session policies allow you to restrict a session based on device state. To accomplish control of a session using its device as a condition, create both a conditional access policy AND a session policy.

### Step 1: Create an Azure AD conditional access policy

1. Create an Azure AD conditional access policy with assigned users and app.
2. Select **Use Conditional Access App Control enforced restrictions** under session controls within the conditional access policy.

After completing this task, go to the Cloud App Security portal and create a session policy to monitor and control file downloads in the session.

### Step 2: Create a session policy

1. In the Cloud App Security portal, select **Control** followed by **Policies**.

2. In the **Policies** page, click **Create policy** followed by **Session policy**.

3. In the **Create session policy** page, give your policy a name and description. For example, **Block downloads from Salesforce for unmanaged devices**.

4. Assign a **Policy severity** and **Category**.

5. For the **Session control type**, select **Control file download (with DLP)**. This setting gives you the ability to monitor everything your users do within a Salesforce session and gives you control to block and protect downloads in real time.

6. Under **Activity source** in the **Activities matching all of the following** section, select the filters:

   * **Device tag**: Select **Does not equal**. and then select **Compliant**,  **Domain joined**, or **Valid client certificate**. Your selection depends on the method used in your organization for identifying managed devices.

   * **App**: Select the app you want to control.

   * **Users**: Select the users you want to monitor.

7. Alternatively, you can block the downloads for locations that aren't part of your corporate network. Under **Activity source** in the **Activities matching all of the following** section, set the following filters:

   * **IP address** or **Location**: You can use either of these two parameters to identify non-corporate or unknown locations, from which a user might be trying to access sensitive data.

     > [!NOTE]
     > If you want to block downloads from BOTH unmanaged devices and non-corporate locations, you have to create two session policies. One policy sets the **Activity source** using the location. The other policy sets the **Activity source** to unmanaged devices.

   * **App**: Select the app you want to control.

   * **Users**: Select the users you want to monitor.

8. Under **Activity source** in the **Files matching all of the following** section, set the following filters:

   * **Classification labels**: If you use Azure Information Protection classification labels, filter the files based on a specific Azure Information Protection Classification label.

   * Select **File name** or **File type** to apply restrictions based on file name or type.
9. Enable **Content inspection** to enable the internal DLP to scan your files for sensitive content.

10. Under **Actions**, select **block**. Customize the blocking message that your users get when they're unable to download files.

11. Set the alerts you want to receive when the policy is matched. You can set a limit so that you don't receive too many alerts. Select whether to get the alerts as an email message, text message, or both.

12. Click **Create**

## Validate your policy

1. To simulate the blocked file download, from an unmanaged device or a non-corporate network location, sign in to the app. Then, try to download a file.

2. The file should be blocked and you should receive the message you set under **Customize block messages**.

3. In the Cloud App Security portal, click on **Control** followed by **Policies**, and then click on the policy you’ve created to view the policy report. A session policy match should appear shortly.

4. In the policy report, you can see which logins where redirected to Microsoft Cloud App Security for session control, and which files were downloaded or blocked from the monitored sessions.


## Next steps

> [!div class="nextstepaction"]
> [How to create an access policy](access-policy-aad.md)

> [!div class="nextstepaction"]
> [How to create a session policy](session-policy-aad.md)

[!INCLUDE [Open support ticket](includes/support.md)]
