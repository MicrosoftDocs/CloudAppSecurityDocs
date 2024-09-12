---
title: Conditional access app control | Microsoft Defender for Cloud Apps
description: Learn how Microsoft Defender for Cloud Apps provides Conditional Access app control.
ms.date: 02/29/2024
ms.topic: conceptual
---
# Microsoft Defender for Cloud Apps conditional access app control

In today's workplace, it's not enough to know what's happened in your cloud environment after the fact. You also need to stop breaches and leaks in real-time, and prevent employees from intentionally or accidentally putting your data and organization at risk.

You want to support users in your organization while they use the best cloud apps available and bring their own devices to work. However, you also need tools to protect your organization from data leaks and theft in real time. Microsoft Defender for Cloud Apps integrates with any identity provider (IdP) to deliver this protection with [access](access-policy-aad.md) and [session](session-policy-aad.md) policies.

For example:

- **Use access policies to:**

    - Block access to Salesforce for users coming from unmanaged devices
    - Block access to Dropbox for native clients.

- **Use session policies to**:

    - Block downloads of sensitive files from OneDrive to unmanaged devices
    - Block uploads of malware files to SharePoint Online

Microsoft Edge users benefit from [direct, in-browser protection](in-browser-protection.md), indicated by the lock :::image type="icon" source="media/in-browser-protection/lock.png" border="false"::: icon shown in the browser's address bar.

Users of other browsers are redirected via a reverse proxy to Defender for Cloud Apps, and display an `*.mcas.ms` suffix in the link's URL. For example, if the app URL is *myapp.com*, the app URL is updated to *myapp.com.mcas.ms*.

This article describes Defender for Cloud Apps's Conditional Access app control with [Microsoft Entra Conditional Access](/entra/identity/conditional-access/overview) policies.

## Conditional Access app control activities

Conditional Access app control uses *access policies* and *session policies* to monitor and control user app access and sessions in real time, across your organization. 

Each policy has conditions to define *who* (which user or group of users), *what* (which cloud apps), and *where* (which locations and networks) the policy is applied to. After determining the conditions, route your users first to Defender for Cloud Apps, where you can apply the access and session controls to protect your data.

Access and session policies include the following types of activities:

|Activity  |Description  |
|---------|---------|
|**Prevent data exfiltration**     |  Block the download, cut, copy, and print of sensitive documents on, for example, unmanaged devices.       |
| **Require authentication context** | Reevaluate Microsoft Entra Conditional Access policies when a sensitive action occurs in the session, such as requiring multifactor authentication. |
|**Protect on download**     |    Instead of blocking the download of sensitive documents, require documents to be labeled and encrypted when you integrate with Microsoft Purview Information Protection. This action ensures the document is protected and user access is restricted in a potentially risky session.     |
|**Prevent upload of unlabeled files**     |  Ensure that unlabeled files with sensitive content are blocked from being uploaded until the user classifies the content. Before a sensitive file is uploaded, distributed, and used by others, it's important to make sure that the sensitive file has the label defined by your organization's policy.        |
|**Block potential malware**     |  Protect your environment from malware by blocking the upload of potentially malicious files. Any file that is uploaded or downloaded can be scanned against Microsoft threat intelligence and blocked instantaneously.       |
|**Monitor user sessions for compliance**     |  Investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future.   Risky users are monitored when they sign into apps and their actions are logged from within the session.     |
|**Block access**     |   Granularly block access for specific apps and users depending on several risk factors. For example, you can block them if they're using client certificates as a form of device management.      |
|**Block custom activities**     |  Some apps have unique scenarios that carry risk, for example, sending messages with sensitive content in apps like Microsoft Teams or Slack. In these kinds of scenarios, scan messages for sensitive content and block them in real time.       |

For more information, see:

- [Create Microsoft Defender for Cloud Apps access policies](access-policy-aad.md)
- [Create Microsoft Defender for Cloud Apps session policies](session-policy-aad.md)

## Usability

Conditional Access app control doesn't require you to install anything on the device, making it ideal when monitoring or controlling sessions from unmanaged devices or partner users.

Defender for Cloud Apps uses best-in-class, patented heuristics to identify and control activities performed by the user in the target app. Our heuristics are designed to optimize and balance security with usability.

In some rare scenarios, when blocking activities on the server-side renders the app unusable, we secure these activities only on the client-side, which makes them potentially susceptible to exploitation by malicious insiders.

## System performance and data storage

Defender for Cloud Apps uses Azure Data Centers around the world to provide optimized performance through geolocation. This means that a user's session may be hosted outside of a particular region, depending on traffic patterns and their location. However, to protect your privacy, no session data is stored in these data centers.

Defender for Cloud Apps proxy servers do not store data at rest. When caching content, we follow the requirements laid out in [RFC 7234 (HTTP caching)](https://tools.ietf.org/html/rfc7234) and only cache public content.

## Supported apps and clients

Apply session and access to controls to any interactive single sign-on that uses the SAML 2.0 authentication protocol. Access controls are also supported for built-in mobile and desktop client apps.

Additionally, if you're using Microsoft Entra ID apps, apply session and access controls to:

- Any interactive single sign-on that uses the Open ID Connect authentication protocol.
- Apps hosted on-premises and configured with the [Microsoft Entra application proxy](/entra/identity/app-proxy/application-proxy).

Microsoft Entra ID apps are also automatically onboarded for Conditional Access app control, while apps that use other IdPs must be [onboarded manually](conditional-access-app-control-how-to-overview.md).

Defender for Cloud Apps identifies apps using data from the cloud app catalog. If you've customized apps with plugins, any associated custom domains must be added to the relevant app in the catalog. For more information, see [Working with the risk score](risk-score.md).

> [!NOTE]
> Installed apps with *non-interactive* sign-in flows, such as the Authenticator app and other built-in apps, cannot be used with Access controls. Our recommendation in that case is to craft an Access policy in Entra ID portal in addition to Microsoft defender for cloud apps access policies
>

## Session control support scope

While session controls are built to work with any browser on any major platform on any operating system, we support the following browsers:

- [Microsoft Edge](https://www.microsoft.com/edge) (latest)
- [Google Chrome](https://www.google.com/chrome/) (latest)
- [Mozilla Firefox](https://www.mozilla.org/firefox/) (latest)
- [Apple Safari](https://www.apple.com/safari/) (latest)

Microsoft Edge users benefit from in-browser protection, without redirecting to a reverse proxy. For more information, see [In-browser protection with Microsoft Edge for Business (Preview)](in-browser-protection.md).

## App support for TLS 1.2+

Defender for Cloud Apps uses Transport Layer Security (TLS) protocols 1.2+ to provide best-in-class encryption, and built-in client apps and browsers that do not support TLS 1.2+ aren't accessible when configured with session control.

However, SaaS apps that use TLS 1.1 or lower will appear in the browser as using TLS 1.2+ when configured with Defender for Cloud Apps.

## Related content

For more information, see:

- [Conditional Access app control known limitations](caac-known-issues.md)
- [Troubleshooting access and session controls](troubleshooting-proxy.md)
