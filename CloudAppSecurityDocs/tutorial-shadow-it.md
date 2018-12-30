---
# required metadata

title: Discover and manager Shadow IT | Microsoft Docs
description: This tutorial describes the process to automatically apply Azure Information Protection classification labels in Microsoft Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/4/2019
ms.topic: tutorial
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: eac0b192-98d7-4939-9a07-1d4a7f8c39c3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dannyk
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
#Customer intent: As a sec op, I want to know and control which apps are used in my org so that I can harden my organization's security.
---
*Applies to: Microsoft Cloud App Security*


# Tutorial: Discover and manage shadow IT in your network

When IT admins are asked how many cloud apps they think their employees use, on average they say 30 or 40, when in reality, the average is over 1,000 separate apps being used by employees in your organization. Shadow IT helps you know and identify which apps are being used and what your risk level is. 80% of employees use non-sanctioned apps that no one has reviewed, and may not be compliant with your security and compliance policies. And because your employees are able to access your resources and apps from outside your corporate network, it's no longer enough to have rules and policies on your firewalls. 
Cloud App Security's Cloud Discovery enables:
- Discovery: Know what apps your users are using enables you to control and sanction what's being used, what's being shared, and how it's used. For example, one of the most common risks is users sharing corporate data from their personal email accounts. 

- Investigate: Gain visibility into what your users are doing in the cloud - this helps you shape how your employees use cloud apps and can be valuable when you investigate threats. For example, you might see someone connecting from an airport kiosk which isn't as secure as connecting within the corporate network, so you might want to let them access the data, but not download the data. 

- Identify threats: attackers can now gather information and data from the cloud without even entering your network, and malware can be sent through the cloud, for example malware sent to all users who sync with a directory in the cloud. 

- Control: Sanction and unsanction apps as needed, and control what should be done after you know what the risks are. You can set automated actions for what to do when users perform activities that are risky for your organization. For example, do you want to block or limit sharing or downloads of certain content or to certain devices? 

 
## How to discover and manage Shadow IT in your network

Use this process to roll out Shadow IT Cloud Discovery in your organization.

![shadow IT lifecycle](./media/shadow-it-lifecycle.png)

### Set up

### Phase 1: Discover and identify
    
1. **Discover Shadow IT**: Identify your organization's security posture: run Cloud Discovery in your organization to see what's actually happening in your network. 
  
    1. Integrate Cloud App Security with your proxy. Cloud App Security natively integrates with some third-party proxies, including [Zscaler](zscaler-integration.md).
    
    2. Get up and running quickly with Cloud Discovery by integrating with [Windows Defender ATP](wdatp-integration.md). This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.
   
    3. For coverage on all devices connected to your network, it's important to deploy the [Cloud App Security log collector](discovery-docker.md) on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.

    4. Now that Cloud Discovery is running on your network, look at the continuous reports that are generated and look at the Cloud Discovery dashboard to get a full picture of what apps are being used in your organization. It's a good idea to look at them by category, because you will often find that non-sanctioned apps are being used for legitimate work-related purposes that were not addressed by a sanctioned app.

2. **Identify the risk levels of your apps**: Use the Cloud App Security cloud app catalog to dive deeper into what the risks are that are involved with each discovered apps. Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors. The risk factors start from general information about the app (where are the app's headquarters, who is the publisher), and through security measures and controls (support for encryption at rest, provides an audit log of user activity).
    
   - In the Cloud App Security portal, under **Discover**, click **Discovered apps**. Filter the list of apps discovered in use in your organization by the risk factors you are concerned about. For example, you can use the Advanced filters to find all apps with a risk score lower than 8. 

   - You can drill down into the app to see understand more about its compliance by clicking the app name and then clicking the **Info** tab to see details about the app's security risk factors.
    
### Phase 2: Evaluate and analyze

1. **Evaluate compliance**: Check whether the apps are certified as compliant with your organization's standards, such as HIPAA, SOC2, GDPR.
   - In the Cloud App Security portal, under **Discover**, click **Discovered apps**. Filter the list of apps discovered in use in your organization by the compliance risk factors you are concerned about. For example, use the suggested query to filter out non-compliant apps.
   - You can drill down into the app to see understand more about its compliance by clicking the app name and then clicking the **Info** tab to see details about the app's compliance risk factors.

2. **Analyze usage**: Now that you know whether or not you want the app to be used in your organization, you want to investigate how and who is using it. If it's only used in a limited way in your organization maybe it's ok, but maybe if the use is growing you want to be notified about it so you can decide if you want to block the app.
    - In the Cloud App Security portal, under **Discover**, click **Discovered apps** and then drill down by clicking on the specific app you want to investigate. The **Use** tab lets you know how many active users are using the app and how much traffic it's generating. This can already give you a pretty good picture of what's happening with the app. Then, if you want to see who, specifically, is using the app, you can drill down further bu clicking **Total active users**. This important step can give you pertinent information, for example, if you discover that all the users of a specific app are from the Marketing department, it's possible that there's a business need for this app, and if it's risky you should talk to them about an alternative before blocking it.
3. Use the Cloud App Catalog to identify alternative solutions that can replace risky discovered apps.

### Phase 3: Manage your apps
    
- **Manage cloud apps**: Cloud App Security helps you with the process for managing app use in your organization - you might want to review use for a specific time period before deciding to block an app.
    
     - Now it's time to create policies so you can be automatically alerted when something happens that you're concerned about. For example, you might want to create an **Activity policy** that let's you know when there is a spike in downloads or traffic from an app you're concerned about. You can set the policy to notify you by email or text message. 

- **Continuous monitoring**: Now that you have thoroughly investigated the app, you want to set policies that monitor the apps and provide control where needed.

    1. Configure [**App discovery policies **](cloud-discovery-policies.md)
    2. [Connect apps via API](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) for continuous monitoring.
    3. Protect apps using [Conditional Access App Control](proxy-intro-aad.md).
     
## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  