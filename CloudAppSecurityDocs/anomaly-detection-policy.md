---
# required metadata

title: Create anomaly detection policies in Cloud App Security | Microsoft Docs
description: This topic provides a description of Anomaly detection policies and provides reference information about the building blocks of an anomaly detection policy.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/21/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: ab9bc377-d2f5-4f4c-a419-f1728a15d1c7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



 
# Anomaly detection policy
This article provides reference details about policies, providing explanations for each policy type and the fields that can be configured for each policy.  

After your organization is protected by Cloud App Security, all cloud activity is scored according to various pre-defined risk factors. Cloud App Security looks at every user session on your cloud and then takes into consideration the risk factors you set here to alert you when something happens that is different from either the baseline of your organization or from the user's regular activity. The policies can be enforced differently for different users, locations, and organizational sectors. For example, you can create a policy that alerts you when members of your IT team are active from outside your offices.  

Cloud App Security has an initial learning period of seven days during which it does not flag any new users, activity, devices, or locations as anomalous. After that, each session is compared to the activity, when users were active, IP addresses, devices, etc. detected over the past month and the risk score of these activities. 


The following anomaly detection policies are available:

**Impossible travel**
- This detection is part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization’s activity. It identifies two user activities (is a single or multiple sessions) originating from geographically distant locations within a time period shorter than the time it would have taken the user to travel from the first location to the second, indicating that a different user is using the same credentials. This detection leverages a machine learning algorithm that ignores obvious "false positives" contributing to the impossible travel condition, such as VPNs and locations regularly used by other users in the organization. The detection has an initial learning period of 7 days during which it learns a new user’s activity pattern.


**Activity from infrequent country**
- This detection is part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization’s activity. This detection considers past activity locations to determine new and infrequent locations. The anomaly detection engine stores information about previous locations used by users in the organization. An alert t is triggered when an activity occurs from a location that was not recently or never visited by the user or by any user in the organization. The detection has an initial learning period of 7 days, during which it does not alert on any new locations.


**Activity from anonymous IP addresses**
- This detection is part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization’s activity. This detection identifies that users were active from an IP address that has been identified as an anonymous proxy IP address. These proxies are used by people who want to hide their device’s IP address, and may be used for malicious intent. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.

**Activity from suspicious IP addresses**
- This detection is part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization’s activity. This detection identifies that users were active from an IP address that has been identified as risky by Microsoft Threat Intelligence. These IP are involved in malicious activities, such as Botnet C&C, and may indicate compromised account. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.


**Unusual X activity (by user)**
- This detection is part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization’s activity. This detection identifies users that perform multiple X activity in a single session with respect to the baseline learned, which could indicate on a breach attempt. This detection leverages a machine learning algorithm that profiles the users log-on pattern and reduces "false positives".


**Multiple failed login attempts**
- This detection is part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization’s activity. This detection identifies users that failed multiple login attempts in a single session with respect to the baseline learned, which could indicate on a breach attempt. This detection leverages a machine learning algorithm that profiles the users log-on pattern and reduces "false positives".

To configure an anomaly detection policy:  
  
1.  In the console, click on **Control** followed by **Policies**.  
  
2.  Click **Create policy** and select **Anomaly detection** policy.  
  
     ![Anomaly detection policy menu](./media/anomaly-detection-policy-menu.png "Anomaly detection policy menu")  
  
3.  Fill in the policy's name and description, and continue to the **Activity filters** field where you can choose the activity for which you wish to apply the policy.  
  
4.  Give your policy a name and description, if you want you can base it on a template, for more information on policy templates, see [Control cloud apps with policies](control-cloud-apps-with-policies.md).  
  
5.  To apply the policy to all activities in your cloud environment, select **All monitored activity**. To limit the policy to specific types of activities, choose **Selected activity**. Click on **Add filters** and set the appropriate parameters by which to filter the activity. For example, to enforce the policy only on activity performed by Salesforce admins, choose this user tag.  
  
6.  Underneath this field set the **Risk factors**. You can choose which risk families you want to consider while calculating the risk score. On the right of the row, you can use the On/Off button to enable and disable the various risks. Additionally, for greater granularity, you can choose the activity on which to enable each particular risk family.  
  
     Risk factors are as follows:  
  
    -   **Login failures**: Are users attempting to log in and failing multiple times over a short period?  
  
    -   **Admin activity**: Are admins using their privileged accounts to log in from unusual locations or at strange hours?  
  
    -   **Inactive accounts**: Is there suddenly activity on an account that hasn't been in use for some time?  
  
    -   **Location**: Is there activity in an unusual, suspicious, or new location?  
  
    -   **Impossible travel**: Is a user logging in from Denver and 10 minutes later logging in from Paris?  
  
    -   **Device and user agent**: Is there activity from an unrecognized or unmanaged device?  

    -   **Activity rate**: Is there suddenly a lot of activity on a particular app? Are there large downloads or deletes, or mass number of files shared or a lot of unexpected admin activity?
  
     You can use these parameters to define complex scenarios, for example, to exclude your office's IP range from the considered risk factors for anomaly detection, create a specific "office IP" tag and filter the range out of the considered parameters. To then exclude the range that you created from the admin activity anomaly detection:  
  
    -   Within **Risk type**, find **Admin activity**.  
  
    -   Change **Apply to** to **Selected Activity**.  
  
    -   Under **Activity filters**, set **Apply to** to **Selected activity** and under **Activities matching all of the following**, choose **Administrative activity** is **True**.  
  
    -   Click on the **+** icon and select  **IP tag does not equal** and select the Office IP tag.  
  
7.  Under **Sensitivity**, select how often you want to receive alerts.  
  
     The sensitivity value determines how many weekly alerts are triggered on average for every 1,000 users.  
  
     ![anomaly detection IPs](./media/anomaly-detection-ips.png "anomaly detection IPs")  
  
8.  Click **Create**.  
 

## Anomaly detection policy reference  
An anomaly detection policy enables you to set up and configure continuous monitoring of user activity for behavioral anomalies. Anomalies are detected by scanning user activity. The risk is evaluated by looking at over 30 different risk indicators, grouped into 6 risk factors. Based on the policy results, security alerts are triggered.   
Each policy is composed of the following parts:  
  
-   Activity filters – Enable you to selectively scan only filtered user activity for anomalies.  
  
-   Risk factors – Enable you to choose which risk factors to include when evaluating risk.  
  
-   Sensitivity – Enable you to set how many alerts the policy should trigger.  
  
### Activity filters  
For a list of Activity filters, see [enter link description here](activity-filters.md).  
  
### Risk factors  
Below is a list of the risk factors that are considered when evaluating the risk of user activity. Each risk factor can be toggled on or off. For each risk factor there are two options under the **Apply to** field, which determine whether to include it when evaluating the risk of user activity:  
  
-   All monitored activity – include it for all user activity that passes the policy activity filter.  
  
-   Selected activity – include it for user activity that passes both the policy activity filters and the activity filters that appear under this risk factor. When this option is selected an activity filter selector appears under the risk factor, which works exactly the same as the policy activity filter.  
  
Each risk factor, when included in the risk evaluation, has its own triggers that cause an increase in the evaluated risk of user activity:  
  
-   Login failures – a high number of login failures or activity comprised entirely of login failures.  
  
-   Admin activity - administrative activity performed by an unexpected user, or performed from an IP, ISP, or location that are new, or not used by any other user in the organization.  
  
-   Inactive accounts - activity performed by a user that was not active for a long time.  
  
-   Location - activity performed from an IP, ISP, or location that were either never used by any other user, never used by this particular user, never used at all, or used only for login failures in the past.  
  
-   Impossible travel - activity from remote locations within a short time.  
  
-   Device and user agent - activity performed by a user using a user agent or device that was either never used by any other user, never used by this particular user, or never used at all.  
  
-   Activity rate - repeated activities performed by a user within a short period. 

### Sensitivity  
To control the number of alerts triggered by the policy, set the **Daily alert limit** and restrict the number of alerts raised on a single day.  
  
## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  
