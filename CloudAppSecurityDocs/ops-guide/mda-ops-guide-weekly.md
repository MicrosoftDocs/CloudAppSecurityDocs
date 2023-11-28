---
title: Weekly operational guide - Microsoft Defender for Cloud Apps
description: This article provides weekly operational recommendations to help security operations teams to plan and run security activities.
ms.date: 11/28/2023
ms.topic: reference
---

# Weekly operational guide - Microsoft Defender for Cloud Apps

This article lists weekly operational activities that we recommend you perform with Defender for Cloud Apps.

## Review SaaS security posture management

Where: M365 Defender portal > Secure Score 
Why Important: SaaS Security Posture Management capabilities in Microsoft Defender for Cloud 
Apps enable you to get deeper visibility and automatically identify SaaS apps misconfigurations, and 
help you remediate them to improve your organizational security. This experience is integrated into 
the Microsoft 365 Defender dashboard to enable security teams to see their holistic security posture 
across the enterprise with Microsoft Secure Score.
Persona: Security & Compliance Administrator, SOC Analyst 
Tip: For best high level overview of list of actions per product, go to Secure Score and select 
Recommended actions and select group by in the right corner and select Product

## Check app connectors, log collectors, and SIEM agent health

<!--in the overview this is in daily?-->
Where: M365 Defender portal > Settings > Cloud apps 
Persona: Security & Compliance Administrator, SOC Analyst 
Why Important: System alerts are special type of alerts raised when connector, agent or log collector 
fails, it’s not possible to send a notification to an administrator in MDA portal. It’s important to check 
health of your app connectors, log collectors and SIEM agents 
If SIEM agent is used, System alerts can be injected go to M365D settings > System >SIEM Agents and
Configure SIEM agent. In Data Types section select Alerts, make sure Alert type filter contain system 
alerts. 
It’s recommended to review status of:
• App connectors
o Settings > Cloud apps > Connected apps > App Connectors
• Conditional Access App control Apps
o Settings > Cloud apps > Connected apps > CAAP
• Automatic log upload 
o Settings > Cloud apps > Cloud Discovery > Automatic log upload 
• API tokens 
o Settings > Cloud apps > System > API tokens


## Track new changes in Microsoft 365 Defender

Where: M365 admin center > Health > Message center 
Why Important: Message center helps you to keep track of upcoming changes, including new 
features, planned maintenance, or other important announcements that may affect your MDA 
environment. 
Persona: Security administrator 
More information: Track new and changed features in the Microsoft 365 Message center.

## Review the governance log

Why Important: The Governance log provides a status record of each task that you set Defender for 
Cloud Apps to run, including both manual and automatic tasks. These tasks include those you set in 
policies, governance actions that you set on files and users, and any other action you set Defender 
for Cloud Apps to take. 
Where: M365 Defender portal > Cloud apps > Governance log
Persona: Security and Compliance administrator 
More information: Full list of Governance log

## Related content