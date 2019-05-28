---
# required metadata

title: Information protection use cases - Cloud App Security | Microsoft Docs
description: This topic outlines the steps to configure many information protection use cases in Cloud App Security.
author: rkarlin
ms.author: rkarlin
ms.date: 05/27/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.service: cloud-app-security
ms.assetid: 9a616767-4558-46f1-9da8-aa337920ae45


# optional metadata
ms.suite: ems
ms.custom: seodec18

---
# Get started with information protection use cases

*Applies to: Microsoft Cloud App Security*

Cloud App Security file policies allow you to enforce a wide range of automated processes, leveraging the cloud provider’s APIs. Policies can be set to provide information protectin, including continuous compliance scans, legal eDiscovery tasks, DLP for sensitive content shared publicly.

Cloud App Security can monitor any file type based on more than 20 metadata filters (for example, access level, file type). For more information, see [File policies](data-protection-policies.md).

## Detect and prevent external sharing of sensitive data

Detect when files with personally identifying information or other sensitive data are stored in a Cloud service and shared with users who are external to your organization. This violates your company policy and creates a potential compliance breach.

### Prerequisites

You must have at least one app connected using [app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).
 
### Steps

1.  On the **Policies** page, create a new **File policy**.

2.  Set the filter **Access Level** equals **Public (Internet) / Public / External**.

3.  Under **Inspection method**, select **Data Classification Service (DCS)**, and choose **Sensitive information inspection**.

5.  Select one or more **Information types**, according to your company's policy.

6.  Configure the actions to be take when an alert is triggered. For example, you can create a governance action that runs on detected file violations in G Suite in which you select the option to **Remove external users** and **Remove public access**.

7.  Create the file policy.

## Detect externally shared confidential data

Detect when files that are labeled **Confidential** and are stored in a cloud service are shared with external users, violating company policies.

### Prerequisites

- You must have at least one app connected using [app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

- Enable [Azure Information Protection integration](azip-integration.md).

### Steps

1.  On the **Policies** page, create a new **File policy**.

2.  Select **Classification label in Azure Information Protection** equals the **Confidential** label, or your company's equivalent.

3.  Set the filter **Access Level** equals **Public (Internet) / Public / External**.

4.  Configure the actions to be take when an alert is triggered.

1.  Optional: Create Governance actions to be taken on files when a violation is detected. The optional governance actions varies between services.

5.  Create the file policy.

## Detect and encrypt sensitive data

Detect files containing personally identifying information and other sensitive data that is share in a cloud app and apply classification labels to limit access only to employees in your company.

### Prerequisites

- You must have at least one app connected using [app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

- Enable [Azure Information Protection integration](azip-integration.md).
 
### Steps

1.  On the **Policies** page, create a new **File policy**.

2.  Under **Inspection method**, select **Data Classification Service (DCS)**, and choose **Sensitive information inspection**.

5.  Select one or more **Information types**, according to your company's policy.

5.  Under **Alert**, check **Apply classification label governance** and select the classification label that your company uses to restrict access to company employees. 

6.  Create the file policy.

> [!NOTE]
> The ability to apply a classification label directly in Cloud App Security is currently only supported for Box, G Suite, SharePoint online and OneDrive for business.

## Detect stale externally shared data

Detect unused and stale files (files that were not updated recently) that are accessible publicly via direct public link, web search or to specific external users.

### Prerequisites

-   You must have at least one app connected using [app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

### Steps

1.  On the **Policies** page, create a new **File policy**.

2.  Select and apply the policy template **Stale externally shared files**.

3.  Customize the **Last modified** period to match your organization’s policy

4.  Configure the actions to be take when an alert is triggered..

5.  Optional: Set governance action to be taken on the alerted file.

    1.  Examples:

        1.  G Suite: Make the file private and notify last file editor

        2.  Box: Notify last file editor

        3.  SharePoint online: Make the file private and Send policy-match
            digest to the file owner.

6.  Create the file policy

**Detect data access from an un-authorized geo-location**

Detect when files are being accessed from an un-authorized geo-location based on
your organization’s geographies to identify potential data leakage or malicious
access.

### Prerequisites

-   At least one app connected using [app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).
### Steps

1.  On Policies page, Create an Activity Policy.

2.  Select *Activity type* filter equals to any type considered as file/folder
    access (e.g View, Download, Access, Modify and etc.)

3.  Select Location filter does not equal the organization’s expected usage
    origin countries (Whitelist)

    1.  Optional: Use Blacklist approach if un-authorized countries list is well
        defined – change the filter to equals.

4.  Configure the actions to be take when an alert is triggered.

5.  Optional: Create a governance action on detected violation (availability
    varies between services)

    1.  Choose to suspend user

6.  Create the Activity policy

**Detect and protect confidential data store in a non-compliant SP site**

Detect files which are labeled as confidential stored in a non-compliant
SharePoint site.

### Prerequisites

-   Azure information protection labels are configured and used inside the
    organization.

### Steps

1.  On the **Policies** page, create a new **File policy**.

2.  Select **Classification label** in AIP equals **Confidential** label, or your company's equivalent.

3.  Select **Parent folder** filter does not equal, then click **Select a folder** and choose all the compliant folders in your organization.

6.  Check **Create an alert for each matching file**.

7.  Optional - Create a governance action to control what happens when a file is found that violates the policy. For example, Set Box to Send a policy digest to file owner and put the file in admin quarantine.

8.  Create the file policy.

## Detect externally shared source code

Detect when files that contain content that might be source code are shared publicly or are shared with users outside of your organization.

### Prerequisites

At least one app connected using [app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

### Steps

1.  On the **Policies** page, create a new **File policy**.

2.  Select and apply the policy template **Externally shared source code**

3.  Optional: Customize the list of file Extensions to match your organization's source code file extensions.

4.  Configure the actions to be take when an alert is triggered.

5.  Optional - Create an action to govern files violating the policy

    1.  Examples:

        1.  Box: Send a policy digest to file owner and admin quarantine the
            file

6.  Select and apply the policy template

## Detect unauthorized access to group data (Refactored)

Detect when certain files that belong to a specific user group are being accessed excessively by a user who is not part of the group, thus potentially preventing potential insider threat.

### Prerequisites

-   At least one app connected using [app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).
### Steps

1.  On Policies page, Create an Activity Policy.

2.  Choose *Act on Repeated activity*

    1.  Customize the parameters of repetitions and a timeframe to meet your
        organizations policy

3.  Select *Activity type* filter equals to any type considered as file/folder
    access (e.g View, Download, Access, Modify and etc.) in the required service
    (e.g

4.  Select filter *User* of a type *From group* equals

5.  Click on Select user group and select the relevant user group/s

    1.  Note: [User groups can be imported
        manually](https://docs.microsoft.com/en-us/cloud-app-security/user-groups)
        from the supported services.

6.  Select filter *Files and folders* of a type *Specific files or folders*
    equals

7.  Click on the *Select a file...*

8.  Choose the files/folders which belong to the audited user group

9.  Configure the actions to be take when an alert is triggered.

10. Optional: Create a governance action on detected violations (availability
    varies between services)

    1.  Choose to suspend user

11. Create the file policy

**Detect publicly accessible S3 buckets (New)**

Detect and protect against potential data leakage from AWS S3 buckets.

### Prerequisites

-   Connected AWS instance via [app
    connectors](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

### Steps

1.  On the **Policies** page, create a new **File policy**.

2.  Select and apply the policy template *Publicly accessible S3 buckets (AWS)*

3.  Configure the actions to be take when an alert is triggered.

4.  Optional - Under Governance, create an action to govern the policy violation

    1.  Check the governance action via AWS – Make private – making the S3
        buckets private.

5.  Select and apply the policy template

**Detect and protect GDPR related data across file storage apps (New)**
-----------------------------------------------------------------------

Detect files containing personally identifying information and other sensitive data that are bound to GDPR
compliance policy that is shared on cloud storage services and apply
classification labels to limit access only to authorized personnel.

### Prerequisites

-   At least one app connected using [app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).
-   [Azure information protection (AIP)
    integration](https://docs.microsoft.com/en-us/cloud-app-security/azip-integration)
    is enabled and GDPR label is configured in AIP.

### Steps

1.  On the **Policies** page, create a new **File policy**.

2.  Select *Data Classification Service* (DCS) for Inspection method

3.  Choose the *Sensitive Information inspection* type

4.  Select one or more Information type that comply with the GDPR compliance

    1.  Some of the relevant types: EU debit card number, EU Driver License
        Number, EU National identification number, EU passport number, EU SSN,
        SU Tax identification number.

5.  Customize action to be taken upon an alert

6.  In Governance, Check Apply Classification label governance per supported app

    1.  Select the GDPR related Classification label.

7.  Create the file policy

> [!NOTE]
>   Currently, apply classification label is only supported for Box, G Suite,
    SharePoint online and OneDrive for business.

**Block file downloads to unmanaged devices**

Control and block download activities in real time from managed and un-managed
devices using Cloud app security [session
controls](https://docs.microsoft.com/en-us/cloud-app-security/proxy-intro-aad).

Prerequisites:

-   [Deploy conditional access app control for Azure AD
    apps](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)

-   Applies for SAML based apps utilizing AAD SSO – [list of supported apps out
    of the
    box](https://docs.microsoft.com/en-us/cloud-app-security/proxy-intro-aad#supported-apps-and-clients).

### Steps

1.  Follow steps
    [here](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download)

> [!NOTE]
>   Support for Any app based on SAML and utilizing SSO with AAD is coming soon.

**Protect files on download in real-time**

Control and protect file downloads in real time by applying correct file label,
utilizing Cloud app security integration with Azure Information protection.

Prerequisites:

-   [Deploy conditional access app control for Azure AD
    apps](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)

-   Applies for SAML based apps utilizing AAD SSO – [list of supported apps out
    of the
    box](https://docs.microsoft.com/en-us/cloud-app-security/proxy-intro-aad#supported-apps-and-clients).

-   Azure information protection labels are configured and used inside the
    organization.

### Steps

1.  Follow steps
    [here](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#create-a-cloud-app-security-session-policy)
    - section \#6.

> [!NOTE]
>   Support for Any app based on SAML and utilizing SSO with AAD is coming soon.

**Protect files by limiting user session in real time**

Control and protect file downloads in real time by applying real time
permissions control for a user downloading the file, for example, making the
file read only for the user.

Prerequisites:

-   [Deploy conditional access app control for Azure AD
    apps](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)

-   Applies for SAML based apps utilizing AAD SSO – [list of supported apps out
    of the
    box](https://docs.microsoft.com/en-us/cloud-app-security/proxy-intro-aad#supported-apps-and-clients).

-   Azure information protection labels are configured and used inside the
    organization.

### Steps

1.  Follow steps
    [here](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#create-a-cloud-app-security-session-policy)
    - section \#6 until bullet c.

2.  Select the *Protect action*

3.  Select Apply custom permissions to downloading user

4.  Choose the permission level that should be applied to the downloading user
    (e.g Viewer – view only).

5.  Customize additional actions to be taken upon an alert.

6.  Create the file policy

> [!NOTE]
>   Permission changes are currently supported for the following [file
    types](https://docs.microsoft.com/en-us/cloud-app-security/azip-integration#prerequisites).

-   Support for Any app based on SAML and utilizing SSO with AAD is coming soon.

## Next steps 

[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
