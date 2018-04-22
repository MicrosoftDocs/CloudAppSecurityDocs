---
# required metadata

title: What is Cloud App Security? | Microsoft Docs
description: This topic describes Cloud App Security and how it works.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
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

*Applies to: Microsoft Cloud App Security*


# What is Microsoft Cloud App Security

> [!NOTE]
> For information about Advanced Security Management and Cloud App Security for Office 365, see [Get started with Advanced Security Management](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a).

Moving to the cloud increases flexibility for employees and reduces IT cost, but it also introduces new challenges and complexities for keeping your organization secure. To be able to get the full benefit of cloud applications, an IT team must find the right balance of supporting access while maintaining control, to protect critical data.  

Cloud App Security is a critical component of the Microsoft Cloud Security stack. It's a comprehensive solution that can help your organization as you move to take full advantage of the promise of cloud applications, but keep you in control, through improved visibility into activity. It also helps increase the protection of critical data across cloud applications. With tools that help uncover shadow IT, assess risk, enforce policies, investigate activities, and stop threats, your organization can more safely move to the cloud while maintaining control of critical data. 

## The Cloud App Security framework  

- **Cloud Discovery**: Discover all cloud use in your organization, including Shadow IT reporting and control and risk assessment.
    
- **Data Protection**: Monitor and control your data in the cloud by gaining visibility, enforcing DLP policies, alerting and investigation. 
    
- **Threat Protection**: Detect anomalous use and security incidents. Use behavioral analytics and advanced investigation tools to mitigate risk and set policies and alerts to achieve maximum control over network cloud traffic.

## Architecture  

Cloud App Security integrates visibility with your cloud by  

-   using Cloud Discovery to map and identify your cloud environment and the cloud apps your organization is using.
-   sanctioning and unsanctioning apps in your cloud.  
-   using easy-to-deploy app connectors that take advantage of provider APIs, for visibility and governance of apps that you connect to.  
-	using proxy protection to get real-time visibility and control over access and activities performed within your cloud apps.
-   helping you have continuous control by setting, and then continually fine-tuning, policies.  

![Cloud App Security architecture diagram](./media/proxy-architecture.png)  

### Data retention & Compliance

Cloud App Security is officially certified with Microsoft Compliance for ISO, HIPAA, CSA STAR, EU model clauses and more. To see the full list of certifications go to [Microsoft Compliance Offerings](https://go.microsoft.com/fwlink/?linkid=842039) and select Cloud App Security.  

When Cloud App Security performs content inspection, data privacy is enforced. The file content is not stored in the Cloud App Security database; only the metadata of the file records and any violations that were identified are stored in the Cloud App Security database. For more information about data retention, see our [privacy policy](http://go.microsoft.com/fwlink/?LinkId=512132) and the [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/You-are-in-control-of-your-data).
Cloud App Security retains data as follows: 
 
- Activity log: 180 days 
- Discovery data: 90 days 
- Alerts: 180 days 

After data is collected from these sources, Cloud App Security runs a sophisticated heuristic anomaly detection engine that profiles your environment and alerts you about anomalous activities with respect to the baseline learned, and gives you deep visibility into your cloud environment. You can configure a policy in Cloud App Security and use it to protect everything in your cloud environment.  

### Cloud Discovery  

Cloud Discovery uses your traffic logs to dynamically discover and analyze the cloud apps that your organization is using. To create a snapshot report of your organization's cloud use, you can manually upload log files from your firewalls or proxies for analysis. To set up continuous reports, use Cloud App Security log collectors to periodically forward your logs.  

For more information about Cloud Discovery, see [Set up Cloud Discovery](set-up-cloud-discovery.md).

### Sanctioning and unsanctioning an app  

You can use Cloud App Security to sanction or unsanction apps in your organization by using the *Cloud app catalog*. The Microsoft team of analysts has an extensive and continuously growing catalog of over 15,000 cloud apps that are ranked and scored based on industry standards. You can use the Cloud app catalog to rate the risk for your cloud apps based on regulatory certifications, industry standards, and best practices. Then, customize the scores and weights of various parameters to your organization's needs. Based on these scores, Cloud App Security lets you know how risky an app is based on over 60 risk factors that might affect your environment.  

### App connectors  
App connectors use APIs from cloud app providers to integrate the Cloud App Security cloud with other cloud apps. App connectors extend control and protection. They also give you access to information directly from cloud apps, for Cloud App Security analysis.  

To connect an app and extend protection, the app administrator authorizes Cloud App Security to access the app. Then, Cloud App Security queries the app for activity logs, and it scans data, accounts, and cloud content. Cloud App Security can enforce policies, detects threats, and provides governance actions for resolving issues.  

Cloud App Security uses the APIs provided by the cloud provider. Each app has its own framework and API limitations. Cloud App Security works with app providers to optimize the use of APIs, and to ensure the best performance. Considering the various limitations that apps impose on APIs (such as throttling, API limits, and dynamic time-shifting API windows), the Cloud App Security engines utilize the allowed capacity. Some operations, like scanning all files in the tenant, require a large number of APIs, so they are spread over a longer period. Expect some policies to run for several hours or several days.  

### Proxy protection
The Cloud App Security proxy gives you the tools you need to have real-time visibility and control over access to and activities performed within your cloud environment. With the proxy, you can protect your organization: 
-	Avoid data leaks by blocking downloads before they happen
-	Set rules that force data stored in and downloaded from the cloud to be protected with encryption
-	Gain visibility into unprotected endpoints so you can monitor what's being done on unmanaged devices
-	Control access from non-corporate networks or risky IP addresses

### Policy control  

You can use policies to define your users' behavior in the cloud. Use policies to detect risky behavior, violations, or suspicious data points and activities in your cloud environment. If needed, you can use policies to integrate remediation processes to achieve complete risk mitigation. Multiple types of policies correlate to the different types of information you might want to gather about your cloud environment and the types of remediation actions you might take.  

## Related Videos
- [Joining the security community](https://channel9.msdn.com/Shows/Microsoft-Security/Join-the-Security-Community)

## See Also  

Read about the basics in [Getting started with Cloud App Security](getting-started-with-cloud-app-security.md).    

Premier customers also can choose Cloud App Security directly from the [Premier portal](https://premier.microsoft.com/).   
