---
title: Investigate threat detection alerts
ms.date: 01/29/2023
ms.topic: conceptual
description: Learn how to investigate threat detection alerts from app governance.
---

# Investigate threat detection alerts

 App governance provides security detections and alerts for malicious activities. The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks. Included in this guide is general information about the conditions for triggering alerts. Because threat detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm. Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.

## MITRE ATT&CK

To make it easier to map the relationship between app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic. This additional reference makes it easier to understand the suspected attacks technique potentially in use when app governance alert is triggered.

This guide provides information about investigating and remediating app governance alerts in the following categories.

- [Initial Access](#initial-access-alerts)
- Execution
- [Persistence](#persistence-alerts)
- Privilege Escalation
- [Defense Evasion](#defense-evasion-alerts)
- Credential Access
- [Discovery](#discovery-alerts)
- Lateral Movement
- [Collection](#collection-alerts)
- [Exfiltration](#exfiltration-alerts)
- Impact

## Security alert classifications

Following proper investigation, all app governance alerts can be classified as one of the following activity types:

- True positive (TP): An alert on a confirmed malicious activity.
- Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.
- False positive (FP): An alert on a non-malicious activity.

## General investigation steps

Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.

- Review the app severity level and compare with the rest of the apps in your tenant. This review will help you identify which Apps in your tenant pose the greater risk.
- If you identify a TP, review all the App activities to gain an understanding of the impact. For example, review the following App information:

  - Scopes granted access
  - Unusual behavior  
  - IP address and location

## Initial access alerts

This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.  

### App redirects to phishing URL by exploiting OAuth redirection vulnerability

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

  To ban access to the app, go to thee OAuth apps page. On the row in which the app you want to ban appears, select the ban icon. You can choose whether you want to tell users the app they installed and authorized has been banned. The notification lets users know the app will be disabled, and they won't have access to the connected app. If you don't want them to know, unselect **Notify users who granted access to this banned app** in the dialog. We recommend that you let the app users know their app is about to be banned from use.

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

  To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon. You can choose whether you want to tell users the app they installed and authorized has been banned. The notification lets users know the app will be disabled and they will not have access to the connected app. If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog. We recommend that you let the app users know their app is about to be banned from use.

- **FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

Follow the tutorial on how to [investigate risky OAuth apps](./investigate-risky-oauth.md).

### OAuth App with Read scopes has suspicious Reply URL

**Severity**: Medium

**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API. This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.

  **Recommended action**: Review the Reply URL and scopes requested by the app. Based on your investigation you can choose to ban access to this app. Review the level of permission requested by this app and which users have granted access.

  To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon. You can choose whether you want to tell users the app they installed and authorized has been banned. The notification lets users know the app will be disabled and they will not have access to the connected app. If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog. We recommend that you let the app users know their app is about to be banned from use.

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

This detection identifies an OAuth application that was created recently in a relatively new publisher tenant. This app has mail permissions that will allow the app to access and/or change mailbox settings. The app also appears to have lower consent volume from targeted users. This can indicate a malicious or risky app that lures users into illicit consent grants via phishing.  

**TP or FP?**

- **TP**: If you’re able to confirm that the consent request to the app was delivered from an unknown or external source and the app does not have a legitimate business use in the organization, then a true positive is indicated. 

    **Recommended action**: 
    - Contact users and admins who have granted consent to this application to confirm this was intentional and the excessive privileges are normal. 
    - Investigate application activity and check affected accounts for suspicious activity. 
    - Based on your investigation, disable the app and suspend and reset passwords for all affected accounts.
    - Classify the alert as a TP in the portal.

- **FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization. 

    **Recommended Action**: Classify the alert as a FP in the portal and please consider sharing feedback based on your investigation of the alert.

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

Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.

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

  Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.

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

This detection triggers an alert when a Line of Business (LOB) app updated the certificate / secret and within few days post certificate update, app is accessed from an unusual location that was not seen recently or never accessed in past and observed unusual activities or usage through Graph API using Machine learning algorithm.

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

- **TP**: If you can confirm that the OAuth app is delivered from an unknown source and app behavior is suspicious.  

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

## Privilege escalation alerts

### OAuth app with suspicious metadata has Exchange permission

**Severity**: Medium

**MITRE ID**: T1078

This alert is triggered when a line of business app with suspicious metadata has privilege to manage permission over Exchange.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app is delivered from an unknown source, and has suspicious metadata characteristics, then a true positive is indicated.

**Recommended Action**:  Revoke consents granted to the app and disable the app.

**FP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.

**Recommended Action**:: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities done by the app.
2. Review the scopes granted by the app.
3. Review the user activity associated with the app.

## Defense Evasion alerts

### App impersonating a Microsoft logo

**Severity**: Medium  

A non-Microsoft cloud app is using a logo that was found by a machine learning algorithm to be very similar to a Microsoft logo. This can be an attempt to impersonate Microsoft software products and appear legitimate.

**TP or FP?**

- **TP**: If you can confirm that the app logo is an imitation of a Microsoft logo and the app behavior is suspicious.  

  **Recommended Action**: Revoke consents granted to the app and disable the app.

- **FP**: If you can confirm that the app logo is not an imitation of a Microsoft logo or no unusual activities were performed by the app.  

  **Recommended Action**: Dismiss the alert

**Understand the scope of the breach**

1. Review all activities performed by the app.
1. Review the scopes granted to the app.
1. Review the user activity associated with the app.

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

### Suspicious enumeration activities performed using Azure Active Directory PowerShell

**Severity**: Medium

**MITRE ID**: T1087

This detection identifies a large volume of suspicious enumeration activities performed within a short time span through an Azure AD PowerShell application.

**TP or FP?**

- **TP**: If you’re able to confirm that suspicious/unusual enumeration activities were performed by the Azure AD PowerShell application.

  **Recommended action**: Disable and remove the application and reset the password.

- **FP**: If you can confirm that no unusual activities were performed by application.

  **Recommended action**: Dismiss the alert.

**Understand the scope of the breach**

1. Review all activities performed by this application.
1. Review the user activity associated with this application.

## Exfiltration alerts

This section describes alerts indicating that a malicious actor may be attempting to steal data of interest to their goal from your organization.

### OAuth App using unusual user agent

**Severity**: Low

**MITRE ID**: T1567

This detection identifies an OAuth application that is using an unusual user agent to access the Graph API.

**TP or FP?**

- **TP**: If you’re able to confirm that the OAuth app has recently started using a new user agent that was not used previously and this change is unexpected, then a true positive is indicated.

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

- **TP**: If you’re able to confirm that the OAuth application is not expected to change the user agent it uses to make requests to the Exchange Web Services API, then a true positive is indicated.

  **Recommended actions**: Classify the alert as a TP. Based on the investigation, if the app is malicious, you can revoke consents and disable the app in the tenant. If it is a compromised app, you can revoke the consents, temporarily disable the app, review the permissions, reset the secret and certificate and then re-enable the app.

- **FP**: If after investigation, you can confirm that the user agent used by the application has a legitimate business use in the organization.

  **Recommended action**: Classify the alert as a FP. Also, please consider sharing feedback based on your investigation of the alert.

**Understand the scope of the breach**

1. Review if the application was newly created or has had any recent changes made to it.
2. Review the permissions granted to the application and users that have consented to the application.
3. Review all activities done by the app.

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

  **Recommended actions**: Temporarily disable the app and reset the password and then re-enable the app. Follow the tutorial on how to Reset a password using Azure Active Directory.

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

- **TP**: If you’re able to confirm that a high usage of OneDrive workload via Graph API is not expected from this OAuth application having high privilege permissions to read and write to OneDrive, then a true positive is indicated.

  **Recommended Action**: Based on the investigation, if the application is malicious, you can revoke consents and disable the application in the tenant. If it is a compromised application, you can revoke the consents, temporarily disable the app, review the required permissions, reset the password and then re-enable the app.

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
