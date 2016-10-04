---
title: "What is Microsoft Cloud App Security?"
ms.custom: na
ms.date: "08/18/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
applies_to: 
  - "Microsoft Cloud App Security"
ms.assetid: d46756b1-7dd8-4190-9799-3a97688f1266
caps.latest.revision: 43
author: "Rkarlin"
ms.author: "rkarlin"
manager: "stevenpo"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "hu-hu"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "nl-nl"
  - "pl-pl"
  - "pt-br"
  - "pt-pt"
  - "ru-ru"
  - "sv-se"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# What is Microsoft Cloud App Security?
 For information about Advanced Security Management - Cloud App Security capabilities in Office 365, see Get started with [Advanced Security Management](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a). 
 
  While moving to the cloud has increased flexibility for employees and reduced IT cost, it has also introduced new complexity and challenges for keeping your organization secure. To realize the full benefit of cloud applications, IT teams must find the right balance of enabling access while maintaining control to protect critical data.  
  
 [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] is a critical component of the Microsoft Cloud Security stack. It is a comprehensive solution that helps organizations take full advantage of the promise of cloud applications while maintaining control with improved visibility into activity. It also increases protection of critical data across cloud applications. With tools to help uncover Shadow IT, assess risk, enforce policies, investigate activities and stop threats, organizations can safely move to the cloud while maintaining control of critical data.  
  
## The Cloud App Security framework  
  
||||  
|-|-|-|  
|![Discovery icon](../migration/media/discovery-icon.png "Discovery icon")|Discover|Uncover Shadow IT with [!INCLUDE[Adallom](../migration/includes/adallom_md.md)]. Gain visibility by discovering apps, activities, users, data and files in your cloud environment as well as third-party apps that are connected to your cloud.|  
|![investigate icon](../migration/media/investigate-icon.png "investigate icon")|Investigate|Investigate your cloud apps using cloud forensics tools to deep-dive into risky apps, specific users and files in your network as well as finding patterns in the data collected from your cloud and generating reports to monitor your cloud.|  
|![Protect icon](../migration/media/protect-icon.png "Protect icon")|Control|Mitigate risk by setting policies and alerts in order to achieve maximum control over network cloud traffic. Use [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] to migrate your users to safe, sanctioned cloud app alternatives.|  
|![](../Image/protect%20icon.png)|Protect|Use [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] to sanction/unsanction applications, enforce data loss prevention (DLP), control permissions and sharing, and generate custom reports and alerts.|  
  
## Architecture  
 [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] enables visibility integration with your cloud in the following ways:  
  
-   Visibility using Cloud Discovery to map and identify your cloud environment, and the cloud apps you have in use.  
  
-   Ability to sanction and unsanction apps in your cloud.  
  
-   Visibility and governance of apps you connect to using our easy-to-deploy app connectors that leverage provider APIs.  
  
-   Continuous control by enabling you to set and then continually fine-tune policies.  
  
 ![Architecture](../migration/media/architecture.png "Architecture")  
  
> [!NOTE]  
>  When [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] performs content inspection, data privacy is enforced. Your data is not stored in the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] data base, only the metadata of the file records and the violations that were identified. See our [privacy policy](http://go.microsoft.com/fwlink/?LinkId=512132)  and the [Microsoft Trust Center](https://www.microsoft.com/en-us/TrustCenter/Privacy/You-are-in-control-of-your-data) for more information about data retention.
Cloud App Security retains data as follows:
>- Activity log: 180 days
>- Discovery data: 90 days
>- Alerts: unlimited 

   
  
 After data is collected from these sources, [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] runs sophisticated analysis on it, alerting you right away to anomalous activities, and providing you with deep visibility. You can then configure a policy in [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] and then use it to protect everything in your cloud environment.  
  
###  <a name="cloud_discovery_list"></a> How Cloud Discovery works  
 Cloud Discovery uses your traffic logs to dynamically discover and analyze which cloud apps are in use in your organization.  
  
 You can either create a snapshot report of your organization's cloud use, by manually uploading log files from your firewalls or proxies for analysis, or you can set up continuous reports by using Cloud App Security's log collectors to forward your logs periodically.  

For more information about Cloud Discovery, see [How Cloud Discovery works](../migration/how-cloud-discovery-works.md).
 
  
### How sanctioning and unsanctioning an app works  
 [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] enables you to sanction/unsanction apps in your organization, using our **Cloud app catalog**.  
  
 The Microsoft team of analysts has an extensive, and continuously growing, catalog of over 13,000 cloud apps that are ranked and scored based on industry standards. The **Cloud app catalog** rates risk for your cloud apps based on regulatory certifications, industry standards, and best practices. You can then customize the scores and the weights of various parameters to your organization's needs. Based on these scores, [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] lets you know how risky the app is according to over 50 risk factors that might affect your environment.  
  
### How App Connectors work  
 App connectors leverage APIs provided by various cloud apps providers to enable the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] cloud to integrate with other clouds apps and extend control and protection. This enables [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] to pull information directly out of cloud apps for analysis.  
  
 In order to connect an app and extend protection, the app administrator authorizes [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] to access the app, and then [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] queries the app for activity logs, scans data and accounts and cloud content. [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] can then enforce policies, detect threats and provide governance actions for resolving issues.  
  
 [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] leverages the APIs provided by the cloud provider, each app has its own framework and API limitations. [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] works with the app providers to optimize the use of the APIs and to ensure the best performance. Taking into account the different limitations the apps impose on the APIs (such as throttling, API limits, dynamic time-shifting API windows, etc.), the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] engines leverage the allowed capacity. Some operations, such as scanning of all files in the tenant, require a large amount of APIs and therefore are spread over a longer period. Expect some policies to run for several hours or several days.  
  
### How policy control works  
 Policies allow you to define the way you want your users to behave in the cloud. They enable you to detect risky behavior, violations or suspicious data points and activities in your cloud environment, and if required, to integrate remediation processes to achieve complete risk mitigation. There are multiple types of policies that correlate to the different types of information you want to gather about your cloud environment and the types of remediation actions you may want to take.  
  
## See Also  
 [Getting started with Cloud App Security](../migration/getting-started-with-cloud-app-security.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  