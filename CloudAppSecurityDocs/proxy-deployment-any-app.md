---
title: Deploy Conditional Access App Control custom apps with Azure Active Directory
description: This article provides information about how to deploy the Microsoft Cloud App Security Conditional Access App Control reverse proxy features for custom apps using Azure Active Directory
ms.date: 06/14/2021
ms.topic: how-to
---
# Onboard and deploy Conditional Access App Control for custom apps using Azure Active Directory

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Session controls in Microsoft Cloud App Security can be configured to work with any web apps. This article describes how to onboard and deploy custom line-of-business apps, non-featured SaaS apps, and on-premise apps hosted via the Azure Active Directory (Azure AD) Application Proxy with session controls. It provides steps to create an Azure AD Conditional Access policy that routes app sessions to Cloud App Security. For other IdP solutions, see [Onboard and deploy Conditional Access App Control for custom apps with third-party IdP](proxy-deployment-any-app-idp.md).

For a list of apps that are featured by Cloud App Security to work out-of-the-box, see [Protect apps with Cloud App Security Conditional Access App Control](proxy-intro-aad.md#featured-apps).

## Prerequisites

### Add admins to the app onboarding/maintenance list

1. In the menu bar of Cloud App Security, select the settings cog ![settings icon 4](media/settings-icon.png "settings icon 4") and select **Settings**.

1. Under **Conditional Access App Control**, select **App onboarding/maintenance**.

1. Enter the user principal name or email for the users that will be onboarding the app, and then select **Save**.

    ![Screenshot of settings for App onboarding and maintenance.](media/app-onboarding-settings.png)

### Check for necessary licenses

- Your organization must have the following licenses to use Conditional Access App Control:

  - [Azure Active Directory (Azure AD) Premium P1](/azure/active-directory/license-users-groups) or higher
  - Microsoft Cloud App Security

- Apps must be configured with single sign-on
- Apps must use one of the following authentication protocols:

    |IdP|Protocols|
    |---|---|
    |Azure AD|SAML 2.0 or OpenID Connect|
  
## To deploy any app

Follow these steps to configure any app to be controlled by Cloud App Security Conditional Access App Control.

1. **[Configure your Azure AD to work with Cloud App Security](#step-1-configure-azure-ad-to-work-with-cloud-app-security)**

1. **[Configure the app that you are deploying](#conf-app)**

1. **[Verify that the app is working correctly](#verify-app)**

1. **[Enable the app for use in your organization](#enable-app)**

1. **[Update the Azure AD policy](#update-azure-ad)**

> [!NOTE]
> To deploy Conditional Access App Control for Azure AD apps, you need a valid [license for Azure Active Directory Premium P1 or higher](/azure/active-directory/license-users-groups) as well as a Cloud App Security license.

## Step 1: Configure Azure AD to work with Cloud App Security

>[!NOTE]
>When configuring an application with SSO in Azure AD, or other identity providers, one field that may be listed as optional is the sign-on URL setting. Note that this field may be required for Conditional Access App Control to work.

1. In Azure AD, browse to **Security** > **Conditional Access**.

1. On the **Conditional Access** pane, in the toolbar at the top, select **New policy**.

1. On the **New** pane, in the **Name** textbox, enter the policy name.

1. Under **Assignments**, select **Users and groups**, assign the users that will be onboarding (initial sign-on and verification) the app, and then select **Done**.

1. Under **Assignments**, select **Cloud apps**, assign the apps you want to control with Conditional Access App Control, and then select **Done**.

1. Under **Access controls**, select **Session**, select **Use Conditional Access App Control**, and choose a built-in policy (**Monitor only** or **Block downloads**) or **Use custom policy** to set an advanced policy in Cloud App Security, and then click **Select**.

    ![Azure AD conditional access.](media/azure-ad-caac-policy.png)

1. Optionally, add conditions and grant controls as required.

1. Set **Enable policy** to **On** and then select **Create**.

[!INCLUDE [Configuration steps](includes/proxy-deploy-configure.md)]

## Update the Azure AD policy (Azure AD only)<a name="update-azure-ad"></a>

1. In Azure AD, under **Security**, click **Conditional Access**.
1. Update the policy you created earlier to include the relevant users, groups, and controls you require.
1. Under **Session** > **Use Conditional Access App Control**, if you selected **Use Custom Policy**, go to Cloud App Security and create a corresponding session policy. For more information, see [Session policies](session-policy-aad.md).

## Next steps

> [!div class="nextstepaction"]
> [PREVIOUS: Deploy Conditional Access App Control for featured apps](proxy-deployment-aad.md)

> [!div class="nextstepaction"]
> [NEXT: How to create a session policy](session-policy-aad.md)

## See also

> [!div class="nextstepaction"]
> [Introduction to Conditional Access App Control](proxy-intro-aad.md)

> [!div class="nextstepaction"]
> [Troubleshooting access and session controls](troubleshooting-proxy.md)

[!INCLUDE [Open support ticket](includes/support.md)]

