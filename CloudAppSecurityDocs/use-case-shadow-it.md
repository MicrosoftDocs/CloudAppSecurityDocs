---
# required metadata

title: Discover and manage Shadow IT | Microsoft Docs
description: This topic walks you through a tutorial about how to discover and manage Shadow IT using Cloud Discovery in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/30/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 5f29ae97-7cc7-455e-9112-3c44b855dc2f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dannyk
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
*Applies to: Microsoft Cloud App Security*


# Discover and manage shadow IT in your network

When IT admins are asked how many cloud apps they think their employees use, on average they say 30 or 40, when in reality, the average is over 1,000 separate cloud apps being used by employees in your organization. Discovering and managing shadow IT helps you know and identify which applications are being used and what your risk level is. 80% of employees use non-sanctioned cloud apps that no one has reviewed, and may not be compliant with your security and compliance policies. And even if they are, because your employees are able to access your resources and cloud apps from outside your corporate network, it's no longer enough to set rules and policies on your firewalls. 

Cloud App Security's Cloud Discovery enables:

- Discovery: Know what cloud apps your users are using, what's being used, what's being shared, and how it's used. For example, one of the most common risks is users sharing corporate data from their personal email accounts. 

- Investigate: Gain visibility into which apps your users are using in the cloud - this helps you shape how your employees use cloud applications and can be valuable when you investigate threats. For example, you might see someone connecting from an airport kiosk which isn't as secure as connecting within the corporate network, so you might want to let them access the data, but not download the data. 

- Manage and Control: Sanction and unsanction cloud apps as needed, and control what should be done after you know what the risks are. 

 
## How to discover Shadow IT in your network

Use this process to roll out Shadow IT Cloud Discovery in your organization.

![shadow IT lifecycle](./media/shadow-it-lifecycle.png)

### Prerequisites

### Phase 1: Discover and identify
    
1. **Discover Shadow IT**: Identify your organization's security posture: run Cloud Discovery in your organization to see what's actually happening in your network. 
    a. The easiest way to get up and running quickly with Cloud Discovery is to integrate with [Windows Defender ATP](wdatp-integration.md). This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.
    b. For coverage on all devices connected to your network, it's important to deploy the [Cloud App Security log collector](discovery-docker.md) on your firewalls and proxies to collect data from your endpoints and send it to Cloud App Security for analysis.
    c. Now that Cloud Discovery is running on your network, you can look at the continuous reports that are generated and look at the Cloud Discovery dashboard to get a full picture of what cloud apps are being used in your organization. It's a good idea to look at them by category, because you will often find that non-sanctioned cloud apps are being used for legitimate work-related purposes that were not addressed by a sanctioned app.

2. **Identify the risk levels of your cloud apps**: Use the Cloud App Security cloud app catalog to dive deeper into what the risks are that are involved with each discovered cloud apps. Cloud App Security's risk catalog includes over 16,000 applications that are assessed using over 70 risk factors. The risk factors start from general information about the app (where are the app's headquarters, who is the publisher), and through security measures and controls (support for encryption at rest, provides an audit log of user activity).
    
   - In the Cloud App Security portal, under **Discover**, click **Discovered apps**. Filter the list of cloud apps discovered in use in your organization by the risk factors you are concerned about. For example, you can use the Advanced filters to find all cloud apps with a risk score lower than 4. 

   - You can drill down into the app to see understand more about its compliance by clicking the app name and then clicking the **Info** tab to see details about the app's security risk factors.
### Phase 2: Evaluate and analyze

1. **Evaluate compliance**: Check whether the cloud apps are certified as compliant with your organization's standards, such as HIPAA, SOC2, GDPR.
   - In the Cloud App Security portal, under **Discover**, click **Discovered apps**. Filter the list of cloud apps discovered in use in your organization by the compliance risk factors you are concerned about. For example, use the suggested query that filters out non-GDPR compliant cloud apps.
   - You can drill down into the app to see understand more about its compliance by clicking the app name and then clicking the **Info** tab to see details about the app's compliance risk factors.

2. **Analyze usage**: Now that you know whether or not you want the app to be used in your organization, you want to investigate how and who is using it. If it's only used in a limited way in your organization maybe it's ok, but maybe if the use is growing you want to be notified about it so you can decide if you want to block the app.
    - In the Cloud App Security portal, under **Discover**, click **Discovered apps** and then drill down by clicking on the specific app you want to investigate. The **Use** tab lets you know how many active users are using the app and how much traffic it's generating. This can already give you a pretty good picture of what's happening with the app. Then, if you want to see who, specifically, is using the app, you can drill down further by clicking **Total active users**. This important step can give you pertinent information, for example, if you discover that all the users of a specific app are from the Marketing department, it's possible that there's a business need for this app, and if it's risky you should talk to them about an alternative before blocking it.
    
### Phase 3: Continuous monitoring
    
1. **Manage cloud apps**: Cloud App Security helps you with the process for managing app use in your organization - you might want to review use for a specific time period before deciding to block an app.
    
     1. Now it's time to create policies so you can be automatically alerted when something happens that you're concerned about. For example, you might want to create an **App discovery policy** that let's you know when there is a spike in downloads or traffic from an app you're concerned about. You can set the policy to notify you by email or text message. 

2. **Continuous monitoring**: Now that you have thoroughly investigated the app, you want to check your alerts regularly, and perform a periodic review of the PDF reports provided by Cloud App Security.


     
## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  