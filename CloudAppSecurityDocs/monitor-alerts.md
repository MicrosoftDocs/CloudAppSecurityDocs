---
title: "Monitor alerts"
ms.custom: na
ms.date: "07/31/2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: f118a3bf-1663-46ba-884f-b1b03a84ab66
caps.latest.revision: 4
author: "Rkarlin"
ms.author: "rkarlin"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "hu-hu"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "nl-nl"
  - "pl-pl"
  - "pt-br"
  - "pt-pt"
  - "ru-ru"
  - "sv-se"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Monitor alerts
To view alerts:

In the Cloud App Security portal, click on Alerts.


![Alert menu](./media/alert-menu.png)


The following alerts types will be displayed. 

|Alert name|AlertID|Description|
|----|----|----|
|New location|ALERT_GEOLOCATION_NEW_COUNTRY|A new location was detected since the scan began (up to 6 months). This only shows up once for each country for your entire organization. |
|New admin user|ALERT_ADMIN_USER|A new admin was detected for a specific app – this can be someone who is an admin in one application and is now an admin for another application. This alert relates to the specific admin type, so it will show up each time the type of admin changes. If a user lost admin privileges and then got them again, this alert will be displayed.|
|Inactive account|ALERT_ZOMBIE_USER|If a user is inactive for 60 days per application – for example, if someone is active in Box but hasn't touched Google Apps for 60 days, the user will be considered inactive in Google Apps. A tag is added to these users so you can search for inactive accounts.|
|Unexpected admin location|ALERT_NEW_ADMIN_LOCATION|A new location was detected for administrators since the scan began (up to 6 months). This only shows up once for each country for any admin across your organization. |
|Suspicious activity alert|ALERT_SUSPICIOUS_ACTIVITY|Suspicious activities are scored according to how suspicious the anomalous activity is (Is there an inactive account involved? Is it from a new location?) These criteria are all calculated together to provide a risk score based on the following risk factors: <br>User is administrator <br>Strictly remote user<br>Anonymous proxy<br> Entire session is failed logins<br>Numerous failed login<br>New (admin)<br>IP/ISP/country/user-agent for user/tenant<br> IP/ISP/country/user-agent used only by (admin) user<br>First (admin) user activity in a while<br>First time this particular administrative activity is performed in a while<br>This particular administrative activity is not common / was never performed before<br>This IP had only failed logins in the past<br>Impossible travel|
|Compromised account|ALERT_COMPROMISED_ACCOUNT|If there was a breach in an application, and the list of breached accounts is published, Cloud App Security downloads the list and compares it to your list of users - including internal users, external users and personal accounts. |
|Suspicious cloud use alert|ALERT_DISCOVERY_ANOMALY_DETECTION|Cloud Discovery anomaly detection checks the pattern of regular behavior and looks for users or apps that are used in an unusual way. |
|Activity policy violation|ALERT_CABINET_EVENT_MATCH_AUDIT|This alert lets you know when a policy match was detected.|
|File policy violation|ALERT_CABINET_EVENT_MATCH_FILE|This alert lets you know when a policy match was detected.|
|Proxy policy violation|ALERT_CABINET_INLINE_EVENT_MATCH|This alert lets you know when a policy match was detected.|
|Field policy violation|ALERT_CABINET_EVENT_MATCH_OBJECT|This alert lets you know when a policy match was detected.|
|New service discovered|ALERT_CABINET_DISCOVERY_NEW_SERVICE|A new app was discovered.|
|Use of personal account|ALERT_PERSONAL_USER_SAGE|Based on file shares and user names, the detection engine searches for personal accounts. |

