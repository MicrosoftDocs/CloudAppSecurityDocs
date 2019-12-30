---
# required metadata
title: Protect any app in use in your organization in real time
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

# Tutorial: Protect any app in use in your organization in real time

*Applies to: Microsoft Cloud App Security*

The apps you sanction employees to use, often store some of your most sensitive corporate data and secrets. In the modern workplace, users access these apps from many risky situations. These users could be partners in your organization over who you have little visibility, or employees using unmanaged devices or coming from public IP addresses. Due to the wide range of risks in this landscape, a zero-trust strategy must be employed. Often, it’s not enough to know about breaches and data loss in these apps after the fact; therefore, many information protection and cyberthreat scenarios must be addressed or prevented in real time.

This tutorial provides instructions for using access and session controls to monitor and control access to apps and their data, in order to manage access and mitigate against threats to protect your most sensitive assets. Specifically, we’ll cover the following scenarios:

> [!div class="checklist"]
>
> * Monitor user activities for anomalies
> * Protect your data when it’s exfiltrated
> * Prevent unprotected data from being uploaded to your apps

## How to protect your organization from any app in real time

Use this process to roll out real-time controls in your organization.

### Phase 1: Monitor user activities for anomalies
<!--Monitor user activities for anomalies within popular custom cloud and on-premise apps-->

1. **Deploy your apps**: Start by deploying the important apps that your organization uses. The deployment is made simple by our native integration with Azure Active Directory (Azure AD) Conditional Access. You can deploy apps  using the following steps:

    * Start by [deploying apps that are featured](proxy-intro-aad.md) by Cloud App Security to work out-of-the-box. For a list of apps that are featured, see [Supported apps and clients](proxy-intro-aad.md#supported-apps-and-clients).

    * Then, for apps not featured by Cloud App Security, use the following process to [onboard and deploy any app](proxy-deployment-any-app.md).

    Once your apps are deployed, they are monitored in real time giving you immediate insights into their activities and related information. You can use this information to identify anomalous behavior.

1. **Monitor and assess**: In Cloud App Security, use the [Activity Log](activity-filters.md) to monitor and characterize app use in your environment, and understand their risks. You can narrow the scope of activities listed by using [search, filters, and queries](activity-filters-queries.md) to quickly identify risky activities.

### Phase 2: Protect your data when it’s exfiltrated

A primary concern for many organizations is how to prevent data exfiltration before it happens. Two of the biggest risks are unmanaged devices (that may not be protected with a pin or may contain malicious apps) and guest users where your IT department has little visibility and control.

Now that your apps are deployed, you can easily configure policies to mitigate both of these risks by leveraging our native integrations with Windows Intune for device management, Azure AD for user groups, and Azure Information Protection for data protection.

* **Mitigate unmanaged devices**: Create a [session policy to label](session-policy-aad.md#create-a-cloud-app-security-session-policy) and protect highly confidential files meant for users in your organization only.
* **Mitigate guest users**: Create a [session policy to apply custom permissions](session-policy-aad.md#protect-download) to any file that is downloaded by guest users. For example, you can set permissions so that guest users can only access the protected file.

### Phase 3: Prevent unprotected data from being uploaded to your apps

In addition to preventing data exfiltration, organizations often want to make sure that data that is infiltrated to cloud apps is also secure. A common use case is when a user attempts to upload files that are not labeled correctly.

For any of the apps you’ve configured above, you can configure a session policy to prevent the upload of files that are not labeled correctly, as follows:

1. Create a session policy to [block uploads of incorrectly labeled files](session-policy-aad.md#protect-upload).

1. Configure the policy to display a [block message with instructions on how to correct the label and try again](session-policy-aad.md#educate-protect).

Protecting file uploads in this way ensures that data saved to the cloud has the correct access permissions applied. In the event that the file is shared or lost, it can only be accessed by authorized users.
