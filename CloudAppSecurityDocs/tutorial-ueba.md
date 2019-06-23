---
# required metadata

title: Investigate risky users| Microsoft Docs
description: This tutorial describes the process to investigate risky users in Microsoft Cloud App Security, across hybrid environments, by integrating with Azure ATP.
keywords:
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 06/11/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
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

# Tutorial: Investigate risky users

*Applies to: Microsoft Cloud App Security*

Microsoft Cloud App Security integrates with Azure Advanced Threat protection to provided user entity behavioral analytics (UEBA)to enable deep investigation in your hybrid environment across both cloud app and on-premises activities. 

In a single portal, Cloud App Security now gives you all the information you need to make better decisions about risk across your organization, and actively remediate threats. By combining alerts and analyzing data from across these systems, Cloud App Security is the first place to start investigating users to gain identity-based insights across a hybrid environment:
- Microsoft Cloud App Security, which identifies attacks within a cloud session, covering not only Microsoft products but also third-party applications
- Azure Advanced Threat Protection, which uses behavioral analytics to identify attacks across your on-premises network
- Azure Active Directory Identity Protection, which detects and proactively prevents user and sign-in risks to identities in the cloud

Whether you start your investigation into user based on something risky you see in the Cloud App Security dashboard, or whether you are investigating a user who you may know has a motive that the system does not know about, start from the Cloud App Security dashboard to deep dive into risky users.  



This tutorial provides instructions for using Cloud Discovery to investigate risky users.

> [!div class="checklist"]
> * Prerequisites
> * Identify top risky users
> * Investigate a user
> * Understand user risk
> * Protect your organization


## Prerequisites

For complete user investigation across a hybrid environment, you must have:

- A valid license for Microsoft Cloud App Security
- A valid license for Azure ATP connected to your Active Directory instance
- Enable Cloud App Security to [integrate with your Azure ATP environment](aatp-integration.md) 

>[!NOTE]
>If you don't have a subscription for Azure ATP, you will still be able to use the Cloud App Security portal to investigate users, but you won't receive insights from your on-premises environment. You can also view Azure ATP insights in the Cloud App Security portal if you have an Azure ATP license but don't have a license for Microsoft Cloud App Security.


## Identify top risky users

To identify who your riskiest users are in Cloud App Security:

1. Go to the Cloud App Security dashboard and look at the people identified in the **Top users by investigation priority** tile, and then one by one go to their user page to investigate them. <br>The **investigation priority number**, found next to the user name, is a sum of all the user's risky activities over the last week. 

   ![Top users dashboard](./media/dashboard-top-users.png) 

2. Click on a particular user to get to the **User** page. 
   ![User page](./media/user-page.png) 

3. Click the **Investigation priority score** to view a list of all the risky activities that occurred over the last week to combine to give the user this particular score. 
4. Review the information in the **User** page to get an overview of the user and see if there are points at which the user  performed activities that were unusual for that user or were performed at an unusual time. The **User's score compared to the organization** represents which percentile the user is in based on their ranking in your organization - how high they are on the list of users you should investigate, relative to other users in your organization. The number will be red if a user is in or above the 90th percentile of risky users across your organization.<br>The **User** page helps you answer the questions:
	1. Who is the user?<br>Look at the left pane to get information about who the user is and what is known about them. This pane provides you with information about the user's role in your company and their department. Is the user a DevOps engineer who often performs unusual activities as part of their job? Is the user a disgruntled employee who just got passed over for a promotion?
	2. Is the user risky?<br>Check out the top of the right pane so you know whether it's worth your while to investigate the user. What is the employee's [risk score](#risk-score)?
	3. What's risk does the user present to your organization?<br>Look at the list in the bottom pane, which provides you with each activity and each alert related to the user to helps you start understanding what type of risk the user represents so you can start deeper investigation.

  >[!NOTE]
  >It is important to remember that while the **User** page provides information for devices, resources, and accounts across all activities, the investigation priority score is the sum of all risky activities and alerts over the last 7 days.
 
 
## Investigate a user
When something looks anomalous or there's a user you want to investigate, drill down into the alerts for the user. There may be small activities alone don't look like cause for alarm, but when Cloud App Security aggregates them together with other slightly concerning activities, make it possible for you to see that there is need for investigation.
 
When you investigate a user, you want to ask these questions about the activities and alerts you see:
- Do their activities make sense for their job?
- Look at the timeline, were the activities performed at times that makes sense?
- For each activity that you answered "no" to, drill down into the activity and in the **Activity log**, cross check this activity with other activities by the same user. There you can see whether there were other activities that were risky, where the user connected from, and you can very easily pivot to other drill downs, such as recent non-anomalous cloud and on-prem activities, to continue your investigation.


## Understand user risk <a name ="risk-score"></a>
    
Use the **Investigation priority score** to determine which users to investigate first. Cloud App Security builds user profiles for each user based on analytics that take time, peer groups, and expected user activity into consideration. Activity that is anomalous to a user's baseline is evaluated and scored. After scoring is complete, Microsoft's proprietary dynamic peer calculations and machine learning are run on the user activities to calculate the investigation priority for each user. 

The **Investigation priority score** provides you with the ability to detect both malicious insiders, and external attackers moving laterally in your organizations, without having to rely on standard deterministic detections.

Assessing the investigation urgency of each specific user, the Investigation priority score is based on security alerts, abnormal activities, and potential business and asset impact related to each user. 

If you click on the score value for an alert or an activity, you can view the evidence that explains how Cloud App Security scored the activity.

Every Azure AD user has a dynamic Investigation priority score, that is constantly updated based on recent behavior and impact, built from data evaluated from Azure ATP, Microsoft Cloud App Security as well as Azure AD Identity Protection. Your can now immediately understand the real top user threats by **Investigation priority score**, and then directly verify their business impact and investigate all related activities – no matter whether they are compromised, exfiltrating data or acting as insider threats.

Cloud App Security uses the following to measure risk: 

- **Alert scoring**<br>The alert score represents the potential impact of a specific alert on each user. Alert scoring is based on severity, user impact, alert popularity across users, and all entities in the organization.

- **Activity scoring**<br> The activity score determines the probability of a specific user performing a specific activity, based on behavioral learning of the user and their peers. Activities identified as the most abnormal receive the highest scores. 


## Protect your organization

If you see that a user is compromised, or you suspect there's a problem, it's time to take action.
- Directly from the Cloud App Security portal, you can click on the **User actions** control and set the user as high risk or suspend user.
- Alternatively, you can reset the user's password to block their access.
- If you drill down into an alert and determine that the activity should not have triggered an alert, in the [Activity drawer](activity-filters.md), click the **Send us feedback** link so that we can be sure to fine tune our alerting system with your organization in mind.
- After you remediate the issue, close the alert.


## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  
