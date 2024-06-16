---
title: Classic portal -  Deploy Conditional Access App Control for catalog apps with Microsoft Entra ID
description: Classic portal -  This article provides information about how to deploy the Microsoft Defender for Cloud Apps Conditional Access App Control for catalog apps with Microsoft Entra ID.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---

# Classic portal: Deploy Conditional Access App Control for catalog apps with Microsoft Entra ID

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

Access and session controls in Microsoft Defender for Cloud Apps work with applications from the Cloud app catalog and with custom applications.

[!INCLUDE [classic-pre-onboarded-apps](includes/classic-pre-onboarded-apps.md)]

## Prerequisites

- Your organization must have the following licenses to use Conditional Access App Control:

  - [Microsoft Entra ID P1](/azure/active-directory/fundamentals/license-users-groups) or higher
  - Microsoft Defender for Cloud Apps
- Apps must be configured with single sign-on
- Apps must use one of the following authentication protocols:

   |IdP|Protocols|
   |---|---|
   |Microsoft Entra ID|SAML 2.0 or OpenID Connect|
   |Other|SAML 2.0|

## To deploy catalog apps

Follow the steps below to configure catalog apps to be controlled by Microsoft Defender for Cloud Apps Conditional Access App Control.

<a name='configure-integration-with-azure-ad'></a>

### Configure integration with Microsoft Entra ID

> [!NOTE]
> When configuring an application with SSO in Microsoft Entra ID, or other identity providers, one field that may be listed as optional is the sign-on URL setting. Note that this field may be required for Conditional Access App Control to work.

Use the following steps to create a Microsoft Entra Conditional Access policy that routes app sessions to Defender for Cloud Apps. For other IdP solutions, see [Configure integration with other IdP solutions](classic-proxy-deployment-featured-idp.md).

1. In Microsoft Entra ID, browse to **Security** > **Conditional Access**.
1. On the **Conditional Access** pane, in the toolbar at the top, select **New policy** -> **Create new policy**.
1. On the **New** pane, in the **Name** textbox, enter the policy name.
1. Under **Assignments**, select **Users or workload identities** and assign the users and groups that will be onboarding (initial sign-on and verification) the app.
1. Under **Assignments**, select **Cloud apps or actions** and assign the apps and actions you want to control with Conditional Access App Control.
1. Under **Access controls**, select **Session**, select **Use Conditional Access App Control**, and choose a built-in policy (**Monitor only (Preview)** or **Block downloads (Preview)**) or **Use custom policy** to set an advanced policy in Defender for Cloud Apps, and then select **Select**.

    ![Microsoft Entra Conditional Access.](media/classic-azure-ad-caac-policy.png)

1. Optionally, add conditions and grant controls as required.
1. Set **Enable policy** to **On** and then select **Create**.

> [!NOTE]
> Before proceeding, make sure to first sign out of existing sessions.

After you've created the policy, sign in to each app configured in that policy. Make sure you sign in using a user configured in the policy.

Defender for Cloud Apps will sync your policy details to its servers for each new app you sign in to. This may take up to one minute.

The preceding instructions helped you create a built-in Defender for Cloud Apps policy for catalog apps directly in Microsoft Entra ID. In this step, verify that the access and session controls are configured for these apps.

1. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), select the settings cog ![settings icon.](media/classic-settings-icon.png "settings icon"), and then select **Conditional Access App Control**.
1. In the Conditional Access App Control apps table, look at the **Available controls** column and verify that both **Access control** or **Microsoft Entra Conditional Access**, and **Session control** appear for your apps.

   > [!NOTE]
   > If the app isn’t enabled for session control, you can add it by selecting **Onboard with session control** and checking **Use this app with session controls**.
   > ![Onboard with session control.](media/proxy-deployment-aad/classic-onboardwithsessioncontrol.png)

Once you're ready to enable the app for use in your organization's production environment, do the following steps.

1. In Defender for Cloud Apps, select the settings cog ![settings icon.](media/classic-settings-icon.png), and then select **Conditional Access App Control**.
1. In the list of apps, on the row in which the app you're deploying appears, choose the three dots at the end of the row, and then choose **Edit app**.
1. Select **Use the app with session controls** and then select **Save**.

   ![Edit this app dialogue.](media/proxy-deployment-aad/classic-edit-app-checked.png)

1. First sign out of any existing sessions. Then, try to sign in to each app that was successfully deployed. Sign in using a user that matches the policy configured in Microsoft Entra ID, or for a SAML app configured with your identity provider.
1. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), under **Investigate**, select **Activity log**, and make sure the login activities are captured for each app.
1. You can filter by clicking on **Advanced**, and then filtering using **Source equals Access control**.

    ![Filter using Microsoft Entra Conditional Access.](media/classic-sso-logon.png)

1. It's recommended that you sign into mobile and desktop apps from managed and unmanaged devices. This is to make sure that the activities are properly captured in the activity log.  
   To verify that the activity is properly captured, select a single sign-on login activity so that it opens the activity drawer. Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).

> [!NOTE]
> After it is deployed, you can't remove an app from the Conditional Access App Control page. As long as you don't set a session or access policy on the app, the Conditional Access App Control won't change any behavior for the app.

## Next steps

> [!div class="nextstepaction"]
> [« PREVIOUS: Introduction to Conditional Access App Control](proxy-intro-aad.md)

> [!div class="nextstepaction"]
> [NEXT: Deploy Conditional Access App Control for any app »](classic-proxy-deployment-any-app.md)

> [!div class="nextstepaction"]
> [Troubleshooting access and session controls](troubleshooting-proxy.md)

[!INCLUDE [Open support ticket](includes/classic-support.md)]
