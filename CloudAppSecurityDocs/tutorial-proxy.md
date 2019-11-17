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

1. **Deploy your apps**: Start by deploying the important apps that your organization uses. The deployment is made simple by our native integration with Azure Active Directory (Azure AD) Conditional Access. This can be done using the following methods:

    * Commence by [deploying apps that are featured](proxy-intro-aad.md) by Cloud App Security to work out of the box. For a list of apps that are featured, see [Supported apps and clients](proxy-intro-aad.md#supported-apps-and-clients).

    * Then, for apps not featured by Cloud App Security, use our simple process to [onboard and deploy any app](proxy-deployment-any-app.md).

    After deploying your apps, they are monitored in real time giving you immediate insights into their activities and related information that you can use to identify anomalous behavior.

1. **Monitor and assess**: Use the [Activity Log](activity-filters.md) in the Cloud App Security portal to view and better characterize how these apps are used in your environment, and understand their risks. You can narrow the scope of activities listed by using [search, filters, and queries](activity-filters-queries.md) to quickly identify risky activities.

### Phase 2: Protect your data when it’s exfiltrated
<!--Protect your data when it’s exfiltrated to unmanaged devices or by guest users-->

A primary concern for many organizations is how to prevent data exfiltration before it happens. Two of the biggest risks for data exfiltration are unmanaged devices (that may not be pin-protected or may contain malicious apps), and guest users over whom your IT department has little visibility and control.

Now that your apps are deployed, you can easily configure policies to mitigate both of these risks by leveraging our native integrations with Windows Intune for device management, Azure AD for user groups, and Azure Information Protection for data protection.

* **Mitigate unmanaged devices**: Create a [session policy to label](session-policy-aad.md#create-a-cloud-app-security-session-policy) and protect highly confidential files meant for users in your organization only.
* **Mitigate guest users**: Create a [session policy to apply custom permissions](session-policy-aad.md#protect-download) to any file that is downloaded by guest users. For example, you can set permissions so that guest users can only access the protected file.

### Phase 3: Prevent unprotected data from being uploaded to your apps

In addition to preventing data exfiltration, organizations often want to make sure that data that is infiltrated to cloud apps is also secure. A common use case for this is when a user attempts to upload files that are not labeled correctly.

For any of the apps you’ve configured above, you can configure a session policy to prevent the upload of files that are not labeled correctly, as follows:

1. Create a session policy to [block uploads of incorrectly labeled files](session-policy-aad.md#protect-upload).

1. Configure the policy to display a [block message with instructions on how to correct the label and try again](session-policy-aad.md#educate-protect).

Protecting file uploads in this way ensures that data saved to the cloud has the correct access permissions applied. In the event that the file is shared or lost, it can only be accessed by authorized users.
