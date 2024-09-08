---
title: Investigate app governance threat detection alerts | Microsoft Defender for Cloud Apps
ms.date: 02/12/2023
ms.topic: conceptual
ms.custom: has-azure-ad-ps-ref, azure-ad-ref-level-one-done
description: Learn how to investigate threat detection alerts from app governance in Microsoft Defender XDR with Microsoft Defender for Cloud Apps.
---

# Investigate app governance threat detection alerts

App governance provides security detections and alerts for malicious activities. This article lists details for each alert that can aid your investigation and remediation, including the conditions for triggering alerts. Since threat detections are nondeterministic by nature, they're only triggered when there's behavior that deviates from the norm.

For more information, see [App governance in Microsoft Defender for Cloud Apps](app-governance-manage-app-governance.md)

> [!NOTE]
> App governance threat detections are based on counting activities on data that is transient and may not be stored, therefore alerts may provide the number of activities or indications of spikes, but not necessarily all the relevant data. Specifically for OAuth apps Graph API activities, the activities themselves can be audited by the tenant using Log Analytics and Sentinel.
> 
> For more information see: 
>
> - [Access Microsoft Graph activity logs](/graph/microsoft-graph-activity-logs-overview)
> - [Analyze activity logs using Log Analytics](/entra/identity/monitoring-health/howto-analyze-activity-logs-log-analytics)
> 
## MITRE ATT&CK

To make it easier to map the relationship between app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic. This extra reference makes it easier to understand the suspected attacks technique potentially in use when app governance alert is triggered.

This guide provides information about investigating and remediating app governance alerts in the following categories.

- [Initial Access](#initial-access-alerts)
- Execution
- [Persistence](#persistence-alerts)
- [Privilege Escalation](#privilege-escalation-alerts)
- [Defense Evasion](#defense-evasion-alerts)
- [Credential Access](#credential-access)
- [Discovery](#discovery-alerts)
- [Lateral Movement](#lateral-movement-alerts)
- [Collection](#collection-alerts)
- [Exfiltration](#exfiltration-alerts)
- [Impact](#impact-alerts)

## Security alert classifications

Following proper investigation, all app governance alerts can be classified as one of the following activity types:

- **True positive (TP)**: An alert on a confirmed malicious activity.
- **Benign true positive (B-TP)**: An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.
- **False positive (FP)**: An alert on a nonmalicious activity.

## General investigation steps

Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.

- Review the app severity level and compare with the rest of the apps in your tenant. This review helps you identify which Apps in your tenant pose the greater risk.
- If you identify a TP, review all the App activities to gain an understanding of the impact. For example, review the following App information:

  - Scopes granted access
  - Unusual behavior  
  - IP address and location

## Initial access alerts

This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.  

### App redirects to phishing URL by exploiting OAuth redirection vulnerability

**Severity**: Medium

This detection identifies OAuth apps redirecting to phishing URLs by exploiting the response type parameter in OAuth implementation through the Microsoft Graph API.

**TP or FP?**

- **TP**: If you can confirm that the OAuth app was delivered from an unknown source, the response type of the reply URL after consenting to the OAuth app contains an invalid request, and redirects to an unknown or untrusted reply URL.  

  **Recommended action**: Disable and remove the app, reset the password, and remove the inbox rule.  

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities done by the app.  
1. Review the scopes granted by the app.  

### OAuth App with suspicious Reply URL

**Severity**: Medium

This detection identifies an OAuth app accessed a suspicious Reply URL through the Microsoft Graph API.

**TP or FP?**

- **TP**: If you can confirm that the OAuth app is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated. A suspicious URL is one where the reputation of the URL is unknown, not trusted, or whose domain was recently registered and the app request is for a high privilege scope.

  **Recommended action**: Review the Reply URL, domains and scopes requested by the app. Based on your investigation, you can choose to ban access to this app. Review the level of permission requested by this app and which users are granted access.

  To ban access to the app, go to the relevant tab for your app on the **App governance** page. On the row in which the app you want to ban appears, select the ban icon. You can choose whether you want to tell users the app they installed and authorized has been banned. The notification lets users know the app will be disabled, and they won't have access to the connected app. If you don't want them to know, unselect **Notify users who granted access to this banned app** in the dialog. We recommend that you let the app users know their app is about to be banned from use.
 
- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review the apps that are created recently and their Reply URLs.

1. Review all activities done by the app.  

1. Review the scopes granted by the app.  

### App created recently has low consent rate

**Severity**: Low

This detection identifies an OAuth app that was created recently and found to have low consent rate. This can indicate a malicious or risky app that lure users in illicit consent grants.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app is delivered from an unknown source, then a true positive is indicated.

  **Recommended action**: Review the display name, Reply URLs and domains of the app. Based on your investigation you can choose to ban access to this app. Review the level of permission requested by this app and which users granted access.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities done by the app.  
1. If you suspect that an app is suspicious, we recommend that you investigate the app’s name and reply domain in different app stores. When checking app stores, focus on the following types of apps:
   - Apps that have been created recently
   - App with unusual display name
   - Apps with a suspicious Reply domain
1. If you still suspect that an app is suspicious, you can research the app display name and reply domain.

### App with bad URL reputation

**Severity**: Medium

This detection identifies an OAuth app that was found to have bad URL reputation.  

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app is delivered from an unknown source and redirects to a suspicious URL, then a true positive is indicated.

  **Recommended action**: Review the Reply URLs, domains and scopes requested by the app. Based on your investigation you can choose to ban access to this app. Review the level of permission requested by this app and which users have granted access.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities done by the app.  
1. If you suspect that an app is suspicious, we recommend that you investigate the app’s name and reply domain in different app stores. When checking app stores, focus on the following types of apps:
   - Apps that have been created recently
   - App with unusual display name
   - Apps with a suspicious Reply domain
1. If you still suspect that an app is suspicious, you can research the app display name and reply domain.

### Encoded app name with suspicious consent scopes

**Severity**: Medium

**Description**: This detection identifies OAuth apps with characters, such as Unicode or encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API. This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.

**TP or FP?**

- **TP**: If you can confirm that the OAuth app has encoded the display name with suspicious scopes delivered from an unknown source, then a true positive is indicated.  

  **Recommended action**: Review the level of permission requested by this app and which users granted access. Based on your investigation you can choose to ban access to this app.

  To ban access to the app, go to the relevant tab for your app on the **App governance** page. On the row in which the app you want to ban appears, select the ban icon. You can choose whether you want to tell users the app they installed and authorized has been banned. The notification lets users know the app will be disabled and they won't have access to the connected app. If you don't want them to know, unselect Notify users who granted access to this banned app in the dialog. We recommend that you let the app users know their app is about to be banned from use.

- **FP**: If you're to confirm that the app has an encoded name but has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

Follow the tutorial on how to [investigate risky OAuth apps](./investigate-risky-oauth.md).

### OAuth App with Read scopes has suspicious Reply URL

**Severity**: Medium

**Description**: This detection identifies an OAuth app with only *Read* scopes such as *User.Read*, *People.Read*, *Contacts.Read*, *Mail.Read*, *Contacts.Read*.Shared redirects to suspicious Reply URL through Graph API. This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.

  **Recommended action**: Review the Reply URL and scopes requested by the app. Based on your investigation you can choose to ban access to this app. Review the level of permission requested by this app and which users have granted access.

  To ban access to the app, go to the relevant tab for your app on the **App governance** page. On the row in which the app you want to ban appears, select the ban icon. You can choose whether you want to tell users the app they installed and authorized has been banned. The notification lets users know the app will be disabled and they won't have access to the connected app. If you don't want them to know, unselect Notify users who granted access to this banned app in the dialog. We recommend that you let the app users know their app is about to be banned from use.

- **B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities done by the app.
1. If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores. When checking app stores, focus on the following types of apps:
   - Apps that have been created recently.
   - Apps with a suspicious Reply URL
   - Apps that haven't been recently updated. Lack of updates might indicate the app is no longer supported.
1. If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online  

### App with unusual display name and unusual TLD in Reply domain  

**Severity**: Medium  

This detection identifies app with unusual display name and redirect to suspicious reply domain with an unusual Top-level domain (TLD) through Graph API. This can indicate an attempt to camouflage a malicious or risky app as a known and trusted app so that adversaries can mislead the users into consenting to their malicious or risky app.  

**TP or FP?**

- **TP**: If you’re able to confirm that the app with unusual display name delivered from an unknown source and redirects to a suspicious domain having unusual Top-level domain  

    **Recommended action**: Review the display name and Reply domain of the app. Based on your investigation you can choose to ban access to this app. Review the level of permission requested by this app and which users granted access.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

    **Recommended Action**: Dismiss the alert.

**Understand the scope of the breach**

Review all activities done by the app. If you suspect that an app is suspicious, we recommend that you investigate the app’s name and reply domain in different app stores. When checking app stores, focus on the following types of apps:

- Apps that have been created recently
- App with unusual display name
- Apps with a suspicious Reply domain

If you still suspect that an app is suspicious, you can research the app display name and reply domain.

### New app with mail permissions having low consent pattern  

**Severity**: Medium  

This detection identifies OAuth apps created recently in relatively new publisher tenants with the following characteristics:
- Permissions to access or change mailbox settings
- Relatively low consent rate, which can identify unwanted or even malicious apps that attempt to obtain consent from unsuspecting users  

**TP or FP?**

- **TP**: If you’re able to confirm that the consent request to the app was delivered from an unknown or external source and the app doesn't have a legitimate business use in the organization, then a true positive is indicated.

    **Recommended action**:
    - Contact users and admins who have granted consent to this app to confirm this was intentional and the excessive privileges are normal.
    - Investigate app activity and check affected accounts for suspicious activity.
    - Based on your investigation, disable the app and suspend and reset passwords for all affected accounts.
    - Classify the alert as a true positive.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

    **Recommended Action**: Classify the alert as a false positive and consider sharing feedback based on your investigation of the alert.

**Understand the scope of the breach**

Review consent grants to the application made by users and admins. Investigate all activities done by the app, especially access to mailbox of associated users and admin accounts. If you suspect that the app is suspicious, consider disabling the application and rotating credentials of all affected accounts. 

### New app with low consent rate accessing numerous emails  

**Severity**: Medium  

This alert identifies OAuth apps registered recently in a relatively new publisher tenant with permissions to change mailbox settings and access emails. It also verifies whether the app has a relatively low global consent rate and makes numerous calls to Microsoft Graph API to access emails of consenting users. Apps that trigger this alert might be unwanted or malicious apps attempting to obtain consent from unsuspecting users.

**TP or FP?**

- **TP**: If you’re able to confirm that the consent request to the app was delivered from an unknown or external source and the app doesn't have a legitimate business use in the organization, then a true positive is indicated.

    **Recommended action**:
    - Contact users and admins who have granted consent to this app to confirm this was intentional and the excessive privileges are normal. 
    - Investigate app activity and check affected accounts for suspicious activity. 
    - Based on your investigation, disable the app and suspend and reset passwords for all affected accounts.
    - Classify the alert as a true positive.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization, then a false positive is indicated.

    **Recommended Action**: Classify the alert as a false positive and consider sharing feedback based on your investigation of the alert.

**Understand the scope of the breach**

Review consent grants to the application made by users and admins. Investigate all activities done by the app, especially access to the mailboxes of associated users and admin accounts. If you suspect that the app is suspicious, consider disabling the application and rotating credentials of all affected accounts. 

### Suspicious app with mail permissions sending numerous emails

**Severity**: Medium  

This alert finds multitenant OAuth apps that have made numerous calls to Microsoft Graph API to send emails within a short time period. It also verifies whether the API calls have resulted in errors and failed attempts to send emails. Apps that trigger this alert might be actively sending spam or malicious emails to other targets.

**TP or FP?**

- **TP**: If you’re able to confirm that the consent request to the app was delivered from an unknown or external source and the app doesn't have a legitimate business use in the organization, then a true positive is indicated.

    **Recommended action**:
    - Contact users and admins who have granted consent to this app to confirm this was intentional and the excessive privileges are normal.
    - Investigate app activity and check affected accounts for suspicious activity. 
    - Based on your investigation, disable the app and suspend and reset passwords for all affected accounts.
    - Classify the alert as a true positive.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization, then a false positive is indicated.

    **Recommended Action**: Classify the alert as a false positive and consider sharing feedback based on your investigation of the alert.

**Understand the scope of the breach**

Review consent grants to the application made by users and admins. Investigate all activities done by the app, especially access to mailbox of associated users and admin accounts. If you suspect that the app is suspicious, consider disabling the application and rotating credentials of all affected accounts.

### Suspicious OAuth app used to send numerous emails

**Severity**: Medium  

This alert indicates an OAuth app that has made numerous calls to Microsoft Graph API to send emails within a short time period. The app's publisher tenant is known to spawn a high volume of OAuth apps that make similar Microsoft Graph API calls. An attacker might be actively using this app to send spam or malicious emails to their targets.

**TP or FP?**

- **TP**: If you’re able to confirm that the consent request to the app was delivered from an unknown or external source and the app doesn't have a legitimate business use in the organization, then a true positive is indicated.

    **Recommended action**:
    - Contact users and admins who have granted consent to this app to confirm this was intentional and the excessive privileges are normal.
    - Investigate app activity and check affected accounts for suspicious activity.
    - Based on your investigation, disable the app and suspend and reset passwords for all affected accounts.
    - Classify the alert as a true positive.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization, then a false positive is indicated.

    **Recommended Action**: Classify the alert as a false positive and consider sharing feedback based on your investigation of the alert.

**Understand the scope of the breach**

Review consent grants to the application made by users and admins. Investigate all activities done by the app, especially access to mailbox of associated users and admin accounts. If you suspect that the app is suspicious, consider disabling the application and rotating credentials of all affected accounts.

## Persistence alerts

This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.

### App made anomalous Graph calls to Exchange workload post certificate update or addition of new credentials

**Severity**: Medium

**MITRE ID**: T1098.001, T1114

This detection triggers an alert when a Line of Business (LOB) app updated certificate/secrets or added new credentials and within few days post certificate update or addition of new credentials, observed unusual activities or high-volume usage to Exchange workload through Graph API using Machine learning algorithm.

**TP or FP?**

- **TP**: If you’re able to confirm that unusual activities/high volume usage to Exchange workload was performed by the LOB app through Graph API  

  **Recommend action**: Temporarily disable the app and reset the password and then re-enable the app.

- **FP**: If you can confirm that no unusual activities were performed by LOB app or app is intended to do unusually high volume of graph calls.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities performed by this app.
1. Review the scopes granted by the app.
1. Review the user activity associated with this app.

### App with suspicious OAuth scope was flagged high-risk by Machine Learning model, made graph calls to read email and created Inbox Rule

**Severity**: Medium

**MITRE ID**: T1137.005, T1114

This detection identifies an OAuth App that was flagged high-risk by Machine Learning model that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API. Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.

**TP or FP?**

- **TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is detected.

  **Recommended action**: Disable and remove the app, reset the password, and remove the inbox rule.

Follow the tutorial on how to Reset a password using Microsoft Entra ID and follow the tutorial on how to remove the inbox rule.

- **FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities done by the app.
1. Review the scopes granted by the app.
1. Review the inbox rule action and condition created by the app.

### App with suspicious OAuth scope made graph calls to read email and created inbox rule  

**Severity**: Medium

**MITRE ID’s**: T1137.005, T1114  

This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API. Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.  

**TP or FP?**

- **TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.

  **Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.

  Follow the tutorial on how to Reset a password using Microsoft Entra ID and follow the tutorial on how to remove the inbox rule.

- **FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities done by the app.
1. Review the scopes granted by the app.
1. Review the inbox rule action and condition created by the app.

### App accessed from unusual location post certificate update

**Severity**: Low

**MITRE ID**: T1098

This detection triggers an alert when a Line of Business (LOB) app was updated the certificate / secret and within few days post certificate update, app is accessed from unusual location that wasn't seen recently or never accessed in past.

**TP or FP?**

- **TP**: if you’re able to confirm that LOB app accessed from unusual location and performed unusual activities through Graph API.

    **Recommend action**: Temporarily disable the app and reset the password and then re-enable the app.

- **FP**: If you’re able to confirm that LOB app accessed from unusual location for legitimate purpose and no unusual activities performed.

    **Recommended Action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activity performed by this app.
1. Review the scopes granted by the app.
1. Review the user activity associated with this app.

### App accessed from unusual location made anomalous Graph calls post certificate update

**Severity**: Medium

**MITRE ID**: T1098

This detection triggers an alert when a Line of Business (LOB) app updated the certificate / secret and within few days post certificate update, app is accessed from an unusual location that wasn't seen recently or never accessed in past and observed unusual activities or usage through Graph API using Machine learning algorithm.

**TP or FP?**

- **TP**: If you’re able to confirm that unusual activities/usage was performed by the LOB app through Graph API from an unusual location.

    **Recommend action**: Temporarily disable the app and reset the password and then re-enable the app.

- **FP**: If you’re able to confirm that LOB app accessed from unusual location for legitimate purpose and no unusual activities performed.

    **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activity performed by this app.
1. Review the scopes granted by the app.
1. Review the user activity associated with this app.

### App created recently has a high volume of revoked consents

**Severity**: Medium  

**MITRE ID**: T1566, T1098

Several users have revoked their consent to this recently created line-of-business (LOB) or third-party app. This app might have lured users into giving it consent inadvertently.

**TP or FP?**

- **TP**: If you can confirm that the OAuth app is delivered from an unknown source, and app behavior is suspicious.  

  **Recommended Action**: Revoke consents granted to the app and disable the app.  

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization and no unusual activities were performed by the app.

  **Recommended Action**: Dismiss the alert  

**Understand the scope of the breach**

1. Review all activities performed by the app.  
1. If you suspect that an app is suspicious, we recommend that you investigate the name and reply domain of the app in different app stores. When checking app stores, focus on the following types of apps:
   - Apps that have been created recently
   - Apps with an unusual display name
   - Apps with a suspicious Reply domain
1. If you still suspect that an app is suspicious, you can research the app display name and reply domain.

### App metadata associated with known phishing campaign

**Severity**: Medium

This detection generates alerts for non-Microsoft OAuth apps with metadata, such as *name*, *URL*, or *publisher*, that had previously been observed in apps associated with a phishing campaign. These apps might be part of the same campaign and might be involved in exfiltration of sensitive information.

**TP or FP?**

- **TP**: If you are able to confirm that the OAuth app is delivered from an unknown source and is performing unusual activities.

   **Recommended action**: 
    - Investigate the app's registration details on app governance and visit Microsoft Entra ID for more details. 
    - Contact the users or admins who granted consent or permissions to the app. Verify whether the changes were intentional.
    - Search the *CloudAppEvents* Advanced hunting table to understand app activity and determine if the observed behavior is expected.
    - Verify whether the app is critical to your organization before considering any containment actions. Deactivate the app using app governance or Microsoft Entra ID to prevent it from accessing resources. Existing app governance policies might have already deactivated the app.

- **FP**: If you can confirm that no unusual activities were performed by the app and that the app has a legitimate business use in the organization.

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted to the app.
1. Review the user activity associated with the app.


### App metadata associated with previously flagged suspicious apps

**Severity**: Medium

This detection generates alerts for non-Microsoft OAuth apps with metadata, such as *name*, *URL*, or *publisher*, that had previously been observed in apps flagged by app governance due to suspicious activity. This app might be part of an attack campaign and might be involved in exfiltration of sensitive information.

**TP or FP?**

- **TP**: If you are able to confirm that the OAuth app is delivered from an unknown source and is performing unusual activities.

   **Recommended action**:
    - Investigate the app's registration details on app governance and visit Microsoft Entra ID for more details.
    - Contact the users or admins who granted consent or permissions to the app. Verify whether the changes were intentional.
    - Search the *CloudAppEvents* Advanced hunting table to understand app activity and determine if the observed behavior is expected.
    - Verify whether the app is critical to your organization before considering any containment actions. Deactivate the app using app governance or Microsoft Entra ID to prevent it from accessing resources. Existing app governance policies might have already deactivated the app.

- **FP**: If you can confirm that no unusual activities were performed by the app and that the app has a legitimate business use in the organization.

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted to the app.
1. Review the user activity associated with the app.

### Suspicious OAuth app email activity through Graph API

**Severity**: High

This detection generates alerts for multitenant OAuth apps, registered by users with a high risk sign in, that made calls to Microsoft Graph API to perform suspicious email activities within a short period of time.

This detection verifies whether the API calls were made for mailbox rule creation, create reply email, forward email, reply, or new emails being sent. Apps that trigger this alert might be actively sending spam or malicious emails to other targets or exfiltrating confidential data and clearing tracks to evade detection.

**TP or FP?**

- **TP**: If you’re able to confirm that the app creation and consent request to the app was delivered from an unknown or external source and the app doesn't have a legitimate business use in the organization, then a true positive is indicated.

    **Recommended action**:

    - Contact users and admins who have granted consent to this app to confirm this was intentional and the excessive privileges are normal.

    - Investigate app activity and check affected accounts for suspicious activity.

    - Based on your investigation, disable the app and suspend and reset passwords for all affected accounts and remove the inbox rule.

    - Classify the alert as a true positive.


- **FP**: If, after investigation, you can confirm that the app has a legitimate business use in the organization, then a false positive is indicated.

    **Recommended action**:  

    - Classify the alert as a false positive and consider sharing feedback based on your investigation of the alert.

    - Understand the scope of the breach:

      Review consent grants to the application made by users and admins. Investigate all activities done by the app, especially access to mailbox of associated users and admin accounts. If you suspect that the app is suspicious, consider disabling the application and rotating credentials of all affected accounts.

### Suspicious OAuth app email activity through EWS API

**Severity**: High

This detection generates alerts for multitenant OAuth apps, registered by users with a high-risky sign in, that made calls to Microsoft Exchange Web Services (EWS) API to perform suspicious email activities within a short period of time.

This detection verifies whether the API calls were made to update inbox rules, move items, delete email, delete folder, or delete attachment. Apps that trigger this alert might be actively exfiltrating or deleting confidential data and clearing tracks to evade detection.

**TP or FP?**

- **TP**: If you’re able to confirm that the app creation and consent request to the app was delivered from an unknown or external source and the app doesn't have a legitimate business use in the organization, then a true positive is indicated.

    **Recommended action**:

    - Contact users and admins who have granted consent to this app to confirm this was intentional and the excessive privileges are normal.

    - Investigate app activity and check affected accounts for suspicious activity.

    - Based on your investigation, disable the app and suspend and reset passwords for all affected accounts and remove the inbox rule.

    - Classify the alert as a true positive.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization, then a false positive is indicated.

    **Recommended Action**:  

    - Classify the alert as a false positive and consider sharing feedback based on your investigation of the alert.

    - Understand the scope of the breach:

      Review consent grants to the application made by users and admins. Investigate all activities done by the app, especially access to mailbox of associated users and admin accounts. If you suspect that the app is suspicious, consider disabling the application and rotating credentials of all affected accounts.

## Privilege escalation alerts

### OAuth app with suspicious metadata has Exchange permission

**Severity**: Medium

**MITRE ID**: T1078

This alert is triggered when a line of business app with suspicious metadata has privilege to manage permission over Exchange.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app is delivered from an unknown source, and has suspicious metadata characteristics, then a true positive is indicated.

**Recommended Action**:  Revoke consents granted to the app and disable the app.

**FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

**Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities done by the app.
2. Review the scopes granted by the app.
3. Review the user activity associated with the app.

## Defense Evasion alerts

### App impersonating a Microsoft logo

**Severity**: Medium  

A non-Microsoft cloud app is using a logo that was found by a machine learning algorithm to be similar to a Microsoft logo. This can be an attempt to impersonate Microsoft software products and appear legitimate.

> [!NOTE]
> Tenant admins will need to provide consent via pop up to have required data sent outside the current compliance boundary and to select partner teams within Microsoft in order to enable this threat detection for line-of-business apps.
>

**TP or FP?**

- **TP**: If you can confirm that the app logo is an imitation of a Microsoft logo, and the app behavior is suspicious.  

  **Recommended Action**: Revoke consents granted to the app and disable the app.

- **FP**: If you can confirm that the app logo isn't an imitation of a Microsoft logo or no unusual activities were performed by the app.  

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted to the app.
1. Review the user activity associated with the app.

### App is associated with a typosquatted domain

**Severity**: Medium  

This detection generates alerts for non-Microsoft OAuth apps with publisher domains or redirect URLs that contain typosquatted versions of Microsoft brand names. Typosquatting is generally used to capture traffic to sites whenever users inadvertently mistype URLs, but they can also be used to impersonate popular software products and services.

**TP or FP?**

- **TP**: If you can confirm that the publisher domain or redirect URL of the app is typosquatted and doesn't relate to the true identity of the app.

  **Recommended action**:
    - Investigate the app's registration details on app governance and visit Microsoft Entra ID for more details.
    - Check the app for other signs of spoofing or impersonation and any suspicious activity.
    - Verify whether the app is critical to your organization before considering any containment actions. Deactivate the app using app governance to prevent it from accessing resources. Existing app governance policies might have already deactivated the app.

- **FP**: If you can confirm that the publisher domain and redirect URL of the app are legitimate.  

  **Recommended Action**: Classify the alert as a false positive and consider sharing feedback based on your investigation of the alert.

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted to the app.
1. Review the user activity associated with the app.

## Credential access

This section describes alerts indicating that a malicious actor may be attempting to read sensitive credential data, and consists of techniques for stealing credentials like account names, secrets, tokens, certificates, and passwords in your organization.

### Application initiating multiple failed KeyVault read activity with no success

**Severity**: Medium

**MITRE ID**: T1078.004

This detection identifies an application in your tenant that was observed making multiple read action calls to the KeyVault using Azure Resource Manager API in a short interval, with only failures and no successful read activity being completed.

**TP or FP?**
 
- **TP**: If the app is unknown or not being used, the given activity is potentially suspicious. After verifying the Azure resource being used and validating the app use in the tenant, the given activity may require that the app be disabled. This is usually evidence of suspected enumeration activity against the KeyVault resource to gain access to credentials for lateral movement or privilege escalation.
 
  **Recommended actions**: Review the Azure resources accessed or created by the application and any recent changes made to the application. Based on your investigation, choose whether you want to ban access to this app. Review the permission level requested by this app and which users have granted access.
 
- **FP**: If, after investigation, you can confirm that the app has legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.
 
**Understand the scope of the breach**
 
1. Review the app's access and activity.
1. Review all activities done by the app since its creation.
1. Review the scopes granted by the app in Graph API and the Role granted to it in your subscription.
1. Review any user who might have accessed the app prior to the activity.

## Discovery alerts

### App performed drive enumeration

**Severity**: Medium

**MITRE ID**: T1087

This detection identifies an OAuth app that was detected by Machine Learning model performing enumeration on OneDrive files using Graph API.  

**TP or FP?**

- **TP**: If you’re able to confirm that unusual activities/usage to OneDrive was performed by the LOB app through Graph API.

  **Recommended action**: Disable and remove the app and reset the password.

- **FP**: If you can confirm that no unusual activities were performed by app.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities performed by this app.
1. Review the scopes granted by the app.
1. Review the user activity associated with this app.

### Suspicious enumeration activities performed using Microsoft Graph PowerShell

**Severity**: Medium

**MITRE ID**: T1087

This detection identifies a large volume of suspicious enumeration activities performed within a short time span through a [Microsoft Graph PowerShell](/powershell/microsoftgraph/overview) application.

**TP or FP?**

- **TP**: If you’re able to confirm that suspicious/unusual enumeration activities were performed by the Microsoft Graph PowerShell application.

  **Recommended action**: Disable and remove the application and reset the password.

- **FP**: If you can confirm that no unusual activities were performed by application.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities performed by this application.
1. Review the user activity associated with this application.

### Recently created multitenant application enumerates users information frequently

**Severity**: Medium

**MITRE ID**: T1087

This alert finds OAuth apps registered recently in a relatively new publisher tenant with permissions to change mailbox settings and access emails. It verifies whether the app has made numerous calls to Microsoft Graph API requesting user directory information. Apps that trigger this alert might be luring users into granting consent so they can access organizational data.

**TP or FP?**

- **TP**: If you’re able to confirm that the consent request to the app was delivered from an unknown or external source and the app doesn't have a legitimate business use in the organization, then a true positive is indicated.

  **Recommended action**:
    - Contact users and admins who have granted consent to this app to confirm this was intentional and the excessive privileges are normal.
    - Investigate app activity and check affected accounts for suspicious activity. 
    - Based on your investigation, disable the app and suspend and reset passwords for all affected accounts.
    - Classify the alert as a true positive.  
  
- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization, then a false positive is indicated.

    **Recommended Action**: Classify the alert as a false positive and consider sharing feedback based on your investigation of the alert.

**Understand the scope of the breach**

Review consent grants to the application made by users and admins. Investigate all activities done by the app, especially enumeration of user directory information. If you suspect that the app is suspicious, consider disabling the application and rotating credentials of all affected accounts. 

## Exfiltration alerts

This section describes alerts indicating that a malicious actor may be attempting to steal data of interest to their goal from your organization.

### OAuth App using unusual user agent

**Severity**: Low

**MITRE ID**: T1567

This detection identifies an OAuth application that is using an unusual user agent to access the Graph API.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app has recently started using a new user agent that wasn't used previously and this change is unexpected, then a true positive is indicated.

  **Recommended actions**: Review the user agents used and any recent changes made to the application. Based on your investigation, you can choose to ban access to this app. Review the level of permission requested by this app and which users have granted access.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review the apps that are created recently and the user agents used.
2. Review all activities done by the app.  
3. Review the scopes granted by the app.  

### App with an unusual user agent accessed email data through Exchange Web Services

**Severity**: High

**MITRE ID**: T1114, T1567

This detection identifies an OAuth app that used an unusual user agent to access email data using Exchange Web services API.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth application isn't expected to change the user agent it uses to make requests to the Exchange Web Services API, then a true positive is indicated.

  **Recommended actions**: Classify the alert as a TP. Based on the investigation, if the app is malicious, you can revoke consents and disable the app in the tenant. If it's a compromised app, you can revoke the consents, temporarily disable the app, review the permissions, reset the secret and certificate and then re-enable the app.

- **FP**: If after investigation, you can confirm that the user agent used by the application has a legitimate business use in the organization.

  **Recommended action**: Classify the alert as an FP. Also, consider sharing feedback based on your investigation of the alert.

**Understand the scope of the breach**

1. Review if the application was newly created or has had any recent changes made to it.
2. Review the permissions granted to the application and users that have consented to the application.
3. Review all activities done by the app.

## Lateral movement alerts

This section describes alerts indicating that a malicious actor may be attempting to laterally move within different resources, while pivoting through multiple systems and accounts to gain more control in your organization.

### Dormant OAuth App predominantly using MS Graph or Exchange Web Services recently seen to be accessing ARM workloads

**Severity**: Medium

**MITRE ID**: T1078.004

This detection identifies an application in your tenant that has, after a long span of dormant activity, started accessing the Azure Resource Manager API for the first time. Previously, this application had mostly using MS Graph or Exchange Web Service.
 
**TP or FP?**

- **TP**: If the app is unknown or not being used, the given activity is potentially suspicious and may require disabling the app, after verifying the Azure resource being used, and validating the app usage in the tenant.

  **Recommended actions**:

  1. Review the Azure resources accessed or created by the application and any recent changes made to the application.
  1. Review the level of permission requested by this app and which users have granted access.
  1. Based on your investigation, choose whether you want to ban access to this app. 
 
- **FP**: If, after investigation, you can confirm that the app has legitimate business use in the organization.
 
  **Recommended action**: Dismiss the alert.
 
**Understand the scope of the breach**
 
1. Review the app's access and activity.
1. Review all activities done by the app since its creation.
1. Review the scopes granted by the app in Graph API and the Role granted to it in your subscription.
1. Review any user who might have accessed the app prior to the activity.

## Collection alerts

This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.

### App made unusual email search activities

**Severity**: Medium

**MITRE ID**: T1114

This detection identifies when an app consented to suspicious OAuth scope and made a high volume of unusual email search activities, such as email search for specific content through the Graph API. This can indicate an attempted breach of your organization, such as adversaries attempting to search and read specific email from your organization through Graph API.  

**TP or FP?**

- **TP**: If you can confirm a high volume of unusual email search and read activities through the Graph API by an OAuth app with a suspicious OAuth scope and that the app is delivered from unknown source.

  **Recommended actions**: Disable and remove the app, reset the password, and remove the inbox rule.  

- **FP**: If you can confirm the app has performed high volume of unusual email search and read through Graph API for legitimate reasons.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review the scopes granted by the app.
1. Review all activities done by the app.  

### App made anomalous Graph calls to read e-mail

**Severity**: Medium

**MITRE ID**: T1114

This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.

**TP or FP?**

- **TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.

  **Recommended actions**: Temporarily disable the app and reset the password and then re-enable the app. Follow the tutorial on how to Reset a password using Microsoft Entra ID.

- **FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.
1. Monitor for unexpected credential being added to the app.

### App creates inbox rule and made unusual email searches activities

**Severity**: Medium

**MITRE IDs**: T1137, T1114  

This detection identifies App consented to high privilege scope, creates suspicious inbox rule, and made unusual email search activities in users mail folders through Graph API. This can indicate an attempted breach of your organization, such as adversaries attempting to search and collect specific emails from your organization through Graph API.

**TP or FP?**

- **TP**: If you’re able to confirm any specific emails search and collection done through Graph API by an OAuth app with high privilege scope, and the app is delivered from unknown source.

    **Recommended action**: Disable and remove the app, reset the password, and remove the inbox rule.

- **FP**: If you’re able to confirm app has performed specific email search and collection through Graph API and created an inbox rule to a new or personal external email account for legitimate reasons.

    **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities done by the app.
1. Review the scopes granted by the app.
1. Review any inbox rule action created by the app.
1. Review any email search activities done by the app.

### App made OneDrive / SharePoint search activities and created inbox rule  

**Severity**: Medium

**MITRE ID’s**: T1137, T1213

This detection identifies that an App consented to high privilege scope, created a suspicious inbox rule, and made unusual SharePoint or OneDrive search activities through Graph API. This can indicate an attempted breach of your organization, such as adversaries attempting to search and collect specific data from SharePoint or OneDrive from your organization through Graph API.  

**TP or FP?**

- **TP**: If you’re able to confirm any specific data from SharePoint or OneDrive search and collection done through Graph API by an OAuth app with high privilege scope, and the app is delivered from unknown source.  

  **Recommended Action**:  Disable and remove the App, reset the password, and remove the inbox rule.  

- **FP**: If you’re able to confirm app has performed specific data from SharePoint or OneDrive search and collection through Graph API by an OAuth app and created an inbox rule to a new or personal external email account for legitimate reasons.  

  **Recommended Action**: Dismiss the alert  

**Understand the scope of the breach**

1. Review all activities done by the app.  
1. Review the scopes granted by the app.  
1. Review any inbox rule action created by the app.  
1. Review any SharePoint or OneDrive search activities done by the app.

### App made numerous searches and edits in OneDrive

**Severity**: Medium

**MITRE IDs**: T1137, T1213

This detection identifies OAuth apps with high privilege permissions that perform a large number of searches and edits in OneDrive using Graph API.

**TP or FP?**

- **TP**: If you’re able to confirm that a high usage of OneDrive workload via Graph API isn't expected from this OAuth application having high privilege permissions to read and write to OneDrive, then a true positive is indicated.

  **Recommended Action**: Based on the investigation, if the application is malicious, you can revoke consents and disable the application in the tenant. If it's a compromised application, you can revoke the consents, temporarily disable the app, review the required permissions, reset the password and then re-enable the app.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended Action**: Resolve the alert and report your findings.

**Understand the scope of the breach**

1. Verify if the app is from a reliable source.
1. Verify if the application was newly created or has had any recent changes made to it.
1. Review the permissions granted to the application and users that have consented to the application.
1. Investigate all other app activities.

### App made high volume of importance mail read and created inbox rule

**Severity**: Medium  

**MITRE IDs**: T1137, T1114

This detection identifies that an App consented to high privilege scope, creates suspicious inbox rule and made a high volume of important mail read activities through Graph API. This can indicate an attempted breach of your organization, such as adversaries attempting to read high importance email from your organization through Graph API.  

**TP or FP?**

- **TP**: If you’re able to confirm that high volume of important email read through Graph API by an OAuth app with high privilege scope, and the app is delivered from unknown source.  

  **Recommended Action**:  Disable and remove the App, reset the password, and remove the inbox rule.  

- **FP**: If you’re able to confirm app has performed high volume of important email read through Graph API and created an inbox rule to a new or personal external email account for legitimate reasons.  

  **Recommended Action**: Dismiss the alert  

**Understand the scope of the breach**

1. Review all activities done by the app.  
1. Review the scopes granted by the app.  
1. Review any inbox rule action created by the app.  
1. Review any high importance email read activity done by the app.

### Privileged app performed unusual activities in Teams

**Severity**: Medium

This detection identifies apps consented to high privilege OAuth scopes, that accessed Microsoft Teams, and made an unusual volume of read or post chat message activities through Graph API. This can indicate an attempted breach of your organization, such as adversaries attempting to gather information from your organization through Graph API.

**TP or FP?**

- **TP**: If you’re able to confirm that unusual chat message activities in Microsoft Teams through Graph API by an OAuth app with a high privilege scope, and the app is delivered from an unknown source.

  **Recommended Action**:  Disable and remove the app and reset the password

- **FP**: If you’re able to confirm that the unusual activities performed in Microsoft Teams through Graph API were for legitimate reasons.

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review the scopes granted by the app.
1. Review all activities done by the app.
1. Review the user activity associated with the app.

### Anomalous OneDrive activity by app that just updated or added new credentials

**Severity**: Medium

**MITRE IDs**: T1098.001, T1213

A non-Microsoft cloud app made anomalous Graph API calls to OneDrive, including high-volume data usage. Detected by machine learning, these unusual API calls were made within a few days after the app added new or updated existing certificates/secrets. This app might be involved in data exfiltration or other attempts to access and retrieve sensitive information.

**TP or FP?**

- **TP**: If you can confirm that unusual activities, such as high-volume usage of OneDrive workload, were performed by the app through Graph API.

  **Recommended Action**: Temporarily disable the app, reset the password and then re-enable the app.

- **FP**: If you can confirm that no unusual activities were performed by the app or that the app is intended to make unusually high volume of Graph calls.

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted by the app.
1. Review the user activity associated with the app.

### Anomalous SharePoint activity by app that just updated or added new credentials

**Severity**: Medium

**MITRE IDs**: T1098.001, T1213.002

A non-Microsoft cloud app made anomalous Graph API calls to SharePoint, including high-volume data usage. Detected by machine learning, these unusual API calls were made within a few days after the app added new or updated existing certificates/secrets. This app might be involved in data exfiltration or other attempts to access and retrieve sensitive information.

**TP or FP?**

- **TP**: If you can confirm that unusual activities, such as high-volume usage of SharePoint workload, were performed by the app through Graph API.

  **Recommended Action**: Temporarily disable the app, reset the password and then re-enable the app.

- **FP**: If you can confirm that no unusual activities were performed by the app or that the app is intended to make unusually high volume of Graph calls.

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted by the app.
1. Review the user activity associated with the app.

### App metadata associated with suspicious mail-related activity

**Severity**: Medium

**MITRE IDs**: T1114

This detection generates alerts for non-Microsoft OAuth apps with metadata, such as *name*, *URL*, or *publisher*, that had previously been observed in apps with suspicious mail-related activity. This app might be part of an attack campaign and might be involved in exfiltration of sensitive information.

**TP or FP?**

- **TP**: If you can confirm that the app has created mailbox rules or made a large number of unusual Graph API calls to the Exchange workload.

   **Recommended action**:
    - Investigate the app's registration details on app governance and visit Microsoft Entra ID for more details.
    - Contact the users or admins who granted consent or permissions to the app. Verify whether the changes were intentional.
    - Search the *CloudAppEvents* Advanced hunting table to understand app activity and identify data accessed by the app. Check affected mailboxes and review messages that might have been read or forwarded by the app itself or rules that it has created.
    - Verify whether the app is critical to your organization before considering any containment actions. Deactivate the app using app governance or Microsoft Entra ID to prevent it from accessing resources. Existing app governance policies might have already deactivated the app.

- **FP**: If you can confirm that no unusual activities were performed by the app and that the app has a legitimate business use in the organization.

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted to the app.
1. Review the user activity associated with the app.

### App with EWS application permissions accessing numerous emails

**Severity**: Medium

**MITRE IDs**: T1114

This detection generates alerts for multitenant cloud apps with EWS application permissions showing a significant increase in calls to the Exchange Web Services API that are specific to email enumeration and collection. This app might be involved in accessing and retrieving sensitive email data.

**TP or FP?**

- **TP**: If you can confirm that the app has accessed sensitive email data or made a large number of unusual calls to the Exchange workload.

   **Recommended action**:
    - Investigate the app's registration details on app governance and visit Microsoft Entra ID for more details.
    - Contact the users or admins who granted consent or permissions to the app. Verify whether the changes were intentional.
    - Search the *CloudAppEvents* Advanced hunting table to understand app activity and identify data accessed by the app. Check affected mailboxes and review messages that might have been read or forwarded by the app itself or rules that it has created.
    - Verify whether the app is critical to your organization before considering any containment actions. Deactivate the app using app governance or Microsoft Entra ID to prevent it from accessing resources. Existing app governance policies might have already deactivated the app.

- **FP**: If you can confirm that no unusual activities were performed by the app and that the app has a legitimate business use in the organization.

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted to the app.
1. Review the user activity associated with the app.

### Unused app newly accessing APIs

**Severity**: Medium

**MITRE IDs**: T1530

This detection generates alerts for a multitenant cloud app that has been inactive for a while and has recently started making API calls. This app may be compromised by an attacker and being used to access and retrieve sensitive data.

**TP or FP?**

- **TP**: If you can confirm that the app has accessed sensitive data or made a large number of unusual calls to Microsoft Graph, Exchange or Azure Resource Manager workloads.

   **Recommended action**:
    - Investigate the app's registration details on app governance and visit Microsoft Entra ID for more details.
    - Contact the users or admins who granted consent or permissions to the app. Verify whether the changes were intentional.
    - Search the *CloudAppEvents* Advanced hunting table to understand app activity and identify data accessed by the app. Check affected mailboxes and review messages that might have been read or forwarded by the app itself or rules that it has created.
    - Verify whether the app is critical to your organization before considering any containment actions. Deactivate the app using app governance or Microsoft Entra ID to prevent it from accessing resources. Existing app governance policies might have already deactivated the app.

- **FP**: If you can confirm that no unusual activities were performed by the app and that the app has a legitimate business use in the organization.

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted to the app.
1. Review the user activity associated with the app.
   
## Impact alerts

This section describes alerts indicating that a malicious actor may be attempting to  manipulate, interrupt, or destroy your systems and data from your organization.

### Entra Line-of-Business app initiating an anomalous spike in virtual machine creation

**Severity**: Medium

**MITRE ID**: T1496

This detection identifies a single tenant new OAuth application that's creating bulk of Azure Virtual Machines in your tenant using the Azure Resource Manager API.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app has recently been created and is creating large numbers of Virtual Machines in your tenant, then a true positive is indicated.

  **Recommended actions**: Review the Virtual machines created and any recent changes made to the application. Based on your investigation, you can choose to ban access to this app. Review the level of permission requested by this app and which users have granted access.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**:

1. Review the apps that are created recently and VMs created.
1. Review all activities done by the app since its creation.
1. Review the scopes granted by the app in Graph API and Role granted to it in your subscription.

### OAuth app with high scope privileges in Microsoft Graph was observed initiating virtual machine creation

**Severity**: Medium

**MITRE ID**: T1496

This detection identifies OAuth application that creating bulk of Azure Virtual Machines in your tenant using the Azure Resource Manager API while having high privilege in the tenant via MS Graph API prior to the activity.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app having high privilege scopes has been created and is creating large numbers of Virtual Machines in your tenant, then a true positive is indicated.

  **Recommended actions**: Review the Virtual machines created and any recent changes made to the application. Based on your investigation, you can choose to ban access to this app. Review the level of permission requested by this app and which users have granted access.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**:

1. Review the apps that are created recently and VMs created.
1. Review all activities done by the app since its creation.
1. Review the scopes granted by the app in Graph API and Role granted to it in your subscription.

## Next steps

[Manage app governance alerts](app-governance-manage-alerts.md)
