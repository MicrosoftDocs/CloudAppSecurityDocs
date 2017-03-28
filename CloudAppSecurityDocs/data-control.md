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

# Controlling and protecting your files  

In today's corporate world, where there is so much data and so many devices, it can be hard to keep track of where your data is and who has access to it. Cloud App Security enables you to take control over your data by enabling file protection across the cloud. Cloud App Security provides you with tools for creating policies for what you want to allow and not allow across your corporate cloud, and gives you a wide range of automated processes to provide continuous compliance scans, legal eDiscovery tasks, DLP for sensitive content stored in your cloud or shared externally or publicly and many more use cases.  
Cloud App Security can monitor any file type based on more than 20 metadata filters (for example, access level, file type). For more information see [Files](file-filters.md). The following are two examples of data related threats that all organizations face, with procedures for how to protect your files in the cloud.
 
## Files that contain sensitive data are being shared externally 

This use case applies to Office 365, G Suite, Box, Dropbox, and Salesforce.

### THE THREAT
Employees are sharing company files with sensitive data outside the organization. This can lead to data leaks that are unmonitored. This may be innocent and not violate your company's policies, but even in that case it's important to monitor what's being shared so that you are always aware of how your network is being used and what data is being shared externally.

### THE SOLUTION
Gain visibility into file sharing in your network and deploy governance actions by deploying the following in Cloud App Security out the following policy and governance action in Cloud App Security.

#### Prerequisites

[Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.

#### Steps

1.	Control your files by creating a policy

    1. On the **Policies** page, click [**Create file policy**](data-protection-policies.md). 

    2.	For example, in the [**Policy template**](policy-template-reference.md) field, choose **File containing PII detected in the cloud (built-in DLP engine)** and click **Apply template**. 
    
    3.	In addition, you can also configure additional policies with content inspection settings to match files on different expression other than U.S. social security numbers. After you start the policy, it takes time for Cloud App Security to scan existing files and also any new files you add. Depending on the amount of data you have in your cloud, it may take some time to complete the scan.

2. Investigate your alerts
    
    1. Click on the policy name to go to the **Policy report** and review the matches that were triggered for the policy.

    2. For matches, you can take immediate [governance actions](governance-actions.md) by clicking on the three dots at the end of the row and selecting the relevant governance action, for example, **Remove external collaborators**.
    
    3. If you find false positives, mark them with a checkmark to exclude them from the report and from live matches. You can use the feedback feature to let the Cloud App Security team of improvements you'd like to add. 

3. After you've checked and fine-tuned the policy to make sure it's running as you intended, you can set it to perform automatic governance actions.

#### How to test it

1. Create a new Word document with the following text in it: 078-05-1120.
2. Then, save the file as *test file.docx* and upload it to your cloud app. 
3. Go to the policy report. A file policy match should appear shortly. 
4. You can click on the match to see the context of the file. The match itself will be masked to protect the sensitive data. 




## Files shared externally and labeled as confidential

This use case applies to Office 365, G Suite, Box, Dropbox, and Salesforce.

## THE THREAT

You know you need to protect your data, you've already gone to the trouble of classifying your files in Azure Information Protection. But once you classify them, how do you know where they are and who's looking at them? 

## THE SOLUTION
 You can monitor these classified files when they're in the cloud using Cloud App Security. This enables you to make sure that the data you classified as **confidential** (or some other sensitive classification) is not being inappropriately shared.Let Cloud App Security monitor and manage the files you classified in Azure Information Protection by rolling out the following policy and governance actions.

### Prerequisites

- [Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.
- Follow the [Azure Information Protection integration instructions](azip-integration.md) to enable the automatic scan.

### Steps

1. Control your data by creating a policy	
    
    1. On the **Policies** page, click [**Create file policy**](data-protection-policies.md). 

    2.	In the filter section, you can remove the filters for Access level and Last modified to run this policy on all the files in your cloud. These filters only apply to files modified from no on. Add the filter **Classification label** and then **equals** and select your organization's classification label. 

    3.	To monitor inappropriate sharing of these classified files, add a filter with the access level you are trying to prevent - for example,  **Access level equals External, Public, Public on the web**.  After you start the policy, it takes time for Cloud App Security to scan existing files and also any new files you add. Depending on the amount of data you have in your cloud, it may take some time to complete the scan.

2. Investigate your alerts

    1. Then, click on the policy name to go to the **Policy report** and review the matches that were triggered for the policy.
    
    2. For each matches, you can take immediate [governance actions](governance-actions.md) by clicking on the three dots at the end of the row and selecting the relevant governance action, for example, **Put in user quarantine**.
      
    3. If you find false positives, mark them with a check mark to exclude them from the report and from live matches. You can use the feedback feature to let the Cloud App Security team of improvements you'd like to add. 

3. Once you've checked that the policy is matching everything you want to catch, you can refine the policy and set it to perform automatic governance actions.


### How to test

1. Create a new Word document and use the Azure Information Protection tool bar to set the any sensitivity label, such as **Confidential**. 

2. Upload the file to your cloud app and then share it with everyone or with an external address. 

3. Go to the **Policy report**. A file policy match should appear shortly. 

4. You can see the classification label by clicking on the file and opening the **File drawer**. 



## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  