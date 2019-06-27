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

Security operations teams are challenged to monitor user activity, suspicious or otherwise, across all dimensions of the identity attack surface, using multiple security solutions that often are not connected.

In order to enable you to better focus on user identity, Microsoft Cloud App Security integrates with Azure Advanced Threat Protection (ATP) to provided user entity behavioral analytics (UEBA).

While many companies now have hunting teams to proactively identify threats in their environments, knowing what to look for across the vast amount of data can be a challenge. Microsoft Cloud App Security now simplifies this by taking away the need to create complex correlation rules, and lets you look for attacks that span across your cloud and on-premises network.

Whether you start your investigation into a user based on something risky you see in the Cloud App Security dashboard, or whether you're investigating a user who you may know has a motive that the system does not know about, start from the Cloud App Security dashboard to deep dive into risky users.  

This tutorial provides instructions for using Cloud Discovery to investigate risky users.

> [!div class="checklist"]
> * Prerequisites
> * Identify top risky users
> * Investigate a user
> * Understand user risk
> * Protect your organization


## Prerequisites

For complete user investigation across a hybrid environment, you must have a valid license for Azure ATP connected to your Active Directory instance and Cloud App Security must be configured to [integrate with your Azure ATP environment](aatp-integration.md).

>[!NOTE]
>If you don't have a subscription for Azure ATP, you will still be able to use the Cloud App Security portal to investigate users, but you won't receive insights from your on-premises environment. You can also view Azure ATP insights in the Cloud App Security portal if you have an Azure ATP license but don't have a license for Microsoft Cloud App Security.


## Understand the investigation priority score <a name ="risk-score"></a>

The investigation priority score is a score Cloud App Security gives to each user to let you know how risky a user is relative to other users in your organization.
    
Use the **Investigation priority score** to determine which users to investigate first. Cloud App Security builds user profiles for each user based on analytics that take time, peer groups, and expected user activity into consideration. Activity that is anomalous to a user's baseline is evaluated and scored. After scoring is complete, Microsoft's proprietary dynamic peer calculations and machine learning are run on the user activities to calculate the investigation priority for each user. 

The **Investigation priority score** provides you with the ability to detect both malicious insiders, and external attackers moving laterally in your organizations, without having to rely on standard deterministic detections.

Assessing the investigation urgency of each specific user, the Investigation priority score is based on security alerts, abnormal activities, and potential business and asset impact related to each user. 

If you click on the score value for an alert or an activity, you can view the evidence that explains how Cloud App Security scored the activity.

Every Azure AD user has a dynamic Investigation priority score, that is constantly updated based on recent behavior and impact, built from data evaluated from Azure ATP, Microsoft Cloud App Security as well as Azure AD Identity Protection. Your can now immediately understand who the real top risky users are by **Investigation priority score**, and then directly verify their business impact and investigate all related activities – no matter whether they are compromised, exfiltrating data or acting as insider threats.

Cloud App Security uses the following to measure risk: 

- **Alert scoring**<br>The alert score represents the potential impact of a specific alert on each user. Alert scoring is based on severity, user impact, alert popularity across users, and all entities in the organization.

- **Activity scoring**<br> The activity score determines the probability of a specific user performing a specific activity, based on behavioral learning of the user and their peers. Activities identified as the most abnormal receive the highest scores. 

## Identify top risky users

To identify who your riskiest users are in Cloud App Security:

1. Go to the Cloud App Security dashboard and look at the people identified in the **Top users by investigation priority** tile, and then one by one go to their user page to investigate them. <br>The **investigation priority number**, found next to the user name, is a sum of all the user's risky activities over the last week. 

   ![Top users dashboard](./media/dashboard-top-users.png) 

2. Click on a particular user to get to the **User** page. 
   ![User page](./media/user-page.png) 

3. Click the **Investigation priority score** to view a list of all the risky activities that occurred over the last week to combine to give the user this particular score. 
4. Review the information in the **User** page to get an overview of the user and see if there are points at which the user  performed activities that were unusual for that user or were performed at an unusual time. The **User's score compared to the organization** represents which percentile the user is in based on their ranking in your organization - how high they are on the list of users you should investigate, relative to other users in your organization. The number will be red if a user is in or above the 90th percentile of risky users across your organization.<br>The **User** page helps you answer the questions:
	1. Who is the user?<br>Look at the left pane to get information about who the user is and what is known about them. This pane provides you with information about the user's role in your company and their department. Is the user a DevOps engineer who often performs unusual activities as part of their job? Is the user a disgruntled employee who just got passed over for a promotion?
	2. Click on the activity or alert score to understand the reason this activity was considered anomalous.
  2. Is the user risky?<br>Check out the top of the right pane so you know whether it's worth your while to investigate the user. What is the employee's [risk score](#risk-score)?
	3. What's risk does the user present to your organization?<br>Look at the list in the bottom pane, which provides you with each activity and each alert related to the user to helps you start understanding what type of risk the user represents so you can start deeper investigation.

  >[!NOTE]
  >It is important to remember that while the **User** page provides information for devices, resources, and accounts across all activities, the investigation priority score is the sum of all risky activities and alerts over the last 7 days.
 
 
## Investigate a user

When you investigate a user based on an alert or if you saw an alert in an external system, there may be activities which alone may not be cause for alarm, but when Cloud App Security aggregates them together with other activities, the alert may be an indication of a suspicious event.
 
When you investigate a user, you want to ask these questions about the activities and alerts you see:
- Is there a business justification for this employee to perform these activities? For example, if someone from Marketing is accessing the code base, or someone from Development accesses the Finance database, you should follow up with the employee to make sure this was an intentional and justified activity.

- Go to the **Activity log** to understand why this activity received a high score while others did not. You can also filter by all scored activities. You can filter the activities based on **Activity priority**. For example, you can filter based on Activity priority for all activities that occurred in Ukraine. Then you can see whether there were other activities that were risky, where the user connected from, and you can very easily pivot to other drill downs, such as recent non-anomalous cloud and on-prem activities, to continue your investigation.




## Protect your organization

If you see that a user is compromised, or you suspect there's a problem, it's time to take action.

After you finish investigation, you will want to contact the user – all the user’s contact information from Azure Active Directory is added to Cloud App Security so that you can see who performed each activity. Make sure the user is familiar with the activities.


- Directly from the Cloud App Security portal, you can click on the **User actions** control and set the user as high risk or suspend user.
- In case of a compromised identity, you can ask the user to reset their password, and make sure the password is complex enough to be more difficult to hack.
- If you drill down into an alert and determine that the activity should not have triggered an alert, in the [Activity drawer](activity-filters.md), click the **Send us feedback** link so that we can be sure to fine tune our alerting system with your organization in mind.
- After you remediate the issue, close the alert.


## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  
