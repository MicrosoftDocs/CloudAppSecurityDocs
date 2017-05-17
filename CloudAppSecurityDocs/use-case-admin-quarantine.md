---
# required metadata

title: Use case for how to investigate and remediate file breaches using admin quarantine | Microsoft Docs
description: This topic describes the scenario for using admin quarantine to control data breaches.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/17/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 3fc04cfb-ad4c-4ac2-980a-ee9f4c740d88

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

There are plenty of scenarios in today's world of technical espionage and cyber threats in which you find your data exposed to users or apps that leave you vulnerable. With Cloud App Security, not only can you detect those unwanted vulnerabilities, but you can take immediate action to stop them in their tracks and lock down your files.   
Cloud App Security can monitor any file type based on more than 20 metadata filters (for example, access level, file type). For more information see [Files](file-filters.md), and using **Admin quarantine**, you can protect your files in the cloud.
 
## Quarantining files 

This use case applies to Office 365 and Box.

### THE THREAT
Your users are on the cloud. Even if it isn't sanctioned by your organization, according to today's statistics you can be sure that your users are working in cloud apps from their managed and unmanaged devices. But once you find a leak, or a file containing confidential information stored in the cloud, you need to be able to fix it.

### THE SOLUTION
Once you find a sensitive file shared externally or a confidential file saved on the cloud, you can quarantine the file manually or by setting an automated governance action - by doing this you can remove the data leak risk with a click.

#### Applying admin quarantine

1. Set file policies that detect breaches, such as a metadata only policy (such as a classification label in SharePoint Online), a native DLP policy (such as a policy that searches for credit card numbers) or an ICAP third party policy (such as a policy that looks for Vontu).

2. Quarantine location:
    1. For Office 365 SharePoint or OneDrive for Business, define an **Admin quarantine** folder under **Settings**, and provide a user notification that your user will receive when their file is quarantined. 
    ![quarantine settings](./media/quarantine-settings.png)

    2. For Box, the quarantine folder location and user message cannot be customized. The folder location is the drive of the admin who connected Box to Cloud App Security and the user message is: 


2. When a file matches a policy, the **Admin quarantine** option will be available for the file.

3. You can either manually apply the **Admin quarantine** action 
    ![quarantine action](./media/quarantine-action.png)


or set it as an automated quarantine action in the policy. 
    ![quarantine automatically](./media/quarantine-automated.png)


#### How admin quarantine works

 When **Admin quarantine** is applied, the following occurs behind the scenes:

1. The original file is moved to the admin quarantine folder you set.
2. The original file is deleted.
3. A tombstone file is uploaded to the original file location.
      ![quarantine tombstone](./media/quarantine-tombstone.png)

4. The user has access only to the tombstone, where they can read the custom guidelines provided by IT and the correlation ID to contact IT to release the file.
    

#### How to respond to a quaratined file

After a file is quarantined, it's important to know how to remediate the threat situation.

1. When you receive the alert that a file has been quarantined, investigates the file in the Cloud App Security **Alerts** page
   ![quarantine alerts](./media/quarantine-alerts.png)
 
     or in the **Policy Report** on the **Quarantined** tab.
        ![quarantine report](./media/quarantine-report.png)
        
2. Inspect the file in the quarantined folder on SharePoint online.
3. You can also look at the audit logs to deep dive into the file properties.
4. If the file is found to be against corporate policy,  run the organization’s Incident Response (IR) process.
5. If the file is found to be harmless, you can restore the file from quarantine, at which point the original file is released, i.e. it is copied back to the original location, the tombstone is deleted and the user can access the file.
  ![quarantine restore](./media/quarantine-restore.png)

>[!NOTE]
>When you restore a file:
- Original shares are not restored, default folder inheritance applied.
- The restored file contains only the most recent version.


>[!NOTE]
>The quarantine folder site access management is the customer’s responsibility.


## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  