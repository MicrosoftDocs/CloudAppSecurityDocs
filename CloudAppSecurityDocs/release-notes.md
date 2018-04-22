---
# required metadata

title: What's  new with Cloud App Security| Microsoft Docs
description: This topic is updated frequently to let you know what's new in the latest release of Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: d418ef3d-76ee-45d5-b5ae-21346e5239a3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
*Applies to: Microsoft Cloud App Security*


# What's new with Microsoft Cloud App Security

## Cloud App Security release 121
Released April 22, 2018

-	The public preview of **Conditional Access App Control (formerly known as Cloud App Security Proxy)** has been enhanced with capabilities that facilitate deeper visibility into, and control over various applications. You can now create a Session Policy with an *Activity type* filter, to monitor and block a variety of app-specific activities. This new filter augments the existing file download control features, to provide you with comprehensive control of the applications in your organization and works hand-in-hand with Azure Active Directory conditional access, to provide real-time visibility and control of risky user sessions — for example, sessions with B2B collaboration users or users coming from an unmanaged device. For more information see [Session policies](session-policy-aad.md).
-	Cloud App Security's anomaly detection policies have been improved to include two new types of threat detection: Ransomware activity and Terminated user activity. Cloud App Security extended its ransomware detection capabilities with anomaly detection to ensure a more comprehensive coverage against sophisticated Ransomware attacks. Using our security research expertise to identify behavioral patterns that reflect ransomware activity, Cloud App Security ensures holistic and robust protection. Terminated user activity enables you to monitor the accounts of terminated users, who may have been de-provisioned from corporate apps, but in many cases they still retain access to certain corporate resources. For more information see [Get instantaneous behavioral analytics and anomaly detection](anomaly-detection-policy.md).


## Cloud App Security release 120
Released April 8, 2018

-	For Office 365 and Azure AD we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Office 365 and Azure AD applications (both internal and external). This enables you to create policies that will alert you if an application performs unexpected and unauthorized activities. 
-	When exporting an app permissions list to csv, additional fields such as publisher, permissions level and community usage are included to assist with the compliance and investigation process.
-	The ServiceNow connected app was improved so that internal service activities no longer register as having been performed by “Guest” and no longer trigger false positive alerts. These activities are now represented as N/A like all other connected apps.


## Cloud App Security release 119
Released March 18, 2018

-	The IP address ranges page includes built-in IP addresses that are discovered by Cloud App Security. This includes IP addresses for identified cloud services, like Azure and Office 365, as well as the Threat intelligence feed that automatically enriches IP addresses with information about known risky IP addresses. 
-	When Cloud App Security attempts to run a governance action on a file but fails because the file is locked, it will now automatically retry the governance action. 

## Cloud App Security release 118
Released March 4, 2018

- You can now take advantage of Microsoft Cloud App Security’s shadow IT discovery and monitoring capabilities on your own proprietary custom apps. The new ability to add custom apps to Cloud Discovery enables you to monitor app usage and get alerted on changes in the usage pattern. For more information see [Protecting your custom apps](cloud-discovery-custom-apps.md). This feature is being rolled out gradually.

- The Cloud App Security portal **Settings** pages were redesigned. The new design consolidates all the settings pages, provides search functionality and an improved design. 

- Cloud Discovery now supports Barracuda F-Series Firewalls and Barracuda F-Series Firewall Web Log Streaming.

- The search functionality in the User and IP address pages now enable auto complete to make it easier for you to find what you’re looking for.

- You can now perform bulk actions in the Exclude entities and Exclude IP address settings pages. This makes it easier for you to select multiple users and groups or IP addresses and exclude them from being monitored as part of the Cloud Discovery in your organization. 

## Cloud App Security release 117
Released February 20, 2018

-	Cloud App Security deepened integration with Azure Information Protection now enables you to protect files in G Suite. This public preview feature enables you to scan and classify files in G Suite, and automatically apply Azure Information protection labels for protection. For more information see [Azure Information Protection integration](azip-integration.md).

-	Cloud Discovery now supports [Digital Arts i-FILTER](http://www.daj.jp/en/products/if/).

-	The SIEM agents table now includes more detail for easier management.

## Cloud App Security release 116
Released February 4, 2018
- Cloud App Security's anomaly detection policy was enhanced with new **scenario-based detections** including impossible travel, activity from a suspicious IP address and multiple failed login attempts. The new policies are automatically enabled, providing out-of-the-box threat detection across your cloud environment. In addition, the new policies expose more data from the Cloud App Security detection engine, to help you speed up the investigation process and contain ongoing threats. For more information, see [Get instantaneous behavioral analytics and anomaly detection](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy).

- Gradual roll out: Cloud App Security now correlates between users and their accounts across SaaS apps. This enables you to easily investigate all the activities for a user, across all their various correlated SaaS apps, no matter which app or account they used.  

-	Gradual roll out: Cloud App Security now supports multiple instances of the same connected app. If you have multiple instances of, for example, Salesforce (one for sales, one for marketing) you will be able to connect them both to Cloud App Security and manage them from the same console to create granular policies and deeper investigation. 

- The Cloud Discovery parsers now support two additional Checkpoint formats, XML and KPC.



## Cloud App Security release 115
Released January 21, 2018

- This release provides an improved experience when selecting specific folders in file policies. You can now easily view and select multiple folders to include in a policy. 
- In the **Discovered apps** page: 
  - The bulk tagging feature enables you to apply custom tags (in addition to sanctioned and unsanctioned tags). 
  - When you **Generate an IP addresses report**, or **Generate a users report** the exported reports now include the information about whether the traffic was from sanctioned or unsanctioned apps. 
- You can now request a new API App connector from the Microsoft Cloud App Security team directly in the portal, from the **Connect an app** page. 


## Cloud App Security release 114
Released January 7, 2018

- Beginning in version 114, we are gradually rolling out the ability to create and save custom queries in the Activity log and Discovered apps pages. Custom queries enable you to create filter templates that can be reused for deep-dive investigation. In addition, **Suggested queries** have been added to provide out-of-the-box investigation templates to filter your activities and discovered apps. The **Suggested queries** include custom filters to identify risks such as impersonation activities, administrator activities, risky non-compliant cloud storage apps, enterprise apps with weak encryption, and security risks. You can use the **Suggested queries** as a starting point, modify them as you see fit, and then save them as a new query. For more information see [Activity filters and queries](activity-filters-queries.md) and [Discovered app filters and queries](discovered-app-queries.md).
 
- You can now check the current Cloud App Security service status by going [status.cloudappsecurity.com](https://status.cloudappsecurity.com) or directly from within the portal by clicking on **Help**>**System status**. 
 


## See Also  

For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  