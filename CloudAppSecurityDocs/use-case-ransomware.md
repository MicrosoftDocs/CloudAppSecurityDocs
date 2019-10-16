---
# required metadata

title: Overview of threat protection scenario - Cloud App Security | Microsoft Docs
description: This topic describes the scenario for protecting your organization against threats in your cloud environment.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 12/14/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 7a06a243-9ec2-4a11-8db2-bc065cdfef64

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Protecting your organization from ransomware

*Applies to: Microsoft Cloud App Security*

In latest massive ransomware attack, WannaCry hit the cyber world hard, infecting an estimated 200,000 computers across 150 countries. With the increase of ransomware attacks over the last few years, an average of 25,000 attacks per month in 2015 and 56,000 in 2016, it's becoming a cybersecurity necessity to be proactive about making sure your network and your cloud aren't at risk. This article explains how you can use Cloud App Security to monitor your cloud, detect, and mitigate threats and apply best practices for protecting your environment against ransomware.

## What is ransomware?
Ransomware is a cyber attack in which the attacker sends you a file that can block you from accessing your computer and encrypt your own files. The files are sometimes held for ransom and aren't decrypted until you pay the attacker to restore access to your computer, files, or critical LOB apps. Ransomware attacks can affect any computer, home, office, network, or server. In fact, because large organizations are made up of many users who may inadvertently open a file that unleashes ransomware across your network, organizations are at even greater risk of being forced to pay the attacker to stop the ransomware and restore access to computers or files.

>[!NOTE]
> This use case applies to Office 365, G Suite, Box and Dropbox.

## THE THREAT
A user in your organization is the target of a ransomware attack. The user might unknowingly open an email infected and run ransomware, which infects the all of their files, including the files synced to the cloud.

## THE SOLUTION
Detect potential ransomware on your cloud environment by creating a policy to update you when suspicious activity is detected, and set up automated actions to prevent ransomware files from being saved to your cloud.

## Out-of-the-box protection

[Connect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) at least one cloud app (Office 365, G Suite, Box, and Dropbox) to Cloud App Security.

1.	By default, Cloud App Security scans your network to establish a baseline, wherein it learns patterns of what your users ordinarily do in your cloud, when they do it and what they commonly do. 

2. Cloud App Security's automated [threat detection policies](anomaly-detection-policy.md) start running in the background from the time you connect. One of these policies searches for ransomware activity to ensure comprehensive coverage against sophisticated ransomware attacks. Using our security research expertise to identify behavioral patterns that reflect ransomware activity, Cloud App Security ensures holistic and robust protection. If Cloud App Security identifies, for example, a high rate of file uploads or file deletion activities it may represent an adverse encryption process. This data is collected in the logs received from connected APIs and is then combined with learned behavioral patterns and threat intelligence, for example, known ransomware extensions. 




## Next steps 

[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
