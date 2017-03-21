---
# required metadata

title: Overview of data control scenario | Microsoft Docs
description: This topic describes the scenario for controlling data in your cloud environment.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/21/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 57927618-cb66-4c7f-afd7-c96926460816

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Data control  
File Policies allow you to enforce a wide range of automated processes leveraging the cloud provider’s APIs. Policies can be set to provide continuous compliance scans, legal eDiscovery tasks, DLP for sensitive content shared publicly and many more use cases.  
Cloud App Security can monitor any file type based on more than 20 metadata filters (for example, access level, file type). For more information see [Files](file-filters.md).
 
## Files shared externally contain sensitive data

This use case applies to Office 365, G Suite, Box, Dropbox, and Salesforce.

**Threat**|**Solution**
----|----
|Employees are sharing company files with sensitive data outside the organization.|Detect when files stored in your cloud apps contain PII or other sensitive data and are shared with users outside your organization.|

### Prerequisites

[Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.

### Steps

1.	On the **Policies** page, click **Create file policy**. 
2.	In the **Policy template** field, choose **File containing PII detected in the cloud (built-in DLP engine)** and click **Apply template**.
3.	Optional: Configure additional policies with content inspection settings to match files on different expression other than U.S. social security numbers.
4.	Optional: Create a filter to **Access level equals External, Public, Public on the web**. 

### How to test it

Create a new Word document with the following text in it: 078-05-1120. Then, save the file as *test file.docx* and upload it to your cloud app. A file policy match should appear shortly. 

## Files shared externally and labeled as confidential

This use case applies to Office 365, G Suite, Box, Dropbox, and Salesforce.

**Threat**|**Solution**
----|----
|Data loss of files that are classified as **confidential** (or some other sensitive classification) outside your organization.|Detect files in your cloud apps that are classified as **Confidential** and have the incorrect access levels which allow unauthorized users to access them. Apply automatic governance actions such as **Quarantine file** to prevent data loss to your organization.|

### Prerequisites

- [Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.
- Follow the [Azure Information Protection integration instructions](azip-integration.md) to enable the automatic scan.

### Steps

1.	On the **Policies** page, click **Create file policy**. 
2.	Create the filter **Classification label**, selecting your organization's classification label.
3.	Create the filter **Access level equals External, Public, Public on the web**
4.	Optional: Under **Governance**, choose which automatic actions to take when a file violates the policy.

### How to test

Create a new Word document and use the Azure Information Protection tool bar to set the any sensitivity label, such as **Confidential**. Upload the file to your cloud app and then share it with everyone or with an external address. A file policy match should appear shortly. 

## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  