---
# required metadata

title: Daily activities to protect your cloud environment | Microsoft Docs
description: This article provides a foundation for what you must do in Cloud App Security on a regular basis to monitor cloud app use in your organization.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: a835fa24-15c5-4bbb-a25a-688444040f1f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Daily activities to protect your cloud environment
After you get Cloud App Security up and running, you will need to configure data streams, sanction apps you want to allow people to use, and set up policies to monitor your cloud environment. Then you can use Cloud App Security to control and protect your cloud and manage risk.  

This topic describes what you should do With Cloud App Security on a daily basis.  

## Check the dashboard  
The Cloud App Security dashboard provides you with an overview of activities and features, including:

- Open alerts
- Activity violations
- Content violations
- An activity map that plots where user activity originates
- Connected app usage trends in your cloud environment  

We recommend that you check the dashboard on a daily basis to see what new alerts have been triggered. It is also a good place to keep an eye on the health of your cloud environment to get a sense of what's happening across your cloud environment.  

![Cloud App Security dashboard](./media/dashboard.png "dashboard")  

## Handle your alerts  
Alerts are the entry points to understanding your cloud environment more deeply. You may want to create new policies based on what you find. For example, you might see an administrator signing in from an unknown location. You can create a policy that automatically suspends an admin account when it is used to sign in from that location.  

It is a good idea to review all of your alerts and to use them as tools for modifying your policies. If harmless events are being considered violations to existing policies, you should refine your policies so that you receive fewer unnecessary alerts.  

-   Under **Open alerts**, click **View all alerts**.  

     This section of the dashboard provides full visibility into any suspicious activity or violation of your established policies. It then helps you safeguard the security posture you defined for your cloud environment.  

     ![Alerts](./media/alerts.png "alerts")  

-   For each alert, you need to investigate and determine the nature of the violation and the required response.  

     You can filter the alerts by Alert type or by Severity in order to process the most important ones first.  

     Select a specific alert. Depending on what type of alert it is, you will receive various actions that can be taken before resolving the alert.  

     There are three types of violations you will need to deal with when investigating alerts:  

    #### Serious violations
     Serious violations require immediate response.

         Examples:  

         For a suspicious activity alert, you might want to suspend the account until the user changes their password.  

         For a data leak you might want to restrict permissions or quarantine the file.  

         If a new, unsanctioned service is discovered, you might want to block access to the service on your proxy or firewall.  

    #### Questionable violations
    Questionable violations require further investigation.  

         You can contact the  user or the user's manager about the nature of the activity.  

         Leave the activity open until you have more information.  

 #### Authorized violations or anomalous behavior
 Authorized violations or anomalous behavior can result from legitimate use.  

         Dismiss the alert.  

-   When you finish this process, mark the alert as resolved.  

The following table provides a list of the types of alerts that can be triggered and recommends ways in which you can resolve them.  

|Alert type|Description|Recommended resolution|  
|----------------|-----------------|----------------------------|  
|Activity policy violation|This type of alert is the result of a policy you created.|To work with this type of alert in bulk, we recommend that you work in the Policy center to mitigate them.<br /><br /> Fine-tune the policy to exclude noisy entities by adding more filters and more granular controls.<br /><br /> If the policy is very accurate, the alert is warranted, and it's a violation you want to stop immediately, consider adding automatic remediation in the policy.|  
|File policy violation|This type of alert is the result of a policy you created.| To work with this type of alert in bulk, we recommend that you work in the Policy center to mitigate them.<br /><br /> Fine-tune the policy to exclude noisy entities by adding more filters and more granular controls.<br /><br /> If the policy is very accurate, the alert is warranted, and it's a violation you want to stop immediately, consider adding automatic remediation in the policy.|  
|Compromised account|This type of alert is triggered when Cloud App Security identifies an account that was compromised, meaning there's a very high probability that the account was used in an unauthorized way.|We recommend that you suspend the account until you can reach the user and make sure they change their password.|  
|Inactive account|This alert is triggered when an account is no longer used in one of your connected cloud apps.|Contact the user and the user's manager to determine  whether the account is still active. If not, suspend the user and terminate the license for the app.|  
|New admin user|This alerts you to changes in your privileged accounts for connected apps.|Confirm that the new admin permissions are in fact required for the user. If they are not, recommend revoking admin privileges to reduce exposure.|  
|New admin location|This alerts you to changes in your privileged accounts for connected apps.|Confirm that the sign in from this anomalous location was legitimate. If it's not, recommend revoking admin permissions or suspending the account to reduce exposure.|  
|New location|This is an informative alert about access to a connected app from a new location, and it's triggered only once per country.|Investigate the specific user's activity.|  
|New discovered service|This is an alert about Shadow IT--a new app was detected by Cloud Discovery.|<ul><li>Assess the risk of the service based on the app catalog.</li><li>Drill down into the activity to understand usage patterns and prevalence.</li><li>Decide whether to sanction or unsanction the app.</li><br /></ul>For unsanctioned apps:<br /><br /><ul><li>You may want to block use in your proxy or firewall.</li><li>If you have an unsanctioned app and a sanctioned app in the same category, you can export a list of users of the unsanctioned app, and then contact them to migrate them to the sanctioned app.</li></ul></li>|  
|Suspicious activity|This alert lets you know that anomalous activity has been detected that is not aligned with expected activities or users in your  organization.|Investigate the behavior and confirm it with the user.<br /><br /> This type of alert is a great place to start learning more about your environment and creating new policies with these alerts. For example, if someone suddenly uploads a large amount of data to one of your connected apps, you can set a rule to govern that type of anomalous behavior.|  
|Suspicious cloud use|This alert lets you know that anomalous activity has been detected that is not aligned with expected activities or users in your  organization.|Investigate the behavior and confirm it with the user.<br /><br /> This type of alert is a great place to start learning more about your environment and creating new policies with these alerts. For example, if someone suddenly uploads a large amount of data to one of your connected apps, you can set a rule to govern that type of anomalous behavior.|  
|Use of personal account|This alert lets  you know that a new personal account has access to resources in your connected apps.|Remove the user's collaborations in the external account.|  

## Use policies to assess risk  
After you take a look at your open alerts, go to the Policy center to review policy violations that didn't trigger alerts.  

-   In the Cloud App Security dashboard, click **Control** and then **Policies**.  

-   Select a specific policy to see the **Violating now** list of policy matches that didn't trigger alerts.  

-   Click the violations one at a time and decide what to do for each. See the following figures for more information about governance actions.  

     For example, if your policy is set to find compliance breaches and someone saves credit card numbers in files on OneDrive, you will have a match in the policy.  

     ![PCI matches](./media/pci-matches.png "pci matches")  

-   Select the match to see the actual files that breached the policy.  

     ![PCI content matches](./media/pci-content-matches.png "pci content matches")  

     You can select the file itself to get information about the files.  

     You can click **Collaborators** to see who has access to this file.  

     You can click **Matches** to see the actual credit card numbers.  

     ![Content matches ccn](./media/content-matches-ccn.png "content matches ccn")  

## Next steps  
For more information about investigating alerts, see [Investigate](investigate.md).  
For technical support, please visit [the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
Premier customers can also choose Cloud App Security directly from the [Premier Portal.](https://premier.microsoft.com/)  
