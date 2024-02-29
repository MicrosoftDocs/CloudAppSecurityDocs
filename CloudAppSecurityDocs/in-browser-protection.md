---
title: In-browser protection with Microsoft Edge for Business | Microsoft Defender for Cloud Apps
description: Learn how to apply in-browser protection with Microsoft Defender for Cloud Apps session policies and Microsoft Edge for Business
ms.date: 02/29/2024
ms.topic: how-to
---

# In-browser protection with Microsoft Edge for Business (Preview)

Defender for Cloud Apps users who use Microsoft Edge for Business and are subject to session policies are protected directly from within the browser. In-browser protection reduces the need for proxies, improving both security and productivity.

Microsoft Edge for Business supports separate profiles for work and personal use, allowing users and organizations to separate browsing data into independent silos. For example, personal favorites and history aren't synchronized with the work account if you set up separate profiles for work and personal use. The work and personal profiles have separate caches and storage locations to keep information separate.

In-browser protection is applied on the work profile only, where users experience a smoother experience with their cloud apps. In-browser protection provides less latency and fewer incompatibilities, with higher levels of security protection from attackers.

## Prerequisites

This section lists the supported platforms for in-browser protection with Microsoft Edge for Business.

|Requirement  |Description  |
|---------|---------|
|**Operating systems**     |   Windows 10 or 11      |
|**Identity platform**     | Microsoft Entra ID        |
|**Microsoft Edge for Business versions**     |   121 and higher      |
|**Supported session policies**     | - Block\Monitor of file download (all files\sensitive files) <br>- Block\Monitor file upload <br>- Block\Monitor copy\cut <br>- Block\Monitor print <br><br> Users that are served by multiple policies, including at least one policy that's *not* supported by Microsoft Edge for Business, their sessions are always served by the reverse proxy. <br><br>Policies defined in the Microsoft Entra ID portal are also always served by reverse proxy.   |

All other scenarios are served automatically with the standard reverse proxy technology including user sessions from browsers that don't support in-browser protection, or for policies not supported by in-browser protection.

For example, the following users are all served by the reverse proxy:

- Google Chrome users
- Microsoft Edge users who are scoped to a block paste policy
- Microsoft Edge users on Android devices
- Users in apps that use the OKTA authentication method
- Microsoft Edge users in InPrivate mode
- Microsoft Edge users with older browser versions
- B2B guest users

For more information, see [Protect apps with Microsoft Defender for Cloud Apps Conditional Access App Control](proxy-intro-aad.md).

## User access for in-browser protection

To benefit from in-browser protection with Microsoft Edge for Business, users must sign into the browser using their work profile. Users who attempt to access the cloud app from outside of their work profile are prompted to switch to their work profiles, or create a new one if it doesn’t exist.

For example, a user accessing a resource on contoso.com must use their user@contoso.com profile.

Users know that they're using the in-browser protection in Microsoft Edge for Business because they see an extra *"lock"* icon in the browser address bar. The icon indicates that the session is protected by Defender for Cloud Apps. For example:

:::image type="content" source="media/in-browser-protection/url-icon.png" alt-text="Screenshot of an extra lock icon in the browser address bar.":::

Also, the `.mcas.ms` suffix doesn't appear in the browser address bar with in-browser protection, as it does with standard conditional access app control, and developer tools are turned off with in-browser protection.

## Configure in-browser protection settings

In-browser protection with Microsoft Edge for Business is enabled by default. Admins can turn the integration off and on, and can configure a prompt for non-Edge users to switch to Microsoft Edge for enhanced performance and security.

**To configure in-browser protection settings:**

1. In Microsoft Defender XDR, select **Settings > Cloud Apps > Conditional Access App Control > Edge for Business integration**.

1. Configure the following settings as needed:

    - Toggle the **Turn on Edge for Business integration** option **Off** or **On**.
    - Select to **Notify users in non-Edge browsers to use Microsoft Edge for Business for better performance and security**.

        If you selected to notify non-Edge users, select to either use the default message or customize your own message.

1. Select **Save** when you're done to save your changes.

### Working with Microsoft Purview and Endpoint data loss prevention

If the same exact context and action are configured for both Defender for Cloud Apps policies and a Microsoft Purview Endpoint data loss prevention policy (DLP), the Endpoint DLP policy is applied.

For example, if you have an Endpoint DLP policy that blocks a file upload to Salesforce, and you also have a Defender for Cloud Apps policy that monitors file uploads to Salesforce, the Endpoint DLP policy is applied.

For more information, see [Learn about data loss prevention](/purview/dlp-learn-about-dlp).

## Related content

For more information, see [Microsoft Defender for Cloud Apps conditional access app control](proxy-intro-aad.md).
