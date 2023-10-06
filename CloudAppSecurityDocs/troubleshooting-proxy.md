---
title: Troubleshoot access and session controls for admins | Microsoft Defender for Cloud Apps
description: This article describes how to troubleshoot common access and session control issues experienced by admins with Microsoft Defender for Cloud Apps.
ms.date: 08/20/2023
ms.topic: troubleshooting
---

# Troubleshooting access and session controls for admin users

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides Microsoft Defender for Cloud Apps admins with guidance on how to investigate and resolve common access and session control issues as experienced by admins.

## Check minimum requirements

Before you start troubleshooting, make sure your environment meets the following minimum general requirements for access and session controls.

|Requirement  |Description  |
|---------|---------|
|**Licensing**     |   Make sure you have a valid [license](https://aka.ms/M365EnterprisePlans) for Microsoft Defender for Cloud Apps.      |
|**Single Sign-On (SSO)**     |  Apps must be configured with one of the supported SSO solutions: <br><br>  - Azure Active Directory (Azure AD) using SAML 2.0 or OpenID Connect 2.0 <br>- Non-Microsoft IdP using SAML 2.0       |
|**Browser support**     |  Session controls are available for browser-based sessions on the latest versions of the following browsers: <br><br>- Microsoft Edge<br>Google Chrome<br>Mozilla Firefox<br>or Apple Safari      |
|**Downtime**     |   Defender for Cloud Apps allows you to define the default behavior to apply if there's a service disruption, such as a component not functioning correctly. <br><br>For example, when the normal policy controls can't be enforced, you might choose to harden (block) or bypass (allow) users from taking actions on potentially sensitive content. <br><br>To configure the default behavior during system downtime, in Microsoft 365 Defender, go to **Settings** > **Conditional Access App Control** > **Default behavior** > **Allow** or **Block** access.      |

## Reference of troubleshooting issues for admins

Use the following table to find the issue you're trying to troubleshoot:

|Issue type  |Issues  |
|---------|---------|
|[Network condition issues](#network-condition-issues)     |  [Network errors when navigating to a browser page](#network-errors-when-navigating-to-a-browser-page) <br><br>[Slow sign-ins](#slow-sign-ins) <br><br> [More considerations for network conditions](#more-considerations-for-network-conditions)       |
|[Device identification issues](#device-identification-issues)    | [Misidentified Intune Compliant or Hybrid Azure AD joined devices](#misidentified-intune-compliant-or-hybrid-azure-ad-joined-devices) <br><br>[Client certificates aren't prompting when expected](#client-certificates-arent-prompting-when-expected)  <br><br> [Client certificates aren't prompting when expected](#client-certificates-arent-prompting-when-expected) <br> [Client certificates are prompting at every sign-in](#client-certificates-are-prompting-at-every-sign-in) <br><br>[More considerations for device identification](#more-considerations-for-device-identification)      |
|[Issues when onboarding an app](#issues-when-onboarding-an-app)     |  [App doesn't appear on the Conditional Access App Control apps page](#app-doesnt-appear-on-the-conditional-access-app-control-apps-page) <br><br> [App status: Continue Setup](#app-status-continue-setup)   [Can't configure controls for native apps](#cant-configure-controls-for-native-apps) <br><br> [*App isn't recognized* page appears](#app-isnt-recognized-page-appears) <br><br> [Request session control option appears](#request-session-control-option-appears)<br><br> [More considerations for onboarding apps](#more-considerations-for-onboarding-apps)    |
|[Issues when creating access and session policies](#issues-when-creating-access-and-session-policies)     | [In Conditional Access policies, you can't see the Conditional Access App Control option](#in-conditional-access-policies-you-cant-see-the-conditional-access-app-control-option) <br><br> [Error message when creating a policy: You don't have any apps deployed with Conditional Access App Control](#error-message-when-creating-a-policy-you-dont-have-any-apps-deployed-with-conditional-access-app-control) <br><br> [Can't create session policies for an app](#cant-create-session-policies-for-an-app) <br><br>[Can't choose Inspection Method: Data Classification Service](#cant-choose-inspection-method-data-classification-service) <br><br> [Can't choose Action: Protect](#cant-choose-action-protect) <br><br> [More considerations for onboarding apps](#more-considerations-for-onboarding-apps)        |
| [Diagnose and troubleshoot with the Admin View toolbar](#diagnose-and-troubleshoot-with-the-admin-view-toolbar) | [Bypass proxy session](#bypass-proxy-session) <br><br> [Record a session](#record-a-session) |

## Network condition issues

Common network condition issues you may encounter include:

- [Network errors when navigating to a browser page](#network-errors-when-navigating-to-a-browser-page)
- [Slow sign-in](#slow-sign-ins)
- [Extra considerations](#network-conditions-additional-considerations)

### Network errors when navigating to a browser page

When you're first setting up Defender for Cloud Apps access and session controls for an app, common network errors that may arise include: *This site isn't secure* and *There's no internet connection*. These messages can indicate a general network configuration error.

**Recommended steps**

1. Configure your firewall to work with Defender for Cloud Apps using the Azure IP addresses and DNS names relevant to your environment.
    1. Add **outbound port 443** for the following IP addresses and DNS names for your [Defender for Cloud Apps data center](network-requirements.md#access-and-session-controls).
    1. Restart your device and your browser session
    1. Verify that the sign-in is working as expected

1. Enable TLS 1.2 in your browser's internet options. For example:

    | Browser | Steps |
    |---|---|
    | **Microsoft Internet Explorer** | 1. Open Internet Explorer<br />2. Select **Tools** > **Internet Options** > **Advance** tab<br />3. Under **Security**, select **TLS 1.2**<br />4. Select **Apply**, and then select **OK**<br />5. Restart your browser and verify that you can access the app |
    | **Microsoft Edge / Edge Chromium** | 1. Open search from the taskbar and search for "Internet Options"<br />2. Select **Internet Options**<br />3. Under **Security**, select **TLS 1.2**<br />4. Select **Apply**, and then select **OK**<br />5. Restart your browser and verify that you can access the app |
    | **Google Chrome** | 1. Open Google Chrome<br />2. At the top-right, select **More** (3 vertical dots) > **Settings**<br />3. At the bottom, select **Advanced**<br />4. Under **System**, select **Open proxy settings**<br />5. On the **Advanced** tab, under **Security**, select **TLS 1.2**<br />6. Select **OK**<br />7. Restart your browser and verify that you're able to access the app |
    | **Mozilla Firefox** | 1. Open Mozilla Firefox<br />2. In the address bar and search for "about:config"<br />3. In the Search box, search for "TLS"<br />4. Double-click the entry for **security.tls.version.min**<br />5. Set the integer value to 3 to force TLS 1.2 as the minimum required version<br />6. Select **Save** (check mark to the right of the value box)<br />7. Restart your browser and verify that you're able to access the app |
    | **Safari** | If you're using Safari version 7 or greater, TLS 1.2 is automatically enabled |

Defender for Cloud Apps uses Transport Layer Security (TLS) protocols 1.2+ to provide best-in-class encryption:

- Native client apps and browsers that don't support TLS 1.2+ aren't accessible when configured with session control.
- SaaS apps that use TLS 1.1 or lower appear in the browser as using TLS 1.2+ when configured with Defender for Cloud Apps.

> [!TIP]
> While session controls are built to work with any browser on any major platform on any operating system, we support the latest versions of Microsoft Edge, Google Chrome, Mozilla Firefox, or Apple Safari. You may want to block or allow access specifically to mobile or desktop apps.
>


### Slow sign-ins

Proxy chaining and nonce-handling are some of the common issues that could result in slow sign-in performance.

**Recommended steps**

Configure your environment to remove any factors that might be causing slowness during sign-in. For example, you might have firewalls or forward proxy chaining configured, which connects two or more proxy servers to navigate to the intended page. You may also have other external factors affecting the slowness.

1. Identify whether proxy chaining is occurring in your environment.
1. Remove any forward proxies where possible.

Some apps use a nonce hash during authentication to prevent replay attacks. By default, Defender for Cloud Apps assumes that an app uses a nonce. If the app you're working with doesn't use nonce, disable nonce-handling for this app in Defender for Cloud Apps:

1. In Microsoft 365 Defender, select **Settings** > **Cloud Apps**. 
1. Under **Connected apps**, select **Conditional Access App Control apps**.
1. In the list of apps, on the row in which the app you're configuring appears, select the three dots at the end of the row, and then select **Edit** for your app.
1. Select **Nonce-handling** to expand the section and then clear **Enable nonce handling**.
1. Sign out of the app and close out all browser sessions.
1. Restart your browser and sign-in to the app again. Verify that the sign-in is working as expected.

<a name="network-conditions-additional-considerations"></a>

### More considerations for network conditions

While troubleshooting network conditions, also consider the following notes about the Defender for Cloud Apps proxy:

- **Verify whether your session is being routed to another data center**: Defender for Cloud Apps uses Azure Data Centers around the world to optimize performance through geolocation. 

    This means that a user's session may be hosted outside of a region, depending on traffic patterns and their location. However, to protect your privacy, no session data is stored in these data centers.

- **Proxy performance**: Deriving a performance baseline depends on many factors outside of the Defender for Cloud Apps proxy, such as:

  - What other proxies or gateways sit in series with this proxy
  - Where the user is coming from
  - Where the targeted resource resides
  - Specific requests on the page

  In general, any proxy adds latency. The advantages of the Defender for Cloud Apps proxy are:

  - Using the global availability of Azure domain controllers to geolocate users to the nearest node and reduce their round-trip distance. Azure domain controllers can geolocate on a scale that few services around the world have.

  - Using the integration with Azure AD Conditional Access to only route the sessions you want to proxy to our service, instead of all users in all situations.

## Device identification issues

Defender for Cloud Apps provides the following options for identifying a device's management state.

- Microsoft Intune compliance
- Hybrid Azure AD Domain joined
- Client certificates

For more information on device identification, see [Managed Device Identification](proxy-intro-aad.md#managed-device-identification).

Common device identification issues you may encounter include:

- [Misidentified Intune Compliant or Hybrid Azure AD joined devices](#misidentified-intune-compliant-or-hybrid-azure-ad-joined-devices)
- [Client certificates aren't prompting when expected](#client-certificates-arent-prompting-when-expected)
- [Client certificates are prompting at every sign-in](#client-certificates-are-prompting-at-every-sign-in)
- [Extra considerations](#device-identification-additional-considerations)

### Misidentified Intune Compliant or Hybrid Azure AD joined devices

Azure AD Conditional Access enables Intune-compliant and Hybrid Azure AD joined device information to be passed directly to Defender for Cloud Apps. In Defender for Cloud Apps, use the device state as a filter for access or session policies. 

For more information, see [Introduction to device management in Azure Active Directory](/azure/active-directory/devices/overview).

**Recommended steps**

1. In Microsoft 365 Defender, select **Settings** > **Cloud Apps**.
1. Under **Conditional Access App Control**, select **Device identification**. This page shows the device identification options available in Defender for Cloud Apps.
1. For **Intune compliant device identification** and **Hybrid Azure AD joined identification** respectively, select **View configuration** and verify that the services are set up. Services are automatically synced from Azure AD and Intune respectively.

1. Create an access or session policy with the **Device Tag** filter equal to **Hybrid Azure AD joined**, **Intune compliant**, or both.
1. In a browser, sign in to a device that is Hybrid Azure AD joined or Intune compliant based on your policy filter.
1. Verify that activities from these devices are populating the log. In Defender for Cloud Apps, on the **Activity log** page, [filter](activity-filters.md) on **Device Tag** equal to **Hybrid Azure AD joined**, **Intune compliant**, or both based on your policy filters.
1. If activities aren't populating in the Defender for Cloud Apps activity log, go to Azure AD and do the following steps:
    1. Under **Monitoring** > **Sign-ins**, verify that there are sign-in activities in logs.
    1. Select the relevant log entry for the device you logged into.
    1. In the **Details** pane, on the **Device info** tab, verify that the device is **Managed** (Hybrid Azure AD joined) or **Compliant** (Intune compliant). 

        If you can't verify either state, try another log entry or ensure that your device data is configured correctly in Azure AD.
    1. For Conditional Access, some browsers may require extra configuration such as installing an extension. For more information, see [Conditional Access browser support](/azure/active-directory/conditional-access/concept-conditional-access-conditions#supported-browsers).
    1. If you still don't see the device information in the **Sign-ins** page, open a support ticket for Azure AD.

### Client certificates aren't prompting when expected

The device identification mechanism can request authentication from relevant devices using client certificates. You can upload an X.509 root or intermediate certificate authority (CA) certificate, formatted in the PEM certificate format.

Certificates must contain the CA's public key, which is then used to sign the client certificates presented during a session. For more information, see [Client-certificate authenticated devices](proxy-intro-aad.md#client-certificate-authenticated-devices).

**Recommended steps**

1. In Microsoft 365 Defender, select **Settings** > **Cloud Apps**.

1. Under **Conditional Access App Control**, select **Device identification**. This page shows the device identification options available with Defender for Cloud Apps.

1. Verify that you uploaded an X.509 root or intermediate CA certificate. You must upload the CA certificate that's used to sign for your certificate authority.

1. Create an access or session policy with the **Device Tag** filter equal to **Valid client certificate**.

1. Make sure that your client certificate is:
    - Deployed using the PKCS #12 file format, typically a *.p12* or *.pfx* file extension
    - Installed in the user store, not the device store, of the device you're using for testing

1. Restart your browser session.

1. When logging in to the protected app:
    - Verify that you're redirected to the following URL syntax: `<https://*.managed.access-control.cas.ms/aad_login>`
    - If you're using iOS, make sure you're using the Safari browser.
    - If you're using Firefox, you must also [add the certificate to Firefox's own certificate store](https://www.jscape.com/blog/firefox-client-certificate). All other browsers use the same default certificate store.

1. Validate that the client certificate is prompted in your browser.

    If it doesn't appear, try a different browser. Most major browsers support performing a client certificate check. However, mobile and desktop apps often use built-in browsers that may not support this check and therefore affect authentication for these apps.

1. Verify that activities from these devices are populating the log. In Defender for Cloud Apps, on the **Activity log** page, add a [filter](activity-filters.md) on **Device Tag** equal to **Valid client certificate**.

1. If you still don't see the prompt, open a [support ticket](support-and-ts.md) and include the following information:

    - The details of the browser or native app where you experienced the problem
    - The operating system version, such as iOS/Android/Windows 10
    - Mention if the prompt is working on Microsoft Edge Chromium

### Client certificates are prompting at every sign-in

If you're experiencing the client certificate popping up after opening a new tab, this might be due to settings hidden within **Internet Options**. Verify your settings in your browser. For example:

**In Microsoft Internet Explorer**:

1. Open Internet Explorer and select **Tools** > **Internet Options** > **Advanced** tab.
1. Under **Security**, select **Don't prompt for Client Certificate selection when only one certificate exists** > Select **Apply** > **OK**. 
1. Restart your browser and verify that you can access the app without the extra prompts.

**In Microsoft Edge / Edge Chromium**:

1. Open search from the taskbar and search for *Internet Options*.
1. Select **Internet Options** > **Security** > **Local intranet** > **Custom level**.
1. Under **Miscellaneous** > **Don't prompt for Client Certificate selection when only one certificate exists**, select **Disable**.
1. Select **OK** > **Apply** > **OK**.
1. Restart your browser and verify that you can access the app without the extra prompts.

<a name="device-identification-additional-considerations"></a>

### More considerations for device identification

While troubleshooting device identification, you can require certificate revocation for Client Certificates.

Certificates that are revoked by the CA are no longer trusted. Selecting this option requires all certificates to pass the CRL protocol. If your client certificate doesn't contain a CRL endpoint, you can't connect from the managed device.

## Issues when onboarding an app

You can onboard the following types of apps for access and session controls:

- **Catalog apps**: Apps that come with session controls out-of-the-box as indicated by the **Session control** label.

- **Any (custom) apps**: Custom line-of-business (LOB) or on-premises apps can be onboarded to session controls by an admin.

For example:

![Screenshot of a proxy list showing catalog and any (custom) apps.](media/troubleshooting-onboarding.png)

When onboarding an app, make sure that you've followed the proxy deployment guides carefully. For more information, see:

1. [Deploy catalog apps with session controls](proxy-deployment-aad.md)
1. [Deploy custom LOB apps, nonfeatured SaaS apps, and on-premises apps hosted via the Azure AD app proxy with session controls](proxy-deployment-any-app.md)

Common scenarios you may encounter while onboarding an app include:

- [App doesn't appear on the **Conditional Access App Control apps** page](#app-doesnt-appear-on-the-conditional-access-app-control-apps-page)
- [App status: Continue Setup](#app-status-continue-setup)
- [Can't configure controls for native apps](#cant-configure-controls-for-native-apps)
- [*App isn't recognized* page appears](#app-isnt-recognized-page-appears)
- [**Request session control** option appears](#request-session-control-option-appears)
- [Extra considerations](#onboarding-apps-additional-considerations)

### App doesn't appear on the Conditional Access App Control apps page

When onboarding an app to Conditional Access App Control, the final deployment step is to have the end user navigate to the app. Do the steps in this section if the app isn't appearing as expected.

**Recommended steps**

1. Make sure your app meets the following Conditional Access app prerequisites, depending on your identity provider:

    - **Azure AD**:

        1. Make sure you have a valid license for Azure AD Premium P1 in addition to a Defender for Cloud Apps license.
        1. Make sure that the app uses the SAML 2.0  or the OpenID Connect protocol.
        1. Make sure that the app SSO in Azure AD.

    - **Non-Microsoft**:

        1. Make sure you have a valid Defender for Cloud Apps license.
        1. Create a duplicate app.
        1. Make sure that the app uses the SAML protocol.
        1. Validate that you have fully onboarded the app and the status of the app is **Connected**.

1. In your Azure AD policy, under the **Session**, make sure that the session is forced to route to Defender for Cloud Apps. This, in turn, allows the app to appear in on the **Conditional Access App Control apps** page, as follows:

    - **Conditional Access App Control** is selected.
    - In the built-in policies drop-down, **Monitor only** is selected

1. Make sure to navigate to the app in a new browser session by using a new incognito mode or by signing in again.

### App status: Continue Setup

An app's status can vary, and can include **Continue Setup**, **Connected**, or **No Activities**.

For apps connected via non-Microsoft identity providers (IdP), if the setup isn't complete, when accessing the app you'll see a page with the status of **Continue Setup**. Use the following steps complete the setup.

**Recommended steps**

1. Select **Continue Setup**.

1. Go through the [deployment guide](proxy-deployment-any-app.md) and verify that you have completed all the steps. Pay particular attention to the following notes:

    1. Make sure you create a new custom SAML app. You need this app to change the URLs and SAML attributes that might not be available in gallery apps.
    1. If your identity provider doesn't allow the reuse of the same identifier, also known as Entity ID or Audience, change the identifier of the original app.

### Can't configure controls for native apps

Native apps can be detected heuristically and you can use access policies to monitor or block them. Use the following steps to configure controls for native apps.

**Recommended steps**

1. In an access policy, add a **Client app** filter, and set it equal to **Mobile and desktop**.

1. Under **Actions**, select **Block**.
1. Optionally, customize the blocking message that your users get when they're unable to download files. For example, customize this message to *You must use a web browser to access this app*.
1. Test and validate that the control is working as expected.

### *App isn't recognized* page appears

Defender for Cloud Apps can recognize over 31,000 apps through the **Cloud App Catalog**.

If you're using a custom app that is configured through Azure AD SSO, and isn't one of the supported apps, you'll come across an **App is not recognized** page. To resolve the issue, you must configure the app on  Conditional Access App Control.

**Recommended steps**

1. In Microsoft 365 Defender, select **Settings** > **Cloud Apps**. Under **Connected apps**, select **Conditional Access App Control apps**.

1. In the banner, select **View new apps**.

1. In the list of new apps, locate the app that you're onboarding, select the **+** sign, and then select **Add**.

    1. Select whether the app is a **custom** or **standard** app.
    1. Continue through the wizard, make sure that specified **User-defined domains** are correct for the app you're configuring.

1. Verify that the app appears in the **Conditional Access App Control apps** page.

### Request session control option appears

After adding an app, you may see the **Request session control** option. This occurs because only catalog apps have out-of-the-box session controls. For any other app, you must go through a self-onboarding process.

**Recommended steps**

1. In Microsoft 365 Defender, select **Settings** > **Cloud Apps**.

1. Under **Conditional Access App Control**, select **App onboarding/maintenance**.

1. Enter the user principal name or email for the users that will be onboarding the app, and then select **Save**.

1. Go to the app that you're deploying. The page you see depends on whether the app is recognized. Do one of the following, depending on the page you see:

    - **Not recognized**. You see an *App not recognized* page that prompts you to configure your app. Do the following steps:

        1. [Add the app to Conditional Access App Control](proxy-deployment-any-app.md).
        1. [Add the domains for the app](proxy-deployment-any-app.md), and then return to the app and refresh the page.
        1. [Install the certificates for the app](proxy-deployment-any-app.md).

    - **Recognized**. If your app is recognized, you see an onboarding page prompting you to continue the app configuration process.  For more information, see [Deploy Conditional Access App Control for custom apps using Azure Active Directory](proxy-deployment-any-app.md).

        Make sure the app is configured with all domains required for the app to function correctly. To configure extra domains, proceed to [Add the domains for the app](proxy-deployment-any-app.md), and then return to the app page.

<a name="onboarding-apps-additional-considerations"></a>

### More considerations for onboarding apps

While troubleshooting onboarding apps, remember that apps in Conditional Access App Control don't align with Azure AD apps.

The app names in Azure AD and Defender for Cloud Apps might differ based on the ways the products identify apps. 

- Defender for Cloud Apps identifies apps using the app's domains and adds them to the [cloud app catalog](risk-score.md#the-cloud-app-catalog), where we have over 31,000 apps. Within each app, there you can view or add to the subset of domains. 

- In contrast, Azure AD identifies apps using service principals. For more information, see [app and service principal objects in Azure AD](/azure/active-directory/develop/app-objects-and-service-principals).

In practice, this difference means that selecting **SharePoint Online** in Azure AD is equivalent to selecting apps, such as Word Online and Teams, in Defender for Cloud Apps because the apps all use the `sharepoint.com` domain.

## Issues when creating access and session policies

Defender for Cloud Apps provides the following configurable policies:

- [Access policies](access-policy-aad.md): Used to monitor or block access to browser, mobile, and/or desktop apps.
- [Session policies](session-policy-aad.md). Used to monitor, block, and perform specific actions to prevent data infiltration and exfiltration scenarios in the browser.

To use these policies in Defender for Cloud Apps, you must first configure a policy in Azure AD Conditional Access to extend session controls:

1. In the Azure AD policy, under **Access controls**, select **Session** > **Use Conditional Access App Control**.

1. Select a built-in policy (**Monitor only** or **Block downloads**) or **Use custom policy** to set an advanced policy in Defender for Cloud Apps.

1. Select **Select** to continue.

Common scenarios you may encounter while configuring these policies include:

- [In Conditional Access policies, you can't see the Conditional Access App Control option](#in-conditional-access-policies-you-cant-see-the-conditional-access-app-control-option)
- [Error message when creating a policy: You don't have any apps deployed with Conditional Access App Control](#error-message-when-creating-a-policy-you-dont-have-any-apps-deployed-with-conditional-access-app-control)
- [Can't create session policies for an app](#cant-create-session-policies-for-an-app)
- [Can't choose **Inspection Method**: **Data Classification Service**](#cant-choose-inspection-method-data-classification-service)
- [Can't choose **Action**: **Protect**](#cant-choose-action-protect)
- [Extra considerations](#policies-additional-considerations)

### In Conditional Access policies, you can't see the Conditional Access App Control option

To route sessions to Defender for Cloud Apps, Azure AD Conditional Access policies must be configured to include Conditional Access App Control session controls.

**Recommended steps**

If you don't see the **Conditional Access App Control** option in your Conditional Access policy, make sure that you have a valid license for Azure AD Premium P1 and a valid Defender for Cloud Apps license.

### Error message when creating a policy: You don't have any apps deployed with Conditional Access App Control

When creating an access or session policy, you may see the following error message: *You don't have any apps deployed with Conditional Access App Control*. This error indicates that the app hasn't been deployed.

**Recommended steps**

1. In Microsoft 365 Defender, select **Settings** > **Cloud Apps**. Under **Connected apps**, select **Conditional Access App Control apps**.

1. If you see the message **No apps connected**, use the following guides to deploy apps:

    - [Deploy catalog apps that have session control enabled](proxy-deployment-aad.md)
    - [Deploy custom line-of-business apps, nonfeatured SaaS apps, and on-premises apps](proxy-deployment-any-app.md) hosted via the Azure Active Directory (Azure AD) Application Proxy with session controls

If you run into any issues while deploying the app, see [Issues when onboarding an app](#issues-when-onboarding-an-app).

### Can't create session policies for an app

After adding a custom app, in the **Conditional Access App Control apps** page, you may see the option: **Request session control**.

> [!NOTE]
> [Catalog apps](proxy-intro-aad.md#session-controls) have out-of-the-box session controls. For any other apps, you must go through a self-onboarding process.

**Recommended steps**

1. Deploy your app to session control. For more information, see [Deploy custom line-of-business apps, nonfeatured SaaS apps, and on-premises apps](proxy-deployment-any-app.md) hosted via the Azure Active Directory (Azure AD) Application Proxy with session controls.

1. Create a session policy and select the **App** filter.

1. Make sure that your app is now listed in the dropdown list.

### Can't choose Inspection Method: Data Classification Service

In session policies, when using the **Control file download (with inspection)** session control type, you can use the **Data Classification Service** inspection method to scan your files in real time and detect sensitive content that matches any of the criteria you have configured. 

If the **Data Classification Service** inspection method isn't available, use the following steps to investigate the issue.

**Recommended steps**

1. Verify that the **Session control type** is set to **Control file download (with inspection)**.

   > [!NOTE]
   > The **Data Classification Service** inspection method is only available for the **Control file download (with inspection)** option.

1. Determine whether the **Data Classification Service** feature is available in your [region](dcs-inspection.md):

    - If the feature isn't available in your region, use the **Built-in DLP** inspection method.
    - If the feature is available in your region but you still can't see the **Data Classification Service** inspection method, open a [support ticket](support-and-ts.md).

### Can't choose Action: Protect

In session policies, when using the **Control file download (with inspection)** session control type, in addition to the **Monitor** and **Block** actions, you can specify the **Protect** action. This action enables you to permit file downloads with the option to encrypt or apply permissions to the file based on conditions, content inspection, or both. 

If the **Protect** action isn't available, use the following steps to investigate the issue.

**Recommended steps**

1. If the **Protect** action isn't available or is greyed out, verify that you have the Azure Information Protection (AIP) Premium P1 license. For more information, see [Microsoft Purview Information Protection integration](azip-integration.md).

1. If the **Protect** action is available, but aren't seeing the appropriate labels.

    1. In Defender for Cloud Apps, in the menu bar, select the settings icon > **Microsoft Information Protection**, and verify that the integration is enabled.

    1. For Office labels, in the AIP portal, make sure **Unified Labeling** is selected.

<a name="policies-additional-considerations"></a>

### More considerations for onboarding apps

While troubleshooting for onboarding apps, there are some extra things to consider.

- **Understand the difference between the Azure AD Conditional Access policy settings: "Monitor only", "Block downloads", and "Use custom policy"**

    In Azure AD Conditional Access policies, you can configure the following built-in Defender for Cloud Apps controls: **Monitor only** and **Block downloads**. These settings apply and enforce the Defender for Cloud Apps proxy feature for cloud apps and conditions configured in Azure AD. 

    For more complex policies, select **Use custom policy**, which allows you to configure access and session policies in Defender for Cloud Apps.

- **Understand the "Mobile and desktop" client app filter option in access policies**

    In Defender for Cloud Apps access policies, unless the **Client app** filter is set to **Mobile and desktop**, the resulting access policy applies to browser sessions. 

    The reason for this is to prevent inadvertently proxying user sessions, which may be a byproduct of using this filter.

## Diagnose and troubleshoot with the Admin View toolbar

The Admin View toolbar provides tools for an admin to diagnose and troubleshoot issues with Conditional Access App Control.

To enable the Admin View toolbar for specific admin users, you first must add admins to the app onboarding/maintenance list.

1. In Microsoft 365 Defender, select **Settings** > **Cloud Apps**.

1. Under **Conditional Access App Control**, select **App onboarding/maintenance**.

1. Enter the user principal name or email address for the admin users that will be onboarding the app.

1. Check the box for **Enable these users to bypass Conditional Access App Control from inside a proxied session** and select **Save**.

    For example:

    ![Screenshot of the App onboarding/maintenance settings.](media/app-onboarding-maintenance.png)

When those users next start a session of an application, the Admin View toolbar is available.

### Bypass proxy session

If you have difficulty accessing or loading your application, and you'd like to see if the problem is with the Conditional Access proxy, you can use the **Bypass session** button in the Admin View toolbar. It appears for users who have the [Admin View toolbar](#diagnose-and-troubleshoot-with-the-admin-view-toolbar) enabled.

For example:

![Screenshot of the Bypass option in the Admin View toolbar.](media/troubleshooting-proxy/proxy-admin-toolbar-bypass.png)

Once you select **Bypass**, the application runs without the Conditional Access proxy. Confirm that the session is bypassed by noting that the URL isn't [suffixed](proxy-intro-aad.md#how-session-control-works).

In the next session of the application, the Conditional Access proxy will be used.

### Record a session

You can help the root cause analysis of problems by providing session recordings to Microsoft support engineers. To record a session, you must enable the [Admin View toolbar](#diagnose-and-troubleshoot-with-the-admin-view-toolbar).

> [!NOTE]
> All personal data is removed from the recordings.

**To record a session from the Admin View toolbar**:

1. From the Admin View toolbar, select **Record session**. For example:

   ![Screenshot of the Record session button.](media/troubleshooting-proxy/proxy-admin-toolbar-record.png)

1. After selecting **Record session**, accept the terms by selecting **Continue** in the next window. For example:

    ![Screenshot of the session recording privacy statement dialog.](media/accept-continue.png)

**To record a session when signing into an app**:

1. To start recording when signing in to the application, select **Record session** when prompted. For example:

    ![Screenshot of selecting to record a session when signing into an app.](media/app-monitored.png)

1. Sign in to the application to begin the scenario simulation.

1. When you finish the scenario simulation, select **Stop recording** in the Admin View toolbar. For example:

    ![Screenshot of selecting to Stop recording.](media/troubleshooting-proxy/proxy-admin-toolbar-stop-recording.png)

**To view your recorded sessions**: 

After you've finished recording, you can view the recorded sessions by selecting **Session recordings** in the Admin View toolbar. A list of recorded sessions from the previous 48 hours appear. For example:

   ![Screenshot of session recordings.](media/troubleshooting-proxy/recording-list.png)

Each recorded session can be downloaded or deleted. For each session listing, select the delete icon to delete the recording, or the download icon to download the recording. For example:

![Screenshot of downloading or deleting a recording.](media/download-delete-recording.png)

## Next steps

For more information, see [Troubleshooting access and session controls for end-users](troubleshooting-proxy-end-users.md).
