---
title: Monthly operational guide - Microsoft Defender for Cloud Apps
description: This article provides monthly operational recommendations to help security operations teams to plan and run security activities.
ms.date: 11/28/2023
ms.topic: reference
---

# Monthly operational guide - Microsoft Defender for Cloud Apps

This article lists monthly operational activities that we recommend you perform with Defender for Cloud Apps.

Monthly activities can be performed more frequently or as needed, depending on your environment 
and needs. 

## Review policy assessments

Why Important: Review the policies and make any necessary updates to ensure they are still 
appropriate for your organization.
Where: M365 Defender portal > Cloud apps > Policy management 
Persona: Security and Compliance administrator 
- Check for and false positive / benign true positive rates: adjust policies where rates is 
too high:
o Example: ensure that any new corp IP is properly filled up in MDA settings to 
avoid Impossible travel False Positive.
- Review business needs and assess requirement for custom policies
o Example: is the threat detected by this policy still relevant? Or is there a new 
built in solution to detect that threat?
- Clear old alerts 
o Example: select alerts time 6 months, filter out alerts with resolved status, 
group similar alerts and verify why they were not attended, if they are benign 
and can be dismissed and policies adjusted 

## Review activity logs

Why Important: Activity logs are frequently reviewed in relation to alerts and are part of threat 
investigation. Additionally it’s beneficial to re-visit the Activity log after certain period of time and 
look from the time perspective for repeated activities by an entity like multiple searches or log on by 
a user. Pivot results by activity type for example failed log on, deletion or privilege assignment. Then 
narrow down activity to an app or a user. Based on the results you may create a new policy which 
will help with closer monitor and respond to potential threat.
Where: M365 Defender portal > Cloud apps > Activity log 
Persona: Security and Compliance administrator

## Related content


