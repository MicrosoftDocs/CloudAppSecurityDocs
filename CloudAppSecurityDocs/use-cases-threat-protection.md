---
# required metadata

title: Threat protection use cases - Cloud App Security | Microsoft Docs
description: This topic outlines the steps to configure many threat protection use cases in Cloud App Security.
author: rkarlin
ms.author: rkarlin
ms.date: 05/27/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.service: cloud-app-security
ms.assetid: 7c8d5bfd-194e-40ba-b0b0-dfae80f45ecb


# optional metadata
ms.suite: ems
ms.custom: seodec18

---
# Get started with threat protection use cases

*Applies to: Microsoft Cloud App Security*


Identify high-risk usage and cloud security issues, detect abnormal user
behavior, and prevent threats in your sanctioned cloud apps. Get visibility into
user and admin activities and define policies to automatically alert on
suspicious behavior or when specific activities that you consider risky happen
in your sanction environments. Draw from the vast amount of Microsoft threat
intelligence and security research data. Threat detection policies help you
ensure that your sanctioned apps have all the security controls you need in
place and help you maintain control over them.

**Detect and control user activity from un-familiar geo-location**

Auto detection of user access or activity from un-familiar location which was
never used by anyone else in the organization.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

Automatically configured out of the box to alert on access from new locations.
No action needed to configure a policy. More details can be found
[here](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy).

**Detect compromised account by impossible geo-location (Impossible travel)**

Auto detection of user access or activity from 2 different location in a time
period which is shorter than the time it takes to travel between the two.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

1.  Automatically configured out of the box to alert on access from impossible
    locations. More details can be found
    [here](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy).

2.  [Optional
    customization](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy#scope-anomaly-detection-policies)
    is possible:

    1.  Customize detection scopes in terms of users/groups

    2.  Choose the type of sign-ins to consider

    3.  Set your sensitivity preference for alerting

3.  Create the file policy

**Detect suspicious activity from an “on-leave” employee**

Detect when a user, on unpaid leave and should not be active on any organization
resource is accessing any of the organization cloud resources.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

-   Create a security group in Azure Active Directory for the users on un-paid
    leave and add all the users to monitor.

## Steps

1.  On the [User groups
    page](https://docs.microsoft.com/en-us/cloud-app-security/user-groups),
    click Create user group and import the relevant Azure AD group.

2.  On the Policies page, create a new Activity policy.

3.  Select filter *User group* equals the name of the user groups you created in
    Azure AD for the un-paid leave users.

4.  Configure the actions to be take when an alert is triggered.

5.  Optional: Create a governance action on detected violation (availability
    varies between services)

    1.  Choose to suspend user

6.  Create the file policy

**Detect and notify the use of a Browser with out of date OS**

Detect when a user is using an outdated client version which might pose
compliance or security risk

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

1.  On the Policies page, create an Activity policy.

2.  Select filter *User agent tag* equals *Outdated browser* and *outdated
    operating system*

3.  Configure the actions to be take when an alert is triggered.

4.  In Governance, All apps, select Notify user – so user can act upon the alert
    and update the necessary components

5.  Create the file policy

**Detect and alert on Admin activity from Risky IP**

Detect an admin activity done from and IP which is considered as a risky IP and
notify system admin for further investigation or govern the admin’s account.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

-   Go to Settings [Symbol] IP address ranges and add IP address ranges for both
    internal subnets and their egress public IPs with the “Internal” category.

## Steps

1.  On the *Policies* page, create an *Activity policy*.

2.  Set Create filters for the policy *Single activity*

3.  Select filter *IP address Category* equals *Risky*

4.  Select filter *Administrative activity* is *True*

5.  Configure the actions to be take when an alert is triggered.

6.  In Governance, *All apps*, select *Notify user* and *CC the user’s manager*

7.  *C*reate the file policy

**Detect activities by service account from external IPs**

Detect service accounts activities originating from a non-internal IP addresses
which could indicate suspicious behavior or a compromised account risk.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

-   Go to Settings [Symbol] IP address ranges and add IP address ranges for both
    internal subnets and their egress public IPs with the “Internal” category.

-   Standardize a naming convention for service accounts in your environment
    (e.g. all account names start with “svc”).

## Steps

1.  On Policies page, create an Activity policy.

2.  Select filter *User Name* Starts with *“svc”* (or other set naming
    convention)

3.  Select filter *IP Address Category* does not equal *Other* and *Corporate*

4.  Configure the actions to be take when an alert is triggered.

5.  Create the policy

**Detect mass download (data exfiltration)**

Detect when a certain user accesses or downloads a massive number of files in a
short period of time.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

1.  On Policies page, create an activity policy

2.  Select filter *IP Addresses Tag* does not equal *Microsoft Azure* – exclude
    non interactive machine-based activities

3.  Select filter *Activity types* equals *\*{Any Download} \** activities

4.  Configure the actions to be take when an alert is triggered.

5.  Create the policy

**Detect potential Ransomware activity**

Auto detection of potential Ransomware activity.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

-   Automatically configured out of the box alert on potential Ransomware
    activity. No action needed to configure a policy.  
    It is possible to configure Scope of the detection and to customize the
    action to be taken upon an alert.  
    More details about how Cloud App Security identifies Ransomware activities
    can be found
    [here](https://docs.microsoft.com/en-us/cloud-app-security/use-case-ransomware).

Note:

-   Applicable for O365, G Suite, Box and Dropbox

**Detect malware in the cloud**

Detect files containing malware in your cloud environments by utilizing Cloud
App Security’s integration with the Microsoft’s Threat Intelligence engine.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

-   Automatically configured out of the box alert on potential Malware infected
    files. No action needed to configure a policy.

**Detect Rough admin takeover**

Detect repeated Admin activity that would indicate malicious intentions.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

1.  On Policies page, create an activity policy

2.  In Create filter for the policy, Select Act on Repeated activity and
    customize the Minimal repetitions and timeframe.

3.  Select filter *User From group* equals *{Select all admin related groups}*
    as *Actor only*

4.  Select filter *Activity type* equals *{All Password update/changes/Reset}*

5.  Configure the actions to be take when an alert is triggered.

6.  Create the policy

**Detect suspicious inbox manipulation rule**

A suspicious inbox rule was set on a user's inbox. This may indicate that the
user account is compromised, and that the mailbox is being used to distribute
spam and malware in your organization.

## Prerequisites

-   Use of Microsoft exchange for e-mails.

## Steps

-   Automatically configured out of the box alert on suspicious inbox
    manipulation rules activity. No action needed to configure a policy.  
    It is possible to configure Scope of the detection and to customize the
    action to be taken upon an alert.

**Detect leaked credentials (New)**  
  
When cybercriminals compromise valid passwords of legitimate users, they often
share those credentials. This is usually done by posting them publicly on the
dark web or paste sites or by trading or selling the credentials on the black
market.

Cloud App Security utilizes Microsoft’s Threat intelligence to match such
credentials to the ones used inside the organization.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

-   Automatically configured out of the box alert on compromised user accounts.
    No action needed to configure a policy.

**Detect anomalous file downloads by a user (New)**<br>
-------------------------------------------------------

Detect when users perform multiple file download activities in a single session
with respect to the baseline learned, which could indicate an attempted breach.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

-   Automatically configured out of the box alert on anomalous user download
    activities. No action needed to configure a policy.  
    It is possible to configure Scope of the detection and to customize the
    action to be taken upon an alert.

**Detect anomalous file shares by a user (New)** 
-------------------------------------------------

Detect when users perform multiple file sharing activities in a single session
with respect to the baseline learned, which could indicate an attempted breach.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

-   Automatically configured out of the box alert on anomalous user share
    activities. No action needed to configure a policy.  
    It is possible to configure Scope of the detection and to customize the
    action to be taken upon an alert.

**Detect anomalous activities from infrequent country (New)**
-------------------------------------------------------------

Detect activities from a location that was not recently or never visited by the
user or by any user in the organization.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

-   Automatically configured out of the box alert on anomalous activity
    locations. No action needed to configure a policy.  
    It is possible to configure Scope of the detection and to customize the
    action to be taken upon an alert.

Note:

-   Detecting anomalous locations necessitates an initial learning period of 7
    days, during which it does not alert on any new locations.

**Detect activity performed by a terminated user (New)**
--------------------------------------------------------

Detect when a terminated user performs an activity in a sanctioned application.
This may indicate malicious activity by a terminated employee who still has
access to corporate resources.

## Prerequisites

-   At least one connected app via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## Steps

-   Automatically configured out of the box alert on terminated user activity.
    No action needed to configure a policy.  
    It is possible to configure Scope of the detection and to customize the
    action to be taken upon an alert.


## Next steps 

[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
