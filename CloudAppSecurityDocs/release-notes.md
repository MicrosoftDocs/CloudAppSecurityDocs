---
# required metadata

title: What's new with Cloud App Security| Microsoft Docs
description: This topic is updated frequently to let you know what's new in the latest release of Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/1/2018
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


## Cloud App Security release 126

Released June 24, 2018

-	**Conditional Access App Control GA**<br>Microsoft Cloud App Security’s Conditional Access App Control (reverse proxy) is now generally available for any SAML applications. Conditional Access App Control integrates directly with your Azure AD conditional access policies to **monitor and control your users’ sessions in real time**, while enabling them to be productive. Since first previewing the feature, many features and improvements have been made, including: 
    -	The ability to create an [access policy](access-policy-aad.md) to manage access to the same apps from native clients, in addition to creating a session policy for browser traffic.
    -	The app onboarding process was streamlined to support custom SAML applications in your organization.
    -	As part of the Azure worldwide network, the integration and interface have been improved for a seamless experience for users located anywhere in the world.
 

-	**Content inspection with Microsoft Data Classification Service GA**<br>Microsoft Cloud App Security integration with Microsoft Data Classification Services is now generally available. This integration enables you to utilize the Microsoft Data Classification Service natively, to classify the files in your cloud apps. For more information see [Microsoft Data Classification Services integration](dcs-inspection.md). This feature is currently only available in the US and Europe (excluding France).

- **Cloud Discovery executive report**<br>Microsoft Cloud App Security is gradually rolling out the ability to generate a Cloud Discovery executive PDF report. This report provides an overview of the Shadow IT use that was identified in your organization, highlighting the top apps and users in use overall and in leading categories, and focuses on the risk that Shadow IT poses in your organization. In addition, the report provides a list of recommendations for how to improve visibility into, and control over, Shadow IT in your organization. Use this report to make sure that potential risks and threats are removed and that your organization remains safe and secure.

-	**Malware detection**<br>The malware detection capability is being gradually rolled out that **automatically detects malicious files in your cloud storage**, regardless of the file type. Microsoft Cloud App Security uses Microsoft's threat intelligence to recognize whether certain files are associated with known malware attacks or are potentially malicious. For more information, see [Anomaly detection policies](anomaly-detection-policy.md).
 
-	**Automated remediation for suspicious activities**<br>You can now set automatic remediation actions for suspicious session triggered by the anomaly detection policies. This enhancement enables you to be alerted instantly when a breach occurs and **apply governance actions automatically**, such as suspend user. For more information, see [Anomaly detection policies](anomaly-detection-policy.md#adp-automated-gov). 
 
-	**Security configuration assessment for Azure**<br>Microsoft Cloud App Security is gradually rolling out the ability to get a security configuration assessment of your Azure environment, and provides recommendations for missing configuration and security control. For example, it will let you know if you are missing MFA for administrative users. For more information, see [Cloud Security Posture Management integration](security-config.md).  
  
-	**Automated detection of risky OAuth Apps**<br>In addition to the existing investigation of OAuth apps connected to your environment, Microsoft Cloud App Security is now gradually rolling out the ability to set automated notifications to let you know when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users. For more information, see [App permission policies](app-permission-policy.md).
 
-	**Managed Security Service Provider management (MSSP) support**<br>Microsoft Cloud App Security now provides a better management experience for MSSPs. External users can now be configured as administrators and assigned any of the [roles currently available in Microsoft Cloud App Security](manage-admins.md). In addition, to enable MSSPs to provide services across multiple customer tenants, Administrators who have access rights to more than one tenant can now easily switch tenants within the portal. For information about managing admins, see [Manage admins](manage-admins.md).
  
-	**Integration with external DLP GA**<br>Microsoft Cloud App Security allows you to [leverage existing investments in third-party classification systems](icap-stunnel.md) such as Data Loss Prevention (DLP) solutions, and enables you to scan the contents of cloud applications using existing deployments running in your environment. For more information, see [External DLP integration](icap-stunnel.md).


## Cloud App Security release 125

Released June 10, 2018


- **New investigation capability by top users:**<br>
Microsoft Cloud App Security added a new investigation widget to the dashboard that shows top users by the number of open threat detection alerts. This investigation widget enables you to focus your threat investigation on users with the highest number of suspicious sessions.

- **Support for AWS S3 buckets:**<br>
Microsoft Cloud App Security can now detect AWS S3 buckets and their sharing levels. This provides alerts and visibility into publicly accessible AWS buckets. This also enables you to create policies based on buckets and apply automatic governance. In addition, there is a new policy template available called **Publicly accessible S3 buckets (AWS)** that you can use to easily create a policy to govern your AWS storage. In order to enable these new capabilities, make sure you update your AWS connected apps by adding the new permissions described in [Connect AWS](connect-aws-to-microsoft-cloud-app-security.md).

- **Admin privileges based on user groups**:
You can now set administrative permissions to Microsoft Cloud App Security admins per user group. For example, you can set a specific user as an administrator for only users in Germany. This would enable the user to view and modify information in Microsoft Cloud App Security only for the user group “Germany - all users.” For more information, see [Managing admin access](manage-admins.md).


## Cloud App Security release 124

Released May 27, 2018

-	**GDPR risk assessment added to Cloud App Catalog**<br>
13 new risk factors were added to Microsoft Cloud App Security. These risk factors follow the checklist of the GDPR framework to enable you to assess the apps in the Cloud App Catalog according to the GDPR regulations.

-	**Integrate with Microsoft Data Classification Service**<br>
Microsoft Cloud App Security now enables you to utilize the Microsoft Data Classification Service natively, to classify the files in your cloud apps. <br>
The Microsoft Data Classification Service provides a unified information protection experience across Office 365, Azure Information Protection, and Microsoft Cloud App Security. It allows you to extend the same data classification framework to the third-party cloud apps that are protected by Microsoft Cloud App Security, leveraging the decisions you already made across an even greater number of apps. 

-	**Connect to Microsoft Azure** (gradual rollout)<br>
Microsoft Cloud App Security is extending its IaaS monitoring capabilities beyond Amazon Web Services and now supports Microsoft Azure. This enables you to seamlessly connect and monitor all your Azure subscriptions with Cloud App Security. This connection provides you with a powerful set of tools to protect your Azure environment, including: 

       - 	Visibility into all activities performed through the portal

       - 	Ability to create custom policies to alert on unwanted behavior, as well as the ability to automatically protect possible risky users by suspending, or forcing them to sign in again.

       - 	All Azure activities are covered by our anomaly detection engine and will automatically alert on any suspicious behavior in the Azure portal, such as impossible travel, suspicious mass activities, and activity from a new country.<br>

  For more information, see [Connect Azure to Microsoft Cloud App Security](connect-azure-to-microsoft-cloud-app-security.md).
 
-	**Scoped deployments** (gradual rollout) <br>
Microsoft Cloud App Security provides enterprises with the ability to granularly determine which users they want to monitor and protect based on group membership. This feature enables you to select users whose activities will not show up for any of the protected applications. The scoped monitoring capability is especially useful for: 

    -	Compliance – If your compliance regulations necessitate that you refrain from monitoring users from certain countries due to local regulations.

       -	Licensing – If you want to monitor fewer users to stay within the limits of your Microsoft Cloud App Security licenses.
   For more information, see [Scoped deployment](scoped-deployment.md).

-	**Breached app alert for discovered apps**<br>
 We now have a built-in alert to notify you when any of a tenant’s discovered apps is breached. The alert will provide information about the time and date of the breach, which users used the app, and will link to publicly available sources that provide information about the breach.

-	**New mail server**<br>
 Cloud App Security’s mail server changed and uses different IP address ranges. To make sure you can get notifications, add the new IP addresses to your anti-spam whitelist. For users who customize their notifications, Microsoft Cloud App Security enables this for you using MailChimp®, a third-party email service. For the list of mail server IP addresses, and instructions for enabling work with MailChimp, see [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements#email-server) and [Mail settings](mail-settings.md).


## Cloud App Security release 123

Released May 13, 2018

- **Anomaly detection policy scoping**:<br>
The anomaly detection policies can now be scoped. This enables you to set each anomaly detection policy to include only specific users or groups, and to exclude specific users or groups. For example, you can set the Activity from infrequent county detection to ignore a specific user who travels frequently. 


## Cloud App Security release 122
Released April 29, 2018

-	Gradual rollout: You can now **set administrative permissions to Microsoft Cloud App Security admins per app**. For example, you can set a specific user as an administrator for only G Suite. This would enable the user to view and modify information in Microsoft Cloud App Security only when it relates exclusively to G Suite. For more information, see [Managing admin access](manage-admins.md).
- Gradual rollout: **Okta admin roles are now visible** in Microsoft Cloud App Security and are available for each role as a tag under **Settings** > **User groups**.


## Cloud App Security release 121
Released April 22, 2018

-	The public preview of **Conditional Access App Control (formerly known as Cloud App Security Proxy)** has been enhanced with capabilities that facilitate deeper visibility into, and control over various applications. You can now create a Session Policy with an *Activity type* filter, to monitor, and block a variety of app-specific activities. This new filter augments the existing file download control features, to provide you with comprehensive control of the applications in your organization and works hand-in-hand with Azure Active Directory conditional access, to provide real-time visibility and control of risky user sessions — for example, sessions with B2B collaboration users or users coming from an unmanaged device. For more information, see [Session policies](session-policy-aad.md).
-	Gradual roll out: Cloud App Security's **anomaly detection policies have been improved** to include two new types of threat detection: Ransomware activity and Terminated user activity. Cloud App Security extended its ransomware detection capabilities with anomaly detection to ensure a more comprehensive coverage against sophisticated Ransomware attacks. Using our security research expertise to identify behavioral patterns that reflect ransomware activity, Cloud App Security ensures holistic and robust protection. Terminated user activity enables you to monitor the accounts of terminated users, who may have been de-provisioned from corporate apps, but in many cases they still retain access to certain corporate resources. For more information, see [Get instantaneous behavioral analytics and anomaly detection](anomaly-detection-policy.md).


## Cloud App Security release 120
Released April 8, 2018

-	For Office 365 and Azure AD, we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Office 365 and Azure AD applications (both internal and external). This enables you to create policies that will alert you if an application performs unexpected and unauthorized activities. 
-	When exporting an app permissions list to csv, additional fields such as publisher, permissions level, and community usage are included to assist with the compliance and investigation process.
-	The ServiceNow connected app was improved so that internal service activities no longer register as having been performed by “Guest” and no longer trigger false positive alerts. These activities are now represented as N/A like all other connected apps.


## Cloud App Security release 119
Released March 18, 2018

-	The IP address ranges page includes built-in IP addresses that are discovered by Cloud App Security. This includes IP addresses for identified cloud services, like Azure and Office 365, as well as the Threat intelligence feed that automatically enriches IP addresses with information about known risky IP addresses. 
-	When Cloud App Security attempts to run a governance action on a file but fails because the file is locked, it will now automatically retry the governance action. 

## Cloud App Security release 118
Released March 4, 2018

- You can now take advantage of Microsoft Cloud App Security’s shadow IT discovery and monitoring capabilities on your own proprietary custom apps. The new ability to add custom apps to Cloud Discovery enables you to monitor app usage and get alerted on changes in the usage pattern. For more information, see [Protecting your custom apps](cloud-discovery-custom-apps.md). This feature is being rolled out gradually.

- The Cloud App Security portal **Settings** pages were redesigned. The new design consolidates all the settings pages, provides search functionality, and an improved design. 

- Cloud Discovery now supports Barracuda F-Series Firewalls and Barracuda F-Series Firewall Web Log Streaming.

- The search functionality in the User and IP address pages now enables auto complete to make it easier for you to find what you’re looking for.

- You can now perform bulk actions in the Exclude entities and Exclude IP address settings pages. This makes it easier for you to select multiple users and groups or IP addresses and exclude them from being monitored as part of the Cloud Discovery in your organization. 

## Cloud App Security release 117
Released February 20, 2018

-	Cloud App Security deepened integration with Azure Information Protection now enables you to protect files in G Suite. This public preview feature enables you to scan and classify files in G Suite, and automatically apply Azure Information protection labels for protection. For more information, see [Azure Information Protection integration](azip-integration.md).

-	Cloud Discovery now supports [Digital Arts i-FILTER](http://www.daj.jp/en/products/if/).

-	The SIEM agents table now includes more detail for easier management.

## Cloud App Security release 116
Released February 4, 2018
- Cloud App Security's anomaly detection policy was enhanced with new **scenario-based detections** including impossible travel, activity from a suspicious IP address, and multiple failed login attempts. The new policies are automatically enabled, providing out-of-the-box threat detection across your cloud environment. In addition, the new policies expose more data from the Cloud App Security detection engine, to help you speed up the investigation process and contain ongoing threats. For more information, see [Get instantaneous behavioral analytics and anomaly detection](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy).

- Gradual roll out: Cloud App Security now correlates between users and their accounts across SaaS apps. This enables you to easily investigate all the activities for a user, across all their various correlated SaaS apps, no matter which app or account they used.  

-	Gradual roll out: Cloud App Security now supports multiple instances of the same connected app. If you have multiple instances of, for example, Salesforce (one for sales, one for marketing) you will be able to connect them both to Cloud App Security and manage them from the same console to create granular policies and deeper investigation. 

- The Cloud Discovery parsers now support two additional Checkpoint formats, XML, and KPC.



## Cloud App Security release 115
Released January 21, 2018

- This release provides an improved experience when selecting specific folders in file policies. You can now easily view and select multiple folders to include in a policy. 
- In the **Discovered apps** page: 
  - The bulk tagging feature enables you to apply custom tags (in addition to sanctioned and unsanctioned tags). 
  - When you **Generate an IP addresses report**, or **Generate a users report** the exported reports now include the information about whether the traffic was from sanctioned or unsanctioned apps. 
- You can now request a new API App connector from the Microsoft Cloud App Security team directly in the portal, from the **Connect an app** page. 


## Cloud App Security release 114
Released January 7, 2018

- Beginning in version 114, we are gradually rolling out the ability to create and save custom queries in the Activity log and Discovered apps pages. Custom queries enable you to create filter templates that can be reused for deep-dive investigation. In addition, **Suggested queries** have been added to provide out-of-the-box investigation templates to filter your activities and discovered apps. The **Suggested queries** include custom filters to identify risks such as impersonation activities, administrator activities, risky non-compliant cloud storage apps, enterprise apps with weak encryption, and security risks. You can use the **Suggested queries** as a starting point, modify them as you see fit, and then save them as a new query. For more information, see [Activity filters and queries](activity-filters-queries.md) and [Discovered app filters and queries](discovered-app-queries.md).
 
- You can now check the current Cloud App Security service status by going [status.cloudappsecurity.com](https://status.cloudappsecurity.com) or directly from within the portal by clicking on **Help**>**System status**. 
 


## See Also  

For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  