---
title: Monitor alerts raised in Cloud App Security
description: This article provides a list and description of all alerts.
ms.date: 02/14/2021
ms.topic: how-to
---
# Monitor alerts in Cloud App Security

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Alerts are the entry points to understanding your cloud environment more deeply. This article provides a list and description of all alerts.

## Monitoring your alerts

It's a good idea to review all of your alerts. Understanding why an alert is occurring allows you to use them as tools for modifying your policies.

**To view alerts:** In the Microsoft Cloud App Security portal, click on **Alerts**.

![Alert menu](media/alert-menu.png)

- **Dismiss** an alert after you look at it and determine it's not interesting.
  - Enter a **comment** to explain why you dismissed the alert
  - **Send us feedback about this alert** to be reviewed by our security research team for improving the alerts.

- **Resolve** the alert if you investigate it and mitigate the risk.

  - The alert will no longer show up in the alerts table.
  - **Mark as unread** if you started investigating an issue but you want to make sure you remember to continue.
  - **Adjust the policy** that matched the alert to improve future alert matches.
  - Resolving an alert gives you the option to enter a comment and **Send feedback to the Cloud App Security team**.

## Deployment of our enhanced alert monitoring and management experience

As part of our ongoing improvements to monitoring and managing alerts, the Cloud App Security Alerts page has been improved based on your feedback. In the enhanced experience, the **Resolved** and **Dismissed** statuses are replaced by the **Closed** status, and closed alerts have one of the following resolution types:

- **True positive**: An alert on a confirmed malicious activity
- **Benign**: An alert on a suspicious but not malicious activity, such as a penetration test or other authorized suspicious action
- **False positive**: An alert on a non-malicious activity

> [!NOTE]
> The enhanced experience only applies to new alerts and does not affect the status of existing (legacy) alerts that were **Resolved** or **Dismissed**.

![Enhanced alerts page](media/monitor-alerts/enhanced-alerts.png)

### Enhanced alert monitoring

In the enhanced alerts page, the **Status** column shows whether an alert is opened or closed and the **Resolution type** column shows the type of resolution used when closing an alert. You can use the **Status** filter to help you identify opened or closed alerts, and then using the **Advanced** filter, you can further investigate closed alerts by **Resolution type** using both enhanced and legacy resolution types.

![Enhanced alerts page showing advanced filter](media/monitor-alerts/enhanced-alerts-advanced-filter.png)

### Enhanced alert management

When closing alerts, choose one of the following resolution options:

- **Close as true positive**: If the activity is confirmed as malicious
- **Close as benign**: If the activity is suspicious but not malicious activity, such as a penetration test or other authorized suspicious action
- **Close as false positive**: If the activity is confirmed as non-malicious

In the pop-up that appears, provide a reason for closing the alert and fill out the rest of the details as required, and then click **Close alert**.

![Enhanced alerts close popup](media/monitor-alerts/enhanced-alerts-close-resolution.png)

## Built-in alerts

The following alerts types will be displayed.

|Alert name|AlertID|Description|
|----|----|----|
|Compromised account|ALERT_COMPROMISED_ACCOUNT|If there was a breach in an application and the list of breached accounts is published, Cloud App Security downloads the list and compares it to your list of users. The user list includes internal users, external users, and personal accounts. |
|New admin user|ALERT_ADMIN_USER|A new admin was detected for a specific app. This admin can be someone who is an admin in one application and is now an admin for another application. This alert relates to the specific admin type, so it will show up each time the type of admin changes. If a user lost admin privileges and then got them again, this alert will be displayed.|
|New location|ALERT_GEOLOCATION_NEW_COUNTRY|A new location was detected since the scan began (up to 6 months). This alert only shows up once for each country/region for your entire organization. |
|Inactive account|ALERT_ZOMBIE_USER|If a user is inactive for 60 days per application – for example, if someone is active in Box but hasn't touched Google Workspace for 60 days, the user will be considered inactive in Google Workspace. A tag is added to these users so you can search for inactive accounts.|
|Ransomware activity|ALERT_ANUBIS_DETECTION_RANSOMWARE|An activity pattern is detected that is typical of a ransomware attack|
|Unexpected admin location|ALERT_NEW_ADMIN_LOCATION|A new location was detected for administrators since the scan began (up to 6 months). This alert only shows up once for each country/region for any admin across your organization. |

## Custom Alerts

The following alerts types will be displayed.

|Alert name|AlertID|Description|
|----|----|----|
|Suspicious activity alert|ALERT_SUSPICIOUS_ACTIVITY|Suspicious activities are scored according to how suspicious the anomalous activity is (Is there an inactive account involved? Is it from a new location?) These criteria are all calculated together to provide a risk score based on the following risk factors: <br />User is administrator <br />Strictly remote user<br />Anonymous proxy<br /> Entire session is failed logins<br />Numerous failed logins<br />New (admin)<br />IP/ISP/country/user-agent for user/tenant<br /> IP/ISP/country/user-agent used only by (admin) user<br />First (admin) user activity in a while<br />First time this particular administrative activity is performed in a while<br />This particular administrative activity isn't common / was never performed before<br />This IP had only failed logins in the past<br />Impossible travel|
|Suspicious cloud use alert|ALERT_DISCOVERY_ANOMALY_DETECTION|Cloud Discovery anomaly detection checks the pattern of regular behavior and looks for users or apps that are used in an unusual way. |
|Activity policy violation|ALERT_CABINET_EVENT_MATCH_AUDIT|This alert lets you know when a policy match was detected.|
|File policy violation|ALERT_CABINET_EVENT_MATCH_FILE|This alert lets you know when a policy match was detected.|
|Proxy policy violation|ALERT_CABINET_INLINE_EVENT_MATCH|This alert lets you know when a policy match was detected.|
|Field policy violation|ALERT_CABINET_EVENT_MATCH_OBJECT|This alert lets you know when a policy match was detected.|
|New service discovered|ALERT_CABINET_DISCOVERY_NEW_SERVICE|A new app was discovered.|
|Use of personal account|ALERT_PERSONAL_USER_SAGE|Based on file shares and user names, the detection engine searches for personal accounts. |

## Next steps

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[!INCLUDE [Open support ticket](includes/support.md)]
