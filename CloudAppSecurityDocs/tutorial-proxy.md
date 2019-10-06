---
# required metadata
title: Protect your organization in real time
description: This tutorial provides instructions for using access and session controls to monitor and control access to apps and their data.
author: shsagir
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: tutorial
ms.date: 8/19/2019

# optional metadata
#ROBOTS: NOINDEX # Used to prevent showing on search pages
#services: na
#ms.subservice: na
ms.collection: M365-security-compliance
---

# Protect your organization from any app in real time

*Applies to: Microsoft Cloud App Security*

The apps you sanction employees to use, often store some of your most sensitive corporate data and secrets. In the modern workplace, users access these apps from many risky situations. These could be partners in your organization over whom you have little visibility, or they could be employees using unmanaged devices or coming from public IP addresses. Due to the wide range of risks in this landscape, a zero-trust strategy must be employed. Often, it’s not enough to know about breaches and data loss in these apps after the fact; therefore, many information protection and cyberthreat scenarios must be addressed or prevented in real time.

This tutorial provides instructions for using access and session controls to monitor and control access to apps and their data, in order to adaptively manage access and mitigate against threats to protect your most sensitive assets. Specifically, we’ll cover the following scenarios:

> [!div class="checklist"]
>
> * Monitor user activities for anomalies
> * Protect your data when it’s exfiltrated
> * Prevent unprotected data from being uploaded to your apps
> * Enforce adaptive access controls to manage user actions in real time

## How to protect your organization from any app in real time

Use this process to roll out real-time controls in your organization.

### Phase 1: Monitor user activities for anomalies
<!--Monitor user activities for anomalies within popular custom cloud and on-premise apps-->

* Start by deploying the important apps that your organization uses
  * Our integration with Azure AD conditional access makes this very simple to deploy

* In addition to the 30 apps we feature, you can onboard any app with a simple process: https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-any-app

* After this, use the Activity Log in MCAS to monitor and better characterize usage of these apps, and understand risks

### Phase2: Protect your data when it’s exfiltrated
<!--Protect your data when it’s exfiltrated to unmanaged devices or by guest users-->

* Top of mind for many organizations is how to prevent data exfiltration before it happens

* Two of the biggest risks for data exfiltration are unmanaged devices, which may not be pin-protected, or may contain malicious apps, and guest users, over whom your IT department has little visibility and control

* Our integration with Intune for device management and Azure AD for user groups means that you can easily configure policies to mitigate both of these risks

* For any of the apps you’ve configured above, you can configure a policy to protect data that is downloaded, by leveraging our integration with Azure Information Protection
  * Unmanaged devices: create a session policy to label and protect files with a highly confidential policy meant for users in your organization only
  * Guest Users: create a session policy to apply custom permissions to any file that is downloaded, so only the guest user can access that file

### Prevent unprotected data from being uploaded to your apps

* In addition to data exfiltration, organizations want to make sure that data that is infiltrated to cloud apps is also secure

* For any of the apps you’ve configured above, you can configure a session policy to prevent upload of files that have not been correctly labeled, by leveraging our integration with Azure Information Protection
  * Configure an information block message to the user, giving them instructions on how to correct the mistake and try again
  * That way, data that is uploaded to the cloud, if shared or lost in the future, will have access permissions for only those that are intended to see it

### Enforce adaptive access controls to manage user actions in real time

* Many times evaluating risk at the gate is not enough—session risk can involve throughout the session
  * For example, token theft and replay can occur to hijack a session, the user could locations to a public space, or a seemingly innocuous user can go rogue

* For this reason, it’s important to be able to continuously re-evaluate conditional access policies on sensitive actions during a session, and take action accordingly

* Leveraging our deep integration with Azure AD, you can ensure that:
  * If an IP address changes, such as if the session is hijacked or the user moves, the user is prompted to perform an additional factor of authentication during the session, upon any risky action
  * If anomalous activity starts to occur, such as download of large amounts of sensitive content, the user is blocked from accessing the application

## See Also
