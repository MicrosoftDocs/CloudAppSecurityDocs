---
# required metadata

title: Overview of data control scenario | Microsoft Docs
description: This topic describes the scenario for controlling data in your cloud environment.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/26/2017
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
|Employees are sharing company files with sensitive data outside the organization. This can lead to data leaks that are unmonitored. This may be innocent and not violate your company's policies, but even in that case it's important to monitor what's being shared so that you are always aware of how your network is being used and what data is being shared externally.|Detect when files stored in your cloud apps contain either sensitive information that can be identified as PII or credit card numbers or the code name of a top secret project or other sensitive data and are shared with users outside your organization. Review the files that match the policy and verify whether or not they are a valid or approved share. For unauthorized matches, you can immediately take action and remove the external collaborators.|

### Prerequisites

[Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.

### Steps

1.	On the **Policies** page, click **Create file policy**. 
2.	For example, in the **Policy template** field, choose **File containing PII detected in the cloud (built-in DLP engine)** and click **Apply template**. 
3.	In addition, you can also configure additional policies with content inspection settings to match files on different expression other than U.S. social security numbers.

4. Allow the policy to run on your network for at least a few hours.

5. Then, click on the policy name to go to the Policy report and review the matches that were triggered for the policy.

6. If you find false positives, mark them with a checkmark to exclude them from the report and from live messages. 

7. For true matches, you can take immediate governance actions by clicking on the three dots at the end of the row and selecting the relevant governance action, for example, **Remove external collaborators**.

8. Based on the false positives that you found, you can refine the policy and choose to take automatic governance actions.


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
  
  