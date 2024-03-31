---
title: Deploy conditional access app control for catalog apps with non-Microsoft IdP
description: This article provides information about how to deploy the Microsoft Defender for Cloud Apps conditional access app control reverse proxy features for catalog apps with non-Microsoft IdP.
ms.date: 01/29/2023
ms.topic: how-to
---
# Deploy conditional access app control for catalog apps with non-Microsoft IdP

<a name=configure-integration-with-other-idp-solutions></a>

Access and session controls in Microsoft Defender for Cloud Apps work with applications from the Cloud app catalog and with custom applications. For a list of apps that are pre-onboarded by Defender for Cloud Apps to work out-of-the-box, see [Protect apps with Defender for Cloud Apps conditional access app control](proxy-intro-aad.md#pre-onboarded-apps).

## Prerequisites

- Your organization must have the following licenses to use conditional access app control:

  - The license required by your identity provider (IdP) solution
  - Microsoft Defender for Cloud Apps

- Apps must be configured with single sign-on
- Apps must use one of the following authentication protocols:

    |IdP|Protocols|
    |---|---|
    |Microsoft Entra ID|SAML 2.0 or OpenID Connect|
    |Other|SAML 2.0|

## Configure your IdP to work with Defender for Cloud Apps

Use the following steps to route app sessions from other IdP solutions to Defender for Cloud Apps. For Microsoft Entra ID, see [Configure integration with Microsoft Entra ID](proxy-deployment-aad.md).

> [!NOTE]
> For examples of how to configure IdP solutions, see:
>
> - [Configure your PingOne IdP](proxy-idp-pingone.md)
> - [Configure your AD FS IdP](proxy-idp-adfs.md)
> - [Configure your Okta IdP](proxy-idp-okta.md)

1. In the Microsoft Defender Portal, select **Settings**. Then choose **Cloud Apps**.

1. Under **Connected apps**, select **Conditional Access App Control apps**.

1. Select **+ Add**, and in the pop-up, select the app you want to deploy, and then select **Start Wizard**.

1. On the **APP INFORMATION** page, fill out the form using the information from your app's single sign-on configuration page, and then select **Next**.

    - If your IdP provides a single sign-on metadata file for the selected app, select **Upload metadata file from the app** and upload the metadata file.

    - Or, select **Fill in data manually** and provide the following information:

        - **Assertion consumer service URL**
        - If your app provides a SAML certificate, select **Use <app_name> SAML certificate** and upload the certificate file.

    For example:

    ![Screenshot showing the APP INFORMATION area of the Add a SAML application with your identity provider dialog.](media/proxy-deploy-add-idp-app-info.png)

1. On the **IDENTITY PROVIDER** page, use the provided steps to set up a new application in your IdP's portal, and then select **Next**.

1. Go to your IdP's portal and create a new custom SAML app.

1. Copy the single sign-on configuration of the existing `<app_name>` app to the new custom app.

1. Assign users to the new custom app.

1. Copy the apps single sign-on configuration information. You'll need it in the next step. For example:

    ![Screenshot showing the Identity provider / External configuration area of the Add a SAML application with your identity provider dialog.](media/proxy-deploy-add-idp-get-conf.png)

    > [!NOTE]
    > These steps may differ slightly depending on your identity provider. This step is recommended for the following reasons:
    >
    > - Some identity providers do not allow you to change the SAML attributes or URL properties of a gallery app.
    >
    > - Configuring a custom app enables you to test this application with access and session controls without changing the existing behavior for your organization.

1. On the next page, fill out the form using the information from your app's single sign-on configuration page, and then select **Next**.

    - If your IdP provides a single sign-on metadata file for the selected app, select **Upload metadata file from the app** and upload the metadata file.

    - Or, select **Fill in data manually** and provide the following information:

        - **Assertion consumer service URL**
        - If your app provides a SAML certificate, select **Use <app_name> SAML certificate** and upload the certificate file.

    For example:

    ![Screenshot showing the Identity provider / Fill in data manually area of the Add a SAML application with your identity provider dialog.](media/proxy-deploy-add-idp-enter-conf.png)

1. On the next page, copy the following information, and then select **Next**. You'll need the information in the next step.

    - Single sign-on URL
    - Attributes and values

    For example:

    ![Screenshot showing the Identity provider area of the Add a SAML application with your identity provider dialog, with sample details entered.](media/proxy-deploy-add-idp-ext-conf.png)

1. In your IdP's portal, configure the following settings, commonly found in the IdP portal's custom app settings page.

    1. In the single sign-on URL field, enter the single sign-on URL you made a note of earlier. 

    1. Add the attributes and values you made a note of earlier to the app's properties. Some providers may refer to them as *User attributes* or *Claims*.

        When creating a new SAML app, the Okta Identity Provider limits attributes to 1024 characters. To mitigate this limitation, first create the app without the relevant attributes. After creating the app, edit it, and then add the relevant attributes.

    1. Verify that the name identifier is in the email address format.

    1. Save your settings.

1. On the **APP CHANGES** page, do the following, and then select **Next**. You'll need the information in the next step.

    - Copy the Single sign-on URL
    - Download the Defender for Cloud Apps SAML certificate

    For example:

    ![Screenshot showing the App changes area of the Add a SAML application with your identity provider dialog.](media/proxy-deploy-add-idp-app-changes.png)

1. In your app's portal, on the single sign-on settings, do the following:

    1. (Recommended) Create a backup of your current settings.

    1. Replace the **Identity Provider Login URL** field value with the Defender for Cloud Apps SAML single sign-on URL you noted earlier.

    1. Upload the Defender for Cloud Apps SAML certificate you downloaded earlier.

    1. Select **Save**.

After saving your settings, all associated sign-in requests to this app will be routed through conditional access app control.

The Defender for Cloud Apps SAML certificate is valid for one year. After it expires, a new certificate will need to be generated.

## Sign in to each app using a user scoped to the policy<a name="sign-in-scoped"></a>

> [!NOTE]
> Before proceeding, make sure to first sign out of existing sessions.

After you've created the policy, sign in to each app configured in that policy. Make sure you sign in using a user configured in the policy.

Defender for Cloud Apps will sync your policy details to its servers for each new app you sign in to. This may take up to one minute.

## Verify the apps are configured to use access and session controls<a name="portal"></a>

The preceding instructions helped you create a built-in Defender for Cloud Apps policy for catalog apps directly in Microsoft Entra ID. In this step, verify that the access and session controls are configured for these apps.

1. In the Microsoft Defender Portal, select **Settings**. Then choose **Cloud Apps**.

1. Under **Connected apps**, select **Conditional Access App Control apps**.

1. In the apps table, look at the **Available controls** column and verify that both **Access control** or **Azure AD Conditional Access**, and **Session control** appear for your apps.

    If the app isn't enabled for session control, add it by selecting **Onboard with session control** and checking **Use this app with session controls**. For example:

    ![Screenshot of the Onboard with session control link.](media/proxy-deployment-aad/onboard-with-session-control.png)

## Enable the app for use in your organization<a name="enable-app"></a>

Once you're ready to enable the app for use in your organization's production environment, do the following steps.

1. In the Microsoft Defender Portal, select **Settings**. Then choose **Cloud Apps**.

1. Under **Connected apps**, select **Conditional Access App Control apps**. In the list of apps, on the row in which the app you're deploying appears, choose the three dots at the end of the row, and then choose **Edit app**.

1. Select **Enable the app to work on session controls** and then select **Save**. For example:

    :::image type="content" source="media/proxy-deployment-featured-idp/edit-app.png" alt-text="Screenshot of the Edit this app? dialog.":::
   
## Test the deployment<a name="test"></a>

1. First sign out of any existing sessions. Then, try to sign in to each app that was successfully deployed. Sign in using a user that matches the policy configured in Microsoft Entra ID, or for a SAML app configured with your identity provider.

1. In the Microsoft Defender Portal, under **Cloud Apps**, select **Activity log**, and make sure the login activities are captured for each app.

1. You can filter by selecting **Advanced**, and then filtering using **Source equals Access control**. For example:

    ![Screenshot of filtering with Microsoft Entra Conditional Access.](media/sso-logon.png)

1. We recommend that you sign into mobile and desktop apps from managed and unmanaged devices. This is to make sure that the activities are properly captured in the activity log.  

To verify that the activity is properly captured, select a single sign-on login activity so that it opens the activity drawer. Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).

> [!NOTE]
> After it is deployed, you can't remove an app from the Conditional Access App Control page. As long as you don't set a session or access policy on the app, the conditional access app control won't change any behavior for the app.

## Next steps

> [!div class="nextstepaction"]
> [« PREVIOUS: Introduction to conditional access app control](proxy-intro-aad.md)

> [!div class="nextstepaction"]
> [NEXT: Deploy conditional access app control for any app »](proxy-deployment-any-app.md)

> [!div class="nextstepaction"]
> [Troubleshooting access and session controls](troubleshooting-proxy.md)

[!INCLUDE [Open support ticket](includes/support.md)]
