---
# required metadata

title: Discover and manager Shadow IT | Microsoft Docs
description: This tutorial describes the process to automatically apply Azure Information Protection classification labels in Microsoft Cloud App Security.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 11/11/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

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

# Tutorial: Discover and manage shadow IT in your network

*Applies to: Microsoft Cloud App Security*

When IT admins are asked how many cloud apps they think their employees use, on average they say 30 or 40, when in reality, the average is over 1,000 separate apps being used by employees in your organization. Shadow IT helps you know and identify which apps are being used and what your risk level is. 80% of employees use non-sanctioned apps that no one has reviewed, and may not be compliant with your security and compliance policies. And because your employees are able to access your resources and apps from outside your corporate network, it's no longer enough to have rules and policies on your firewalls.

This tutorial provides instructions for using Cloud Discovery to discover which apps are being used, explore the risk of these apps, configure policies to identify new risky apps that are being used, and to unsanction these apps in order to block them natively using your proxy or firewall appliance.

> [!div class="checklist"]
>
> * Discover and identify Shadow IT
> * Evaluate and analyze
> * Manage your apps
> * Advanced Shadow IT discovery reporting
> * Control sanctioned apps

## How to discover and manage Shadow IT in your network

Use this process to roll out Shadow IT Cloud Discovery in your organization.

![shadow IT lifecycle](media/shadow-it-lifecycle.png)

### Phase 1: Discover and identify Shadow IT

1. **Discover Shadow IT**: Identify your organization's security posture by running Cloud Discovery in your organization to see what's actually happening in your network. For more information, see [Set up cloud discovery](set-up-cloud-discovery.md). This can be done using any of the following methods:

    * Get up and running quickly with Cloud Discovery by integrating with [Microsoft Defender ATP](wdatp-integration.md). This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.

    * For coverage on all devices connected to your network, it's important to deploy the [Cloud App Security log collector](discovery-docker.md) on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.

    * Integrate Cloud App Security with your proxy. Cloud App Security natively integrates with some third-party proxies, including [Zscaler](zscaler-integration.md).

Because policies are different across user groups, regions and business groups, you might want to create a dedicated Shadow IT report for each of these units. For more information, see [Docker on Windows on-premises](discovery-docker-windows.md#continuous-reports).

Now that Cloud Discovery is running on your network, look at the continuous reports that are generated and look at the [Cloud Discovery dashboard](working-with-cloud-discovery-data.md) to get a full picture of what apps are being used in your organization. It's a good idea to look at them by category, because you will often find that non-sanctioned apps are being used for legitimate work-related purposes that were not addressed by a sanctioned app.

1. **Identify the risk levels of your apps**: Use the Cloud App Security cloud app catalog to dive deeper into the risks that are involved with each discovered app. Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 80 risk factors. The risk factors start from general information about the app (where are the app's headquarters, who is the publisher), and through security measures and controls (support for encryption at rest, provides an audit log of user activity). For more information, see [Working with risk score](risk-score.md),

    * In the Cloud App Security portal, under **Discover**, click **Discovered apps**. Filter the list of apps discovered in your organization by the risk factors you are concerned about. For example, you can use the Advanced filters to find all apps with a risk score lower than 8.

    * You can drill down into the app to understand more about its compliance by clicking the app name and then clicking the **Info** tab to see details about the app's security risk factors.

### Phase 2: Evaluate and analyze

1. **Evaluate compliance**: Check whether the apps are certified as compliant with your organization's standards, such as HIPAA, SOC2, GDPR.

    * In the Cloud App Security portal, under **Discover**, click **Discovered apps**. Filter the list of apps discovered in your organization by the compliance risk factors you are concerned about. For example, use the suggested query to filter out non-compliant apps.

    * You can drill down into the app to understand more about its compliance by clicking the app name and then clicking the **Info** tab to see details about the app's compliance risk factors.

1. **Analyze usage**: Now that you know whether or not you want the app to be used in your organization, you want to investigate how and who is using it. If it's only used in a limited way in your organization maybe it's ok, but maybe if the use is growing you want to be notified about it so you can decide if you want to block the app.

    * In the Cloud App Security portal, under **Discover**, click **Discovered apps** and then drill down by clicking on the specific app you want to investigate. The **Use** tab lets you know how many active users are using the app and how much traffic it's generating. This can already give you a pretty good picture of what's happening with the app. Then, if you want to see who, specifically, is using the app, you can drill down further by clicking **Total active users**. This important step can give you pertinent information, for example, if you discover that all the users of a specific app are from the Marketing department, it's possible that there's a business need for this app, and if it's risky you should talk to them about an alternative before blocking it.

    * Dive even deeper when investigating use of discovered apps. View subdomains and resources to learn about specific activities, data access, and resource usage in your cloud services. For more information, see [Deep dive into Discovered apps](discovered-apps.md#deep-dive-into-discovered-apps) and [Discover resources and custom apps](discovered-apps.md#discover-resources-and-custom-apps).

1. Use the cloud app catalog and filter for apps that belong to the same app category and using the advanced filters identify solutions that do comply with the different security controls that are required in order to comply with your organization's policy.

### Phase 3: Manage your apps

* **Manage cloud apps**: Cloud App Security helps you with the process for managing app use in your organization. After you identified the different patterns and behaviors used in your organization, you can create new custom app tags in order to classify each app according to its business status or justification. These tags can be then used for specific monitoring purposes, for example, identify high traffic that is going to apps that are tagged as risky cloud storage apps. App tags can be managed under **Cloud Discovery settings** > **App tags**. These tags can then be used later for filtering in the Cloud Discovery pages and creating policies using them.

* **Continuous monitoring**: Now that you have thoroughly investigated the apps, you might want to set policies that monitor the apps and provide control where needed.

Now it's time to create policies so you can be automatically alerted when something happens that you're concerned about. For example, you might want to create an **App discovery policy** that lets you know when there is a spike in downloads or traffic from an app you're concerned about. To achieve this, you should enable **Anomalous behavior in discovered users policy**, **Cloud storage app compliance check**, and **New risky app**. You should also set the policy to notify you by email or text message. For more information, see [policy template reference](policy-template-reference.md),  more about [Cloud Discovery policies](cloud-discovery-policies.md) and Configure [App discovery policies](cloud-discovery-policies.md).

Look at the alerts page and use the **Policy type** filter to look at app discovery alerts. For apps that were matched by your app discovery policies, it is recommended that you do an advanced investigation to learn more about the business justification for using the app, for example, by contacting the users of the app. Then, repeat the steps in Phase 2 to evaluate the risk of the app. Then determine next steps for the application, whether you approve use of it in the future or want to block it the next time a user accesses it, in which case you should tag it as unsanctioned so it can be blocked using your firewall, proxy, or secure web gateway. For more information, see [Integrate with Microsoft Defender ATP](wdatp-integration.md), [Integrate with Zscaler](zscaler-integration.md), [Integrate with iboss](iboss-integration.md), and [Export a block script to govern discovered apps](governance-discovery.md#export-a-block-script-to-govern-discovered-apps).

### Phase 4: Advanced Shadow IT discovery reporting

In addition to the reporting options available in Cloud App Security, you can integrate Cloud Discovery logs into Azure Sentinel for further investigation and analysis. Once the data is in Azure Sentinel, you can view it in dashboards, run queries using Kusto query language, export queries to Microsoft Power BI, integrate with other sources, and create custom alerts. For more information, see [Azure Sentinel integration](siem-sentinel.md).

### Phase 5: Control sanctioned apps

1. To enable app control via APIs, [connect apps via API](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) for continuous monitoring.

2. Protect apps using [Conditional Access App Control](proxy-intro-aad.md).

The nature of cloud apps means that they are updated daily and new apps appear all the time. Because of this,  employees are continuously using new apps and it's important to keep tracking and reviewing and updating your policies, checking which apps your users are using, as well as their usage and behavior patterns. You can always go to the Cloud Discovery dashboard and see what new apps are being used, and follow the instructions in this article again to make sure your organization and your data are protected.

## See Also

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[!INCLUDE [Open support ticket](includes/support.md)]  
