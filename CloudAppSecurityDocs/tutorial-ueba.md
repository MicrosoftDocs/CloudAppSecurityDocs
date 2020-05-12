---
# required metadata

title: Investigate risky users| Microsoft Docs
description: This tutorial describes the process to investigate risky users in Microsoft Cloud App Security, across hybrid environments, by integrating with Azure ATP.
keywords:
author: shsagir
ms.author: shsagir
ms.date: 04/28/2020
ms.topic: tutorial
ms.collection: M365-security-compliance
ms.service: cloud-app-security

# optional metadata

#ROBOTS:
ms.reviewer: dannyk
ms.suite: ems

#Customer intent: As a sec op, I want to know and control which apps are used in my org so that I can harden my organization's security.
---

# Tutorial: Investigate risky users

*Applies to: Microsoft Cloud App Security*

Security operations teams are challenged to monitor user activity, suspicious or otherwise, across all dimensions of the identity attack surface, using multiple security solutions that often are not connected. While many companies now have hunting teams to proactively identify threats in their environments, knowing what to look for across the vast amount of data can be a challenge. Microsoft Cloud App Security now simplifies this by taking away the need to create complex correlation rules, and lets you look for attacks that span across your cloud and on-premises network.

To help you focus on user identity, Microsoft Cloud App Security provides user entity behavioral analytics (UEBA) in the cloud. This can be extended to your on-premises environment by integrating with Azure Advanced Threat Protection (ATP). After you integrate with Azure ATP, you will also gain context around user identity from its native integration with Active Directory.

Whether your trigger is an alert you see in the Cloud App Security dashboard, or whether you have information from a third-party security service, start your investigation from the Cloud App Security dashboard to deep dive into risky users.

This tutorial provides instructions for using Cloud App Security to investigate risky users.

> [!div class="checklist"]
>
> * 1: [Connect to the apps you want to protect](#connect-apps-protect)
> * 2: [Identify top risky users](#identify)
> * 3: [Further investigate users](#investigate)
> * 4: [Protect your organization](#protect)

## Understand the investigation priority score<a name="risk-score"></a>

The investigation priority score is a score Cloud App Security gives to each user to let you know how risky a user is relative to other users in your organization.

Use the **Investigation priority score** to determine which users to investigate first. Cloud App Security builds user profiles for each user based on analytics that take time, peer groups, and expected user activity into consideration. Activity that is anomalous to a user's baseline is evaluated and scored. After scoring is complete, Microsoft's proprietary dynamic peer calculations and machine learning are run on the user activities to calculate the investigation priority for each user.

The **Investigation priority score** provides you with the ability to detect both malicious insiders, and external attackers moving laterally in your organizations, without having to rely on standard deterministic detections.

The investigation priority score is based on security alerts, abnormal activities, and potential business and asset impact related to each user to help you assess how urgent it is to investigate each specific user.

If you click on the score value for an alert or an activity, you can view the evidence that explains how Cloud App Security scored the activity.

Every Azure AD user has a dynamic investigation priority score, that is constantly updated based on recent behavior and impact, built from data evaluated from Azure ATP, Microsoft Cloud App Security as well as Azure AD Identity Protection. You can now immediately understand who the real top risky users are, by filtering according to **Investigation priority score**, directly verify what their business impact is, and investigate all related activities – whether they are compromised, exfiltrating data, or acting as insider threats.

Cloud App Security uses the following to measure risk:

* **Alert scoring**  
The alert score represents the potential impact of a specific alert on each user. Alert scoring is based on severity, user impact, alert popularity across users, and all entities in the organization.

* **Activity scoring**  
The activity score determines the probability of a specific user performing a specific activity, based on behavioral learning of the user and their peers. Activities identified as the most abnormal receive the highest scores.

## Phase 1: Connect to the apps you want to protect<a name="connect-apps-protect"></a>

1. Connect at least one app to Microsoft Cloud App Security using the [API connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md). We recommend that you start by connecting [Office 365](connect-office-365-to-microsoft-cloud-app-security.md).
1. Connect additional apps using the [proxy to achieve conditional access app control](proxy-deployment-aad.md).
1. To enable insights across your on-premises environment, configure Cloud App Security to [integrate with your Azure ATP environment](aatp-integration.md).

## Phase 2: Identify top risky users<a name="identify"></a>

To identify who your riskiest users are in Cloud App Security:

1. Go to the Cloud App Security dashboard and look at the people identified in the **Top users by investigation priority** tile, and then one by one go to their user page to investigate them.  
The **investigation priority number**, found next to the user name, is a sum of all the user's risky activities over the last week.

   ![Top users dashboard](./media/dashboard-top-users.png)

1. Click on a particular user to get to the **User** page.
    ![User page](./media/user-page.png)

1. Review the information in the User page to get an overview of the user and see if there are points at which the user  performed activities that were unusual for that user or were performed at an unusual time. The **User's score compared to the organization** represents which percentile the user is in based on their ranking in your organization - how high they are on the list of users you should investigate, relative to other users in your organization. The number will be red if a user is in or above the 90th percentile of risky users across your organization.  
The User page helps you answer the questions:
    * Who is the user?  
    Look at the left pane to get information about who the user is and what is known about them. This pane provides you with information about the user's role in your company and their department. Is the user a DevOps engineer who often performs unusual activities as part of their job? Is the user a disgruntled employee who just got passed over for a promotion?

    * Is the user risky?  
    Check out the top of the right pane so you know whether it's worth your while to investigate the user. What is the employee's [risk score](#risk-score)?
    * What's risk does the user present to your organization?  
    Look at the list in the bottom pane, which provides you with each activity and each alert related to the user to help you start understanding what type of risk the user represents. In the timeline, click on each line so you can drill down deeper into the activity or alert itself. You can click also on the number next to the activity so that you can understand the evidence that influenced the score itself.
    * What's the risk to other assets in your organization?  
    Select the **Lateral movement paths** tab to understand which paths an attacker can use to gain control of other assets in your organization. For example, even if the user you are investigating has a non-sensitive account, an attacker can use connections to the account to discover and attempt to compromise sensitive accounts in your network. For more information, see [Use Lateral Movement Paths](/azure-advanced-threat-protection/investigate-lateral-movement-path).

  >[!NOTE]
  >It is important to remember that while the User page provides information for devices, resources, and accounts across all activities, the investigation priority score is the sum of all risky activities and alerts over the last 7 days.

## Phase 3: Further investigate users<a name="investigate"></a>

When you investigate a user based on an alert or if you saw an alert in an external system, there may be activities which alone may not be cause for alarm, but when Cloud App Security aggregates them together with other activities, the alert may be an indication of a suspicious event.

When you investigate a user, you want to ask these questions about the activities and alerts you see:

* Is there a business justification for this employee to perform these activities? For example, if someone from Marketing is accessing the code base, or someone from Development accesses the Finance database, you should follow up with the employee to make sure this was an intentional and justified activity.

* Go to the **Activity log** to understand why this activity received a high score while others did not. You can set the **Investigation priority** to **Is set** to understand which activities are suspicious. For example, you can filter based on Investigation priority for all activities that occurred in Ukraine. Then you can see whether there were other activities that were risky, where the user connected from, and you can very easily pivot to other drill downs, such as recent non-anomalous cloud and on-prem activities, to continue your investigation.

## Phase 4: Protect your organization<a name="protect"></a>j

If your investigation leads you to the conclusion that a user is compromised, follow these steps to mitigate the risk.

* Contact the user – Using the user contact information integrated with Cloud App Security from Active Directory, you can drill down into each alert and activity to resolve the user identity. Make sure the user is familiar with the activities.

* Directly from the Cloud App Security portal, click on the **User actions** control and choose whether to require the user to sign in again, suspend the user, or confirm user compromised.

* In case of a compromised identity, you can ask the user to reset their password, making sure the password meets best practice guidelines for length and complexity.
* If you drill down into an alert and determine that the activity should not have triggered an alert, in the [Activity drawer](activity-filters.md), click the **Send us feedback** link so that we can be sure to fine tune our alerting system with your organization in mind.
* After you remediate the issue, close the alert.

## See Also

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[!INCLUDE [Open support ticket](includes/support.md)]
