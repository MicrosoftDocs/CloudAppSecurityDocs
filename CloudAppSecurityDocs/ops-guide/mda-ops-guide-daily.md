---
title: Daily operational guide - Microsoft Defender for Cloud Apps
description: This article provides daily operational recommendations to help security operations teams to plan and run security activities.
ms.date: 11/28/2023
ms.topic: reference
---

# Daily operational guide - Microsoft Defender for Cloud Apps

This article lists daily operational activities that we recommend you perform with Defender for Cloud Apps.

## Review alerts and incidents

Alerts and incidents are two of the most important items your security operations (SOC) team should be reviewing on a daily basis. Triage them regularly from the incidents queue in Microsoft 365 Defender, prioritizing high and medium severity alerts. 

**Persona**: SOC analyst

**Where**: Microsoft 365 Defender > Incidents and alerts

When triaging incidents:

1. In the incident dashboard, filter for the following items:

    |Filter  |Values  |
    |---------|---------|
    |**Status**     |  New, In progress       |
    |**Severity**     |  High, Medium, Low       |
    |**Service source**     |  Keep all service sources checked. This should list alerts with the most fidelity, with correlation across other Microsoft XDR workloads. Select **Defender for Cloud Apps** to view items that come specifically from Defender for Cloud Apps.       |

Activities to be performed when triaging incidents:
1. View the incident dashboard, filter on: 
• Status: New, In progress
• Severity: High, Medium, Low
• Service source: Keep all service sources checked which should be the most 
fidelity alerts with correlation across different XDR workloads. Select MDA, 
App Governance to see explicitly what comes from MDA. 
2. Select each incident:
• Review all tabs
• Use Activity log and Advanced Hunting > In Evidence and Response tab
select each evidence, in the burger menu ( three dots) select Investigate in 
Activity log / Go hunt 
3. Select Manage incident
1. under Classification select “True positive”, “False positive” or “Informational, 
expected activity”. For true alerts, specify the threat type. Note: This 
classification helps your security team see threat patterns and defend your 
organization from them.
2. When actively investigated Assign Incident to a person and change status to 
In Progress. 
4. Set an Incident / Alert to In Progress 
5
5. Once the remediated, resolve the incident. Resolving the incident resolves all linked 
and related active alerts.
Incidents: For more information about the Incidents queue, see Prioritize incidents in Microsoft 365 
Defender and how to response to the Incidents see Incident response playbooks
*MDI: If MDI integration is enabled, MDI alerts still need to be triaged in the MDA Portal, please 
access here for more information.
SIEM: If SIEM integration is enabled, the SIEM solution is normally used first for triaging. 
Why Important: It’s adding more context via additional logs and offering additional SOAR 
functionality. Then Microsoft 365 Defender is used if deep understanding of alerts and incident 
timeline is required. 
Persona: Security Administrator
Prerequisites: Microsoft Sentinel integration , Generic SIEM integration, Enabling the Microsoft 365 
Defender connector
For bi-directional incidents sync it’s recommended enable Microsoft 365 Defender and select 
Microsoft Defender for Cloud Apps option. Microsoft Sentinel's Microsoft 365 Defender incident 
integration allows you to stream all Microsoft 365 Defender incidents into Microsoft Sentinel and 
keep them synchronized between both portals. Incidents from Microsoft 365 Defender include all 
associated alerts, entities, and relevant information, providing you with enough context to perform 
triage and preliminary investigation in Microsoft Sentinel. Once in Sentinel, incidents will remain bidirectionally synced with Microsoft 365 Defender, allowing you to take advantage of the benefits of 
both portals in your incident investigation.
Consider using streaming API - It can be used to send data to an EventHub and then can be 
consumed through a vendor SIEM connector for instance has an EventHub connector (or placed in 
Azure Storage).
Additional information: Working with Microsoft 365 Defender incidents in Microsoft Sentinel and bidirectional sync, Streaming API
Persona: SOC Analyst 
More information: 
Navigate and triage incidents in Microsoft Sentinel
Create custom analytics rules to detect threats

For more information, see [Investigate alerts in Microsoft Defender XDR](/microsoft-365/security/defender/investigate-alerts?view=o365-worldwide).

## Review threat detection data

Why Important: Cloud apps threat detection is one of the main MDA pillars, it’s where SOC analysts 
focus their daily activities, identifying high-risk users showing abnormal behavior. MDA Threat 
Detection benefits from Microsoft threat intelligence and security research data. The alerts are 
available in M365D and should be triaged as part of the established process based on 
recommendations in “Incidents and Alerts” chapter above. 
Persona: Security administrators and SOC analysts 
Where: M365 Defender portal > Incidents & Alerts 
M365 Defender portal > Cloud apps > Policies > Policy management > Threat Detection
M365 Defender portal > Cloud apps > Oauth apps 
There are three main types of Threat Detection policies in MDA Security admins and SOC analysts 
when dealing with alerts will deal with:
• Activity policies
• Anomaly detection policies
• OAuth Policies and App governance policies (depicted in the next chapter) 
Persona: Security administrator 
Creation and prerequisites of Threat protection policies

## Review application governance

Where: M365 Defender portal > Incidents & Alerts 
M365 Defender portal > Incidents & Alerts / App governance
Why important: App governance offers in-depth visibility and control over OAuth apps registered on 
Azure Active Directory and helps to combat increasingly sophisticated campaigns that exploit the 
apps deployed on-premises and cloud infrastructures, establishing a starting point for privilege 
escalation, lateral movement, and exfiltration of data. 
App governance is part of MDA and alerts are also part of M365D Incidents and alerts and should be 
reviewed as described in the Alerts section. It uses machine learning-based detection algorithms to 
detect anomalous app behaviour in your Microsoft 365 tenant and generates alerts that you can see, 
investigate, and resolve. Beyond this built-in detection capability, you can use a set of default policy 
templates or create your own app policies that generate other alerts. 
7
Persona: SOC analyst
Investigate threat detection alerts and corresponding MITRE ATT&CK tactics
How to Investigate pre-defined app policy alerts
Investigate and remediate risky OAuth apps

### Check app governance overview page 

<!--didn't this move?-->

Where: M365 Defender portal > Incidents & Alerts 
M365 Defender portal > Cloud apps > App governance > Overview tab 
Why important: Quick assess the compliance posture of the apps and incidents in the tenant.
Persona: SOC analyst and Security administrator 
List of checks: 
• number of overprivileged, highly privileged apps
• apps with unverified publisher 
• data usage for various services and resources that were accessed using Graph API
• number of apps that accessed data with the most common sensitivity labels
• number of apps that accessed data with and without sensitivity labels across Microsoft 365 
services
• overview of app governance related incidents 
Based on reviewed data create new or adjust app governance policies if required. 

### Review OAuth app data

Where: M365 Defender portal > Incidents & Alerts 
M365 Defender portal > Cloud apps > App governance > Apps
Why important: Quickly gain deep insights into the Microsoft 365 OAuth apps in your tenant. 
Examples:
• A list of OAuth-enabled apps in the tenant, together with relevant app metadata and usage 
data.
• App details with deeper insights and information by selecting an app in the list.
For more information please go to: 
8
View your apps
Obtain detailed information on an app

### Create and manage app governance policies

Where: M365 Defender portal > Cloud apps > App governance > Policies 
Why important: Get in-depth visibility and control over OAuth apps registered on Azure Active 
Directory. Generate alerts based on machine learning algorithms
Persona: Security administrator
Create app policies in app governance
Manage app policies

## Review conditional access app control

Where: M365 Defender portal > Incidents & Alerts 
M365 Defender portal > Cloud apps > Policies > Policy Management > Conditional access
Config: M365 Defender portal> Settings > Cloud apps > Conditional Access App Control 
Why important: Conditional Access App Control (CAAP) enables user app access and sessions to be 
monitored and controlled in real time based on access and session policies. Generated alerts are
available in M365D portal and should be triaged as described in the alerts section.
Persona: Security administrator 
Out of the box there is no CAAP access nor session policies deployed therefore no related alerts 
available. Any web app can be onboarded to work with access and session controls, there are 
number of popular apps that are pre-onboarded, once onboarding completed and first traffic 
generate, you should be able to create first session and access policies suitable for your environment. 
• Access policies
• Session policies
Best practices: 
• Block and protect download of sensitive data to unmanaged or risky devices
• Secure collaboration with external users by enforcing real-time session controls
Persona: SOC administrator 
9
• Review alerts in M365D
• Review Activity log – filter out by source, Access control and Session control 


## Review shadow IT - cloud discovery

Where: M365 Defender portal > Incidents & Alerts 
M365 Defender portal > Cloud apps > Cloud discovery / Cloud app catalog 
M365 Defender portal > Cloud apps > Policies > Policy Management > Shadow IT
Why Important: Cloud Discovery analyses your traffic logs against the Microsoft Defender for Cloud 
Apps catalog of over 31,000 cloud apps. The apps are ranked and scored based on more than 90 risk 
factors to provide you with ongoing visibility into cloud use, Shadow IT, and the risk Shadow IT poses 
into your organization.
Alerts related to Cloud Discovery are available in M365D and should be triaged as part of the process 
described above. 
Persona: Security Administrator 
Default Cloud Discovery anomaly detection policies have been depreciated. Security administrators 
need to create app discovery policies to start alerting / tagging newly discovered apps based on 
certain conditions, risk score, category etc and also app behaviour like daily traffic, downloaded data 
etc. 
Full list of conditions and criteria and details how to create cloud discovery policies can be found 
here: Create Cloud Discovery policies
Examples of detection Cloud Discovery policies and prerequisites can be found here: 
Cloud Discovery policies
Prerequisites: Set up Cloud Discovery
MDE Integration: We are recommending enabling Microsoft Defender for Endpoint integration to
allow you to use Cloud Discovery beyond your corporate network or secure gateways and ability to 
apply governance actions seamlessly on the endpoints (see govern discovered apps chapter). 
Best practices: MDE Integration and MDA Shadow IT Discovery
Persona: Security & Compliance Administrator, SOC Analyst 
Examples: How to use discovered App Filters and App Queries
Discovered app filters and queries in Microsoft Defender for Cloud Apps - useful when there are large 
numbers of discovered apps. 

## Review the cloud discovery dashboard

Where: M365 Defender portal > Cloud apps > Cloud discovery > Dashboard 
Why Important: In addition to alerts Cloud discovery dashboard should be reviewed on daily basis. It 
is designed to give you more insight into how cloud apps are being used in your organization. It 
provides an at-a-glance overview of what kinds of apps are being used, your open alerts, the risk 
levels of apps in your organization.
Persona: Security & Compliance Administrator, SOC Analyst 
1. First look at the overall cloud app use in your organization in the High-level usage overview.
2. Use filtering to generate specific views depending on your interest
3. Then, dive one level deeper to see which are the top categories used in your org for each of 
the different use parameters. You can see how much of this usage is by Sanction apps.
4. Go even deeper and see all the apps in a specific category in the Discovered apps tab.
5. You can see the top users and source IP addresses to identify which users are the most 
dominant users of cloud apps in your organization.
6. Check how the discovered apps spread according to geographic location (according to their 
HQ) in the App Headquarters map.
7. Review the risk score of the discovered app in the App risk overview. 
8. Check the discovery alerts status to see how many open alerts should you investigate.
Full information: Working with discovery data
 Working with discovered apps

### Govern discovered apps

Where: M365 Defender portal > Cloud apps > Cloud discovery > Dashboard 
Why Important: In addition to alerts Cloud discovery dashboard should be reviewed on daily basis. It 
is designed to give you more insight into how cloud apps are being used in your organization. It 
provides an at-a-glance overview of what kinds of apps are being used, your open alerts, the risk 
levels of apps in your organization.
Persona: Security & Compliance Administrator, SOC Analyst 
1. First look at the overall cloud app use in your organization in the High-level usage overview.
2. Use filtering to generate specific views depending on your interest
3. Then, dive one level deeper to see which are the top categories used in your org for each of 
the different use parameters. You can see how much of this usage is by Sanction apps.
4. Go even deeper and see all the apps in a specific category in the Discovered apps tab.
5. You can see the top users and source IP addresses to identify which users are the most 
dominant users of cloud apps in your organization.
6. Check how the discovered apps spread according to geographic location (according to their 
HQ) in the App Headquarters map.
7. Review the risk score of the discovered app in the App risk overview. 
8. Check the discovery alerts status to see how many open alerts should you investigate.
Full information: Working with discovery data
 Working with discovered apps

## Review information protection

Where: M365 Defender portal > Incidents & Alerts 
M365 Defender portal > Cloud apps > Files
 M365 Defender portal > Cloud apps > Policies > Policy Management > Information Protection
Why Important: Defender for Cloud Apps file policies and alerts allow you to enforce a wide range of 
automated processes. Policies can be set to provide information protection, including continuous 
compliance scans, legal eDiscovery tasks, and DLP for sensitive content shared publicly. Alerts should 
be triaged as per process described earlier in the Alerts section. 
Persona: Security & Compliance Administrator, SOC Analyst 
In addition to acting on existing File Policies alerts, SOC teams can perform additional pro active 
actions and run queries in the Files section to check the following:
• How many files are shared publicly so that anyone can access them without a link?
• With which partners are you sharing files (outbound sharing)?
• Do any files have a sensitive name?
• Are any of the files being shared with someone's personal account?
Based on the results existing file policies can be adjusted or new policies deployed. 
Examples of Detections with Information Protection policies: Information protection policies


## Related content

