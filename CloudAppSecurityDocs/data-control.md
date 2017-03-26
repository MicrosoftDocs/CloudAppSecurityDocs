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
File Policies allow you to enforce a wide range of automated processes leveraging the cloud provider’s APIs. Policies can be set to provide continuous compliance scans, legal eDiscovery tasks, DLP for sensitive content stored in your cloud or shared externally or publicly and many more use cases.  
Cloud App Security can monitor any file type based on more than 20 metadata filters (for example, access level, file type). For more information see [Files](file-filters.md).
 
## Files shared externally contain sensitive data

This use case applies to Office 365, G Suite, Box, Dropbox, and Salesforce.

**Threat**|**Solution**
----|----
|Employees are sharing company files with sensitive data outside the organization. This can lead to data leaks that are unmonitored. This may be innocent and not violate your company's policies, but even in that case it's important to monitor what's being shared so that you are always aware of how your network is being used and what data is being shared externally.|Detect when files stored in your cloud apps contain either sensitive information that can be identified as PII or credit card numbers or the code name of a top secret project or other sensitive data and are shared with users outside your organization. Review the files that match the policy and verify whether or not they are a valid or approved share. For unauthorized matches, you can immediately take action and remove the external collaborators.|

### Prerequisites

[Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.

### Steps

1.	On the **Policies** page, click [**Create file policy**](data-protection-policies.md). 

2.	For example, in the [**Policy template**](policy-template-reference.md) field, choose **File containing PII detected in the cloud (built-in DLP engine)** and click **Apply template**. 
3.	In addition, you can also configure additional policies with content inspection settings to match files on different expression other than U.S. social security numbers.

4. Allow the policy to run on your network for at least a few hours.

5. Then, click on the policy name to go to the **Policy report** and review the matches that were triggered for the policy.

6. If you find false positives, mark them with a checkmark to exclude them from the report and from live matches. 

7. For true matches, you can take immediate [governance actions](governance-action.md) by clicking on the three dots at the end of the row and selecting the relevant governance action, for example, **Remove external collaborators**.

8. Based on the false positives that you found, you can refine the policy and choose to take automatic governance actions.

### How to test it

1. Create a new Word document with the following text in it: 078-05-1120.
2. Then, save the file as *test file.docx* and upload it to your cloud app. 
3. Go to the policy report. A file policy match should appear shortly. 
4. You can click on the match to see the context of the file. The match itself will be masked to protect the sensitive data. 




## Files shared externally and labeled as confidential

This use case applies to Office 365, G Suite, Box, Dropbox, and Salesforce.

**Threat**|**Solution**
----|----
|If you've already classified the data in your network, utilizing the classification capabilities in Azure Information Protection, you can monitor these classified files when they're in the cloud. This enables you to make sure that the data you classified as **confidential** (or some other sensitive classification) is not being inappropriately shared.|Detect files in your cloud apps that are classified as **Confidential** and have the incorrect access levels which allow unauthorized users to access them. Apply automatic governance actions such as **Quarantine file** to prevent data loss to your organization.|

### Prerequisites

- [Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.
- Follow the [Azure Information Protection integration instructions](azip-integration.md) to enable the automatic scan.

### Steps

1.	On the **Policies** page, click [**Create file policy**](data-protection-policies.md). 

2.	In the filter section, you can remove the filters for Access level and Last modified to run this policy on all the files in your cloud. These filters only apply to files modified from no on. Add the filter **Classification label** and then **equals** and select your organization's classification label. 

3.	To monitor inappropriate sharing of these classified files, add a filter with the access level you are trying to prevent - for example,  **Access level equals External, Public, Public on the web**.

4. Allow the policy to run on your network for at least a few hours.

5. Then, click on the policy name to go to the **Policy report** and review the matches that were triggered for the policy.

6. If you find false positives, mark them with a checkmark to exclude them from the report and from live matches. 

7. For true matches, you can take immediate [governance actions](governance-action.md) by clicking on the three dots at the end of the row and selecting the relevant governance action, for example, **Put in user quarantine**.

8. Based on the false positives that you found, you can refine the policy and choose to take automatic governance actions.


### How to test

1. Create a new Word document and use the Azure Information Protection tool bar to set the any sensitivity label, such as **Confidential**. 

2. Upload the file to your cloud app and then share it with everyone or with an external address. 

3. Go to the policy report. A file policy match should appear shortly. 

4. You can see the classification label by clicking on the file and opening the **File drawer**. 

## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  