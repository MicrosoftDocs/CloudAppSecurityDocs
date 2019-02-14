---
# required metadata

title: Policy template reference for Cloud App Security
description: This article provides information on how policies are used and set up to control cloud app use.
keywords:
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: a6658937-57a2-484a-85cb-5a4cdbeeb002

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Policy template reference

*Applies to: Microsoft Cloud App Security*

This article provides information on policy templates included in Microsoft Cloud App Security. 

## Policy templates

We recommend starting policy creation based on an existing template whenever possible for ease of use. This table lists policy templates that exist in Microsoft Cloud App Security.

|Risk category|Template name|Description|
|-----|----|----|
|Cloud Discovery|Anomalous behavior in discovered users|Alert when anomalous behavior is detected in discovered users and apps, such as: large amounts of uploaded data compared to other users, large user transactions compared to the user's history.|
|Cloud Discovery|Anomalous behavior of discovered IP addresses|Alerts when anomalous behavior is detected in discovered IP addresses and apps, such as: large amounts of uploaded data compared to other IP addresses, large app transactions compared to the IP address's history.|
|Cloud Discovery|Collaboration app compliance check|Alert when new collaboration apps are discovered that aren't compliant with SOC2 and SSAE 16, and are used by more than 50 users with a total daily use of more than 50 MB.|
|Cloud Discovery|Cloud storage app compliance check|Alert when new cloud storage apps are discovered that aren't compliant with SOC2, SSAE 16, ISAE 3402 and PCI DSS, and are used by more than 50 users with total daily use of more than 50 MB.|
|Cloud Discovery|CRM app compliance check|Alert when new CRM apps are discovered that aren't compliant with SOC2, SSAE 16, ISAE 3402, ISO 27001 and HIPAA, and are used by more than 50 users with a total daily use of more than 50 MB.|
|Cloud Discovery|New cloud storage app|Alert when new cloud storage apps are discovered that are used by more than 50 users with total daily use of more than 50 MB.|
|Cloud Discovery|New code hosting app|Alert when new code hosting apps are discovered that are used by more than 50 users with total daily use of more than 50 MB.|
|Cloud Discovery|New collaboration app|Alert when new collaboration apps are discovered that are used by more than 50 users with a total daily use of more than 50 MB.|
|Cloud Discovery|New CRM app|Alert when new CRM apps are discovered that are used by more than 50 users with a total daily use of more than 50 MB.|
|Cloud Discovery|New high volume app|Alert when new apps are discovered that have total daily traffic of more than 500 MB.|
|Cloud Discovery|New high upload volume app|Alert when new apps are discovered whose total daily upload traffic is more than 500 MB.|
|Cloud Discovery|New Human-Resource Management app|Alert when newly discovered Human-Resource Management apps are used by more than 50 users with a total daily use of more than 50 MB.|
|Cloud Discovery|New online meeting app|Alert when new online meeting apps are discovered that are used by more than 50 users with a total daily use of more than 50 MB.|
|Cloud Discovery|New popular app|Alert when new apps are discovered that are used by more than 500 users.|
|Cloud Discovery|New risky app|Alert when new apps are discovered with risk score lower than 6 and that are used by more than 50 users with a total daily use of more than 50 MB.|
|Cloud Discovery|New sales app|Alert when new sales apps are discovered that are used by more than 50 users with a total daily use of more than 50 MB.|
|Cloud Discovery|New vendor management system apps|Alert when new vendor management system apps are discovered that are used by more than 50 users with a total daily use of more than 50 MB.|
|DLP|Externally shared source code|Alert when a file containing source code is shared outside your organization.|
|DLP|File containing PCI detected in the cloud (built-in DLP engine)|Alert when a file with payment card information (PCI) is detected by the Microsoft Cloud App Security built-in data loss prevention (DLP) engine in a sanctioned cloud app.|
|DLP|File containing PHI detected in the cloud (built-in DLP engine)|Alert when a file with protected health information (PHI) is detected by the Microsoft Cloud App Security built-in data loss prevention (DLP) engine in a sanctioned cloud app.|
|DLP|File containing private information detected in the cloud (built-in DLP engine)|Alert when a file with personal data is detected by the Microsoft Cloud App Security built-in data loss prevention (DLP) engine in a sanctioned cloud app.|
|Threat detection|Administrative activity from a non-corporate IP address|Alert when an admin user performs an administrative activity from an IP address that isn't included in the corporate IP address range category. First configure your corporate IP addresses by going to the Settings page, and setting **IP address ranges**.|
|Threat detection|General anomaly detection|Alert when an anomalous session is detected in one of the sanctioned apps, such as: impossible travel, sign in pattern, inactive account.|
|Threat detection|Log on from a risky IP address|Alert when a user signs into your sanctioned apps from a risky IP address. By default, the Risky IP address category contains addresses that have IP address tags of Anonymous proxy, TOR, or Botnet. You can add more IP addresses to this category in the IP address ranges settings page.|
|Threat detection|Mass download by a single user|Alert when a single user performs more than 50 downloads within 1 minute.|
|Threat detection|Multiple failed user sign-in attempts to an app|Alert when a single user tries to sign in to a single app and fails more than 10 times within 5 minutes.|
|Threat detection|Potential ransomware activity|Alert when a user uploads files to the cloud that might be infected with ransomware.|
|Threat detection|User log on from a non-categorized IP address|Alert when a user logs on from an IP address that isn't included in a specific IP range category. You can categorize IP addresses by going to the Settings page, and selecting IP address ranges.|
|Sharing control|File shared with personal email addresses|Alert when a file is shared with a user’s personal email address.|
|Sharing control|File shared with unauthorized domain|Alert when file is shared with an unauthorized domain (such as your competitor).|
|Sharing control|Shared digital certificates (file extensions)|Alert when a file containing digital certificates is publicly shared. Use this template to help govern your AWS storage.|
|Sharing control|Publicly accessible S3 buckets (AWS)|Alert when an AWS S3 bucket is publicly shared.|
|Sharing control|Stale externally shared files|Find externally shared files that haven't been opened or modified for 6 months.|



## Next steps 
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
