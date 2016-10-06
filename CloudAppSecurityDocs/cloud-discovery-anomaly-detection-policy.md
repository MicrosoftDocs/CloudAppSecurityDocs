---
title: "Cloud Discovery anomaly detection policy"
ms.custom: na
ms.date: "07/27/2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
applies_to: 
  - "Microsoft Cloud App Security"
ms.assetid: eaf73af0-7610-4903-b656-8d90b1d2b18c
caps.latest.revision: 6
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
# Cloud Discovery anomaly detection policy
  This article provides reference details about policies, providing explanations for each policy type and the fields that can be configured for each policy.  
  
## Cloud discovery anomaly detection policy reference  
 A Cloud discovery anomaly detection policy enables you to setup and configure continuous monitoring of unusual increases in cloud application usage. For each cloud application, increases in downloaded data, uploaded data, number of transactions and number of users are considered. Each increase is compared to the normal usage pattern of the application as learned from past usage. The most extreme increases trigger security alerts.  
  
 Each policy is composed of the following parts:  
  
-   Filters – Enable you to selectively monitor application usage, based on an application filter, selected data views, and a selected start date.  
  
-   Sensitivity – Enable you to set how many alerts the policy should trigger.  
  
### Activity filters  
 For a list of Activity filters, see [Activity filters](../Topic/Activity%20policy%20reference.md#activityfilters).  
  
### Apply to  
 The usage being monitored can be filtered in two different ways:  
  
-   Data views – select whether to monitor all data views (default), or choose specific data views to monitor.  
  
    -   When selecting **All data views**, each usage increase is compared to the normal usage pattern as learned from all the data views.  
  
    -   When selecting specific data views, each usage increase is compared to the normal usage pattern as learned from the same data view as the increase was observed in.  
  
-   Users and IP addresses – every cloud application usage is associated either with a user, an IP address, or both.  
  
    -   Selecting **Users** will ignore the association of application usage with IP addresses if there is any.  
  
    -   Selecting **IP addresses** will ignore the association of application usage with users if there is any.  
  
    -   Selecting **Users and IP addresses** will consider both associations, but may produce duplicate alerts when there is a tight correspondence between users and IP addresses.  
  
 Raise alerts only for suspicious activities occurring after date – any increase in application usage before the selected date will be ignored. However, activity from before the selected date will be learned for the purpose of establishing the normal usage pattern.  
  
### Sensitivity  
 There are two ways to control the number of alerts triggered by the policy:  
  
-   Sensitivity slider – choose how many alerts to trigger per 1,000 users per week. The alerts will be triggered of the activities with the highest risk.  
  
-   Daily alert limit – restrict the number of alerts raised on a single day.  
  
## See Also  
 [Daily activities to protect your cloud environment](../migration/daily-activities-to-protect-your-cloud-environment.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  