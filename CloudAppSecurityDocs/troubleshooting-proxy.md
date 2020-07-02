---
# required metadata

title: Troubleshooting proxy issues
description: This article provides a list of common access and session control errors and corresponding resolution recommendations.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 07/02/2020
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.suite: ems
---
# Troubleshooting access and session control

This article provides a list of common access and session control errors, and their corresponding resolution recommendations, as experienced by [admins](#admin-issues) and end-users.

Before you proceed, make sure your environment meets the following minimum general requirements for access and session controls.

- **Licensing**: Make sure you have a valid [license](https://aka.ms/mcaslicensing).
- **Single Sign-On (SSO)**: Apps must be configured with one of the supported SSO solutions.
  - Azure AD using SAML 2.0 or OpenID Connect 2.0
  - Third-party IdP using SAML 2.0
- **Browser support**: Session controls are available for browser-based sessions on these supported browsers: Microsoft Edge (latest), Google Chrome (latest), Mozilla Firefox (latest), or Apple Safari (latest)

## Admin issues

This section is for admins configuring access and session controls with Cloud App Security and helps identify common situations they may run into when working in the following areas:

- [Network conditions](#network-conditions)
- Device identification
- Onboarding an app
- Creating access and session policies

### Network conditions

The following common issues are included in this section:

- [Network errors when navigating to a browser page](#network-errors-when-navigating-to-a-browser-page)
- Slow login
- Navigating to a specific resource redirects me to an unexpected page
- Good to know

#### Network errors when navigating to a browser page

When you are first setting up Cloud App Security access and session controls for an app, common network errors that may arise include: "This site is not secure" and "There is no internet connection". These messages can indicate a general network configuration error.

**Recommended solution**:

1. Configure your firewall to work with Cloud App Security using the Azure IP addresses and DNS names relevant to your environment.
    1. Add **outbound port 443** for the following IP addresses and DNS names for your [Cloud App Security data center](network-requirements.md#access-and-session-controls).
    1. Restart your machine and your browser session
    1. Verify that the login is working as expected
1. Enable TLS 1.2 in your browser's internet options.

    > [!NOTE]
    > Cloud App Security leverages Transport Layer Security (TLS) protocols 1.2+ to provide best-in-class encryption. Native client apps and browsers that do not support TLS 1.2+ will not be accessible when configured with session control. However, SaaS apps that use TLS 1.1 or lower will appear in the browser as using TLS 1.2+ when configured with Cloud App Security.

    | Browser | Steps |
    |---|---|
    | Microsoft Internet Explorer | 1. Open **Internet Explorer**<br />2. Navigate to **Tools**<br />3. Select **Internet Options**<br />4. Go to the **Advanced tab** and scroll down to the **Security section**<br />5. Check the option box for **TLS 1.2**<br />6. Click **OK**<br />7. Restart your browser and verify that you can access the application |

<!--
Open Internet Explorer.
Select Tools > Internet Options > Security tab.
Select a zone to change the security settings.
Following are the zones:
- Internet
- Local intranet
- Trusted sites
- Restricted sites
Select the Enable Protected Mode check box for the all the zones.
Select Apply, and then select OK.
-->

