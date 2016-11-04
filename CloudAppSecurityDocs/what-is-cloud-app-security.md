---
# required metadata

title: What is Cloud App Security | Microsoft Docs
description: Learn what Cloud App Security is and how it works.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: d46756b1-7dd8-4190-9799-3a97688f1266

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# What is Cloud App Security

> [!NOTE]
> For information about Advanced Security Management and Cloud App Security for Office 365, see [Get started with Advanced Security Management](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a).

Moving to the cloud increases flexibility for employees and reduces IT cost, but it also introduces new challenges and complexities for keeping your organization secure. To get the full benefit of cloud applications, an IT team must find the right balance of supporting access while maintaining control to protect critical data.  

Cloud App Security is a critical component of the Microsoft Cloud Security stack. It is a comprehensive solution that can helps your organization take full advantage of the promise of cloud applications, but maintain control, with improved visibility into activity. It also helps increase the protection of critical data across cloud applications. With tools to help uncover Shadow IT, assess risk, enforce policies, investigate activities, and stop threats, your organization can more safely move to the cloud while maintaining control of critical data.  

## The Cloud App Security framework  

|       |   |   |
|-------|---|:---|
|![Discover](./media/discovery-icon.png)|Discover|Uncover Shadow IT with Cloud App Security. Gain visibility by discovering apps, activities, users, data, and files in your cloud environment. Discover third-party apps that are connected to your cloud.|
|![Investigate](./media/investigate-icon.png)|Investigate|Investigate your cloud apps by using cloud forensics tools to deep-dive into risky apps, specific users, and files in your network. Find patterns in the data collected from your cloud. Generate reports to monitor your cloud.|
|![Control](./media/protect-icon.png)|Control|Mitigate risk by setting policies and alerts to achieve maximum control over network cloud traffic. Use Cloud App Security to migrate your users to safe, sanctioned cloud app alternatives.|
|![Protect](./media/protect-icon.png)|Protect|Use Cloud App Security to sanction or unsanction applications, enforce data loss prevention, control permissions and sharing, and generate custom reports and alerts.|


## Architecture  

Cloud App Security integrates visibility with your cloud in the following ways:  

-   Cloud Discovery maps and identifies your cloud environment and the cloud apps your organization is using  
-   Sanctions and unsanctions apps in your cloud  
-   Gives you visibility and governance of apps you connect to by using easy-to-deploy app connectors that take advantage of provider APIs  
-   Gives you continuous control by enabling you to set and then continually fine-tune policies.  

![Cloud App Security architecture](./media/architecture.png)  

> [!NOTE]  
>  When Cloud App Security performs content inspection, data privacy is enforced. Only the metadata of the file records and the violations that were identified are stored in the Cloud App Security database. Your data is not stored in the Cloud App Security database. For more information about data retention, see our [privacy policy](http://go.microsoft.com/fwlink/?LinkId=512132) and the [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/You-are-in-control-of-your-data).
Cloud App Security retains data as follows:
>- Activity log: 180 days
>- Discovery data: 90 days
>- Alerts: unlimited

After data is collected from these sources, Cloud App Security runs sophisticated analysis on the data. It immediately alerts you to anomalous activities, and gives you deep visibility into your cloud environment. You can configure a policy in Cloud App Security and use it to protect everything in your cloud environment.  

###  How Cloud Discovery works  

Cloud Discovery uses your traffic logs to dynamically discover and analyze the cloud apps that your organization is using. To create a snapshot report of your organization's cloud use, you can manually upload log files from your firewalls or proxies for analysis. To set up continuous reports, use Cloud App Security's log collectors to periodically forward your logs.  

For more information about Cloud Discovery, see [Set up Cloud Discovery](set-up-cloud-discovery.md).

### How sanctioning and unsanctioning an app works  

You can use Cloud App Security to sanction or unsanction apps in your organization by using the *Cloud app catalog*.  The Microsoft team of analysts has an extensive and continuously growing catalog of over 13,000 cloud apps that are ranked and scored based on industry standards. Use the Cloud app catalog to rate the risk for your cloud apps based on regulatory certifications, industry standards, and best practices. Then, customize the scores and the weights of various parameters to your organization's needs. Based on these scores, Cloud App Security lets you know how risky an app is according to over 50 risk factors that might affect your environment.  

### How app connectors work  
App connectors use APIs from cloud app providers to integrate the Cloud App Security cloud with other cloud apps and to extend control and protection. This enables Cloud App Security to pull information directly out of cloud apps for analysis.  

To connect an app and extend protection, the app administrator authorizes Cloud App Security to access the app, and then Cloud App Security queries the app for activity logs, and scans data, accounts, and cloud content. Cloud App Security then enforces policies, detects threats, and provides governance actions for resolving issues.  

Cloud App Security uses the APIs provided by the cloud provider. Each app has its own framework and API limitations. Cloud App Security works with app providers to optimize the use of the APIs and to ensure the best performance. Taking into account the varying limitations apps impose on APIs (such as throttling, API limits, and dynamic time-shifting API windows), the Cloud App Security engines utilize the allowed capacity. Some operations, such as scanning all files in the tenant, require a large amount of APIs and therefore are spread over a longer period. Expect some policies to run for several hours or several days.  

### How policy control works  

You can use policies to define your users' behavior in the cloud. Use policies to detect risky behavior, violations, or suspicious data points and activities in your cloud environment. If needed, you can use policies to integrate remediation processes to achieve complete risk mitigation. Multiple types of policies correlate to the different types of information you want to gather about your cloud environment and the types of remediation actions you might want to take.  

## See Also  

[Getting started with Cloud App Security](getting-started-with-cloud-app-security.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
