---
title: Deploy conditional access app control for catalog apps with Microsoft Entra ID | Microsoft Defender for Cloud Apps
description: This article provides information about how to deploy Microsoft Defender for Cloud Apps conditional access app control for catalog apps with Microsoft Entra ID.
ms.date: 05/20/2024
ms.topic: how-to
#customerIntent: To deploy conditional access app control for catalog apps with Microsoft Entra ID
---

# Deploy conditional access app control for catalog apps with Microsoft Entra ID

Access and session controls in Microsoft Defender for Cloud Apps work with applications from the Cloud app catalog and with custom applications. For a list of apps that are pre-onboarded and work out of the box, see [Protect apps with Defender for Cloud Apps conditional access app control](proxy-intro-aad.md#pre-onboarded-apps).

## Prerequisites

- Your organization must have the following licenses to use conditional access app control:

  - [Microsoft Entra ID P1](/azure/active-directory/fundamentals/license-users-groups) or higher
  - Microsoft Defender for Cloud Apps

- Apps must be configured with single sign-on
- Apps must use one of the following authentication protocols:

   |IdP|Protocols|
   |---|---|
   |Microsoft Entra ID|SAML 2.0 or OpenID Connect|
   |Other|SAML 2.0|

<a name='configure-integration-with-azure-ad'></a>

## Configure the Microsoft Entra ID integration

> [!NOTE]
> When configuring an application with SSO in Microsoft Entra ID, or other identity providers, one field that may be listed as optional is the sign-on URL setting. Note that this field may be required for conditional access app control to work.

Use the following steps to create a Microsoft Entra Conditional Access policy that routes app sessions to Defender for Cloud Apps. For other IdP solutions, see [Configure integration with other IdP solutions](proxy-deployment-featured-idp.md).

1. In the Microsoft Entra admin center, search for **Microsoft Entra Conditional Access**.
1. On the **Conditional Access** pane, in the toolbar at the top, select **New policy** -> **Create new policy**.
1. On the **New** pane, in the **Name** textbox, enter the policy name.
1. Under **Assignments**, select the link to assign users and groups that will be onboarding (initial sign-on and verification) the app.
1. Under **Target resources**, select the link to assign the target resources, including the apps and actions you want to control with conditional access app control.
1. Under **Access controls**, select the link to open the **Session** pane. There, select **Use Conditional Access App Control**, and choose a built-in policy (**Monitor only (Preview)** or **Block downloads (Preview)**) or **Use custom policy** to set an advanced policy in Defender for Cloud Apps, and then select **Select**.

    ![Screenshot of the Microsoft Entra Conditional Access page.](media/azure-ad-caac-policy.png)

1. Optionally, add conditions and grant controls as required.
1. Set **Enable policy** to **On** and then select **Create**.

> [!NOTE]
> Before proceeding, make sure to first sign out of existing sessions.

After you've created the policy, sign in to each app configured in that policy. Make sure you sign in using a user configured in the policy.

Defender for Cloud Apps will sync your policy details to its servers for each new app you sign in to. This may take up to one minute.

## Verify that access and session controls are configured

The preceding instructions helped you create a built-in Defender for Cloud Apps policy for catalog apps directly in Microsoft Entra ID. In this step, verify that the access and session controls are configured for these apps.

1. In the Microsoft Defender Portal, select **Settings**. Then choose **Cloud Apps**.

1. Under **Connected apps**, select **Conditional Access App Control apps**. Look at the **Available controls** column and verify that both **Access control** or **Azure AD Conditional Access**, and **Session control** appear for your apps.

   If the app isn’t enabled for session control, add it by selecting **Onboard with session control** and checking **Use this app with session controls**. For example:

    ![Screenshot of onboarding with session control.](media/proxy-deployment-aad/onboard-with-session-control.png)

## Enable your app for use in production

When you're ready, this procedure describes how to enable the app for use in your organization's production environment.

1. In the Microsoft Defender Portal, select **Settings**. Then choose **Cloud Apps**.

1. Under **Connected apps**, select **Conditional Access App Control apps**. In the list of apps, on the row in which the app you're deploying appears, choose the three dots at the end of the row, and then choose **Edit app**.

1. Select **Enable the app to work on session controls** and then select **Save**. For example:

   :::image type="content" source="media/proxy-deployment-aad/edit-app.png" alt-text="Screenshot of the Edit this app? dialog.":::

1. First sign out of any existing sessions. Then, try to sign in to each app that was successfully deployed. Sign in using a user that matches the policy configured in Microsoft Entra ID, or for a SAML app configured with your identity provider.

1. In the Microsoft Defender Portal, under **Cloud Apps**, select **Activity log**, and make sure the login activities are captured for each app.

1. You can filter by selecting **Advanced**, and then filtering using **Source equals Access control**. For example:

    ![Screenshot of filtering using Microsoft Entra Conditional Access.](media/sso-logon.png)

1. We recommend that you sign into mobile and desktop apps from managed and unmanaged devices. This is to make sure that the activities are properly captured in the activity log.  

   To verify that the activity is properly captured, select a single sign-on login activity so that it opens the activity drawer. Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).

> [!NOTE]
> After it's deployed, you can't remove an app from the Conditional Access App Control page. As long as you don't set a session or access policy on the app, the conditional access app control won't change any behavior for the app.

## Next steps

> [!div class="nextstepaction"]
> [« PREVIOUS: Introduction to conditional access app control](proxy-intro-aad.md)

> [!div class="nextstepaction"]
> [NEXT: Deploy conditional access app control for any app »](proxy-deployment-any-app.md)

> [!div class="nextstepaction"]
> [Troubleshooting access and session controls](troubleshooting-proxy.md)

[!INCLUDE [Open support ticket](includes/support.md)]
