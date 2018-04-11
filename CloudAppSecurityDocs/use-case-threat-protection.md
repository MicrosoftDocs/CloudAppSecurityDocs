---
# required metadata

title: Protecting your organization against threats | Microsoft Docs
description: This topic describes the scenario for protecting your organization against threats in your cloud environment.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/27/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 0017be99-29c3-468e-a181-255e343ed4f5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protecting your organization against threats  

Identify high-risk usage and cloud security issues, detect abnormal user behavior, and prevent threats in your connected cloud apps. Get visibility into user and admin activities and define policies to automatically alert on suspicious behavior or when specific activities that you consider risky happen in your sanction environments. Draw from the vast amount of Microsoft threat intelligence and security research data. Threat detection policies help you ensure that your sanctioned apps have all the security controls you need in place and help you maintain control over them.
 
## Mass download by a single user (data exfiltration by an insider)

This use case applies to Office 365, G Suite, Box, Dropbox, Salesforce.

### THE THREAT
A malicious insider can exfiltrate data from Office 365 or other cloud apps by downloading or accessing multiple files over a short period of time.

### THE SOLUTION
Detect when a user downloads or accesses a massive number of files within a short period.

#### Prerequisites

[Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.

#### Setting up monitoring

1.	By default, Cloud App Security scans your network to establish a baseline, wherein it learns patterns of what your users ordinarily do in your cloud, when they do it and what they commonly do. 

2. Set a policy that will watch your cloud apps for massive downloads and alert you if something out of the ordinary happens:

    1. On the **Policies** page, click [**Create activity policy**](user-activity-policies.md). 
   

    2. In the [**Policy template**](policy-template-reference.md) field, choose **Mass download by a single user**.
    
    3. Optionally, you can fine tune the repeated activity filter.
    
    4. Click **Create**. 
   
     
2. Investigating your matches
    
    1. In the **Policies** page, click on the policy name to go to the **Policy report** and review the matches that were triggered for the policy.

    2. You can investigate the match by clicking on a specific match to open the activity drawer. In the drawer, you can see the other policies that this activity matched. 
    
    3. You can check the files that were downloaded by the user by clicking on the activity bjects in the **Activity drawer** and then on the file’s name, this will lead you to the file in the files table. There you can see if the files are owned by the user, who are they shared with and will allow you to determine if these are files they usually work on or whether they are internal IP that should not be downloaded.
     


#### Validating your policy

1. To simulate an alert, download a number of documents, that is larger than the threshold you set, from your connected cloud apps within a short period depending on the timeframe you set in the policy (for example, 30 downloads in less than 5 minutes).
3. Go to the policy report. An activity policy match should appear shortly. 
4. You can click on the match to see which files were downloaded.  

#### Removing the risk

After you've validated it and fine-tuned the policy, remove possible false positives that may have matched your policy, such as service accounts that are syncing files, folders of pictures from company events, etc. Then, do the following: 
  1. You can take [governance actions](governance-actions.md) opening the activity in the activity drawer, and click on the name of the file under **Activity objects**.

  2. Contact the users to see why they need to copies of so many corporate files on their computers.

 
## Admin activity from outside your organization's network

This use case applies to Office 365, G Suite, Box, Dropbox, Salesforce, and Okta.

### THE THREAT
An admin account has been compromised by an outside attacker. Admin accounts are the most sensitive accounts in your organization because the have the highest privileges and access to all the information in your organization. Usually administrative activity should be performed from the office as a part of the admin’s work, and not from remote locations or unrecognized devices.

### THE SOLUTION
Detect when people posing as admins are connecting to your cloud application from external IP addresses and performing any admin activity.

#### Prerequisites

- [Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app to Cloud App Security.

- Go to **Settings** > **IP address ranges** and add IP address ranges for both internal subnets and their egress public IPs and tag them as **Corporate**.

#### Setting up monitoring

1.	Start monitoring your cloud apps by setting up a policy that will watch your cloud apps for admin activity outside your network and alert you if something out of the ordinary happens:

    1. On the **Policies** page, click [**Create activity policy**](user-activity-policies.md). 
   

    2. In the [**Policy template**](policy-template-reference.md) field, choose **Administrative activity from a non-corporate IP address** and also set the **Activity type** to **Log on** and select **User** and then **From group** and select the group your administrators belong to.
    
    3. You can fine-tune the policy to set the number of repeated activities that you want to consider suspicious.
    
    4. Click **Create**. 
   
     
2. Investigating your matches
    
    1. In the **Policies** page, click on the policy name to go to the **Policy report** and review the matches that were triggered for the policy.

    2. You can investigate the match by clicking on a specific match to open the activity drawer. In the drawer, you can see the other policies that this activity matched. 
     
#### Validating your policy

1. To simulate an alert, from a computer with an IP address that is not part of your Corporate network, perform admin activities, making sure that the number of activities you perform is larger than the threshold you set, within a short period depending on the timeframe you set in the policy (for example, 1 activities in less than 5 minutes).
3. Go to the policy report. An activity policy match should appear shortly. 
4. You can click on the match to see what activities were performed. 

#### Removing the risk

After you've validated it and fine-tuned the policy, remove possible false positives that may have matched your policy. Then, do the following: 
  1. You can take [governance actions](governance-actions.md) opening the activity in the activity drawer, and click on the name of the **User**.

  2. In the user page that opens, you can see a graph of the user's activity over the last month, and locations where the user was seen active over the last month as well as group memberships, app activity and accounts. 
  
  3. If necessary, you can click **contact** to send an email message to the user to alert them that their account has been breached.

 ![auto gov external](./media/auto-gov-external.png)

   2. After it's fully validated, you can set it to perform automatic governance actions. For example, you can **Suspend user** or **Remove user's collaborations**.


## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  