---
title: Deploy Conditional Access App Control custom apps with Azure Active Directory
description: This article provides information about how to deploy the Microsoft Defender for Cloud Apps Conditional Access App Control reverse proxy features for custom apps using Azure Active Directory
ms.date: 03/05/2023
ms.topic: how-to
---

# Deploy Conditional Access App Control for custom apps using Azure Active Directory

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Session controls in Microsoft Defender for Cloud Apps can be configured to work with any web apps. This article describes how to onboard and deploy custom line-of-business apps, non-featured SaaS apps, and on-premises apps hosted via the Azure Active Directory (Azure AD) Application Proxy with session controls. It provides steps to create an Azure AD Conditional Access policy that routes app sessions to Defender for Cloud Apps. For other IdP solutions, see [Deploy Conditional Access App Control for custom apps with non-Microsoft IdP](proxy-deployment-any-app-idp.md).

For a list of apps that are featured by Defender for Cloud Apps to work out-of-the-box, see [Protect apps with Defender for Cloud Apps Conditional Access App Control](proxy-intro-aad.md#pre-onboarded-apps).

## Prerequisites

Before starting the onboarding process, you must do the following:

- [Add admins to the app onboarding/maintenance list](#add-admins-to-the-app-onboardingmaintenance-list)
- [Check for necessary licenses](#check-for-necessary-licenses)

### Add admins to the app onboarding/maintenance list

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **Conditional Access App Control**, select **App onboarding/maintenance**.
1. Enter the user principal name or email for the users that will be onboarding the app, and then select **Save**.

    ![Screenshot of settings for App onboarding and maintenance.](media/app-onboarding-settings.png)

### Check for necessary licenses

- Your organization must have the following licenses to use Conditional Access App Control:

  - [Azure Active Directory (Azure AD) Premium P1](/azure/active-directory/license-users-groups) or higher
  - Microsoft Defender for Cloud Apps
- Apps must be configured with single sign-on
- Apps must use one of the following authentication protocols:

   |IdP|Protocols|
   |---|---|
   |Azure AD|SAML 2.0 or OpenID Connect|

## To deploy any app

To onboard an application to be controlled by Defender for Cloud Apps Conditional Access Control, you will need to:

- [Configure Azure AD to work with Defender for Cloud Apps](#configure-azure-ad-to-work-with-defender-for-cloud-apps)
- [Manually add an unidentified app](#how-to-manually-add-an-unidentified-app)

Follow the steps below to configure any app to be controlled by Defender for Cloud Apps Conditional Access App Control.
> [!NOTE]
> To deploy Conditional Access App Control for Azure AD apps, you need a valid [license for Azure Active Directory Premium P1 or higher](/azure/active-directory/fundamentals/license-users-groups) as well as a Defender for Cloud Apps license.

## Configure Azure AD to work with Defender for Cloud Apps

> [!NOTE]
> When configuring an application with SSO in Azure AD, or other identity providers, one field that may be listed as optional is the sign-on URL setting. Note that this field may be required for Conditional Access App Control to work.

1. In Azure AD, browse to **Security** > **Conditional Access**.
1. On the **Conditional Access** pane, in the toolbar at the top, select **New policy** -> **Create new policy**.
1. On the **New** pane, in the **Name** textbox, enter the policy name.
1. Under **Assignments**, select **Users or workload identities**, assign the users that will be onboarding (initial sign-on and verification) the app, and then select **Done**.
1. Under **Assignments**, select **Cloud apps or actions**, assign the apps you want to control with Conditional Access App Control, and then select **Done**.
1. Under **Access controls**, select **Session**, select **Use Conditional Access App Control**, and choose a built-in policy (**Monitor only** or **Block downloads**) or **Use custom policy** to set an advanced policy in Defender for Cloud Apps, and then click **Select**.

    ![Azure AD conditional access.](media/azure-ad-caac-policy.png)

1. Optionally, add conditions and grant controls as required.
1. Set **Enable policy** to **On** and then select **Create**.

Applications in the app catalog are automatically populated into the table under Connected Apps. Sign out of the application if you have an active session and sign in again to allow for the app to be discovered. Check that the app you want to deploy is recognized by navigating there.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **Connected apps**, select **Conditional Access App Control apps** to access a table of applications that can be configured with access and session policies.

    ![Conditional access app control apps.](media/conditional-access-app-control-apps.png)

1. Select the **App: Select apps…** dropdown menu to filter and search for the app you want to deploy.

    ![Select App: Select apps to search for the app.](media/select-apps.png)

1. If you don't see the app there, you'll have to manually add it.

### How to manually add an unidentified app

1. In the banner, select **View new apps**.

    ![Conditional access app control view new apps.](media/caac-view-apps.png)
1. In the list of new apps, for each app that you're onboarding, select the **+** sign, and then select **Add**.

   > [!NOTE]
   > If an app does not appear in the Defender for Cloud Apps app catalog, it will appear in the dialog under unidentified apps along with the login URL. When you click the + sign for these apps, you can onboard the application as a custom app.

    ![Conditional access app control discovered Azure AD apps.](media/caac-discovered-aad-apps.png)

Associating the correct domains to an app allows Defender for Cloud Apps to enforce policies and audit activities.

For example, if you've configured a policy that blocks downloading files for an associated domain, file downloads by the app from that domain will be blocked. However, file downloads by the app from domains not associated with the app won't be blocked and the action won't be audited in the activity log.

> [!NOTE]
> Defender for Cloud Apps still adds a suffix to domains not associated with the app to ensure a seamless user experience.

1. From within the app, on the Defender for Cloud Apps admin toolbar, select **Discovered domains**.

   :::image type="content" source="media/discovered-domains.png" alt-text="Select Discovered domains.":::

   > [!NOTE]
   > The admin toolbar is only visible to users with permissions to onboard or maintenance apps.

1. In the Discovered domains panel, make a note of domain names or export the list as a .csv file.

   > [!NOTE]
   > The panel displays a list of discovered domains that are not associated in the app. The domain names are fully qualified.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **Connected apps**, select **Conditional Access App Control apps**.
1. In the list of apps, on the row in which the app you're deploying appears, choose the three dots at the end of the row, and then select **Edit app**.

   :::image type="content" source="media/edit-app-details.png" alt-text="Edit app details.":::

   > [!TIP]
   > To view the list of domains configured in the app, select **View app domains**.

   - **User-defined domains**: Domains associated with the application. Navigate to the application and you can use the [Admin tool bar](troubleshooting-proxy.md#diagnose-and-troubleshoot-with-the-admin-view-toolbar) to identify the domains associated with the application and determine if any of them are missing. Note that a missing domain can cause the protected application to not render correctly.
   - **Treat access token as login requests**: Some applications use access tokens and code requests as app logins. This gives the ability to treat access token and code requests as logins when onboarding apps to access and session controls for the application to render correctly. When onboarding the application, always make sure this is ticked.
   - **Use app with session control**: To allow this app to be used or not used with session controls. When onboarding the application always make sure this is ticked.
   - **Perform a second logon**: If the application uses a nonce, a second logon is needed to account for nonce handling. The nonce or second logon is used by applications to make sure that the login token that the IdP creates for the user can only be used once, and not stolen and reused by someone else. The nonce is checked by the Service Provider to match what it was expecting, and not something it has recently used already, which could indicate a replay attack. When this is chosen, we ensure that a second login is being triggered from a suffixed session, which ensures a successful login. For better performance, this should be enabled.

      :::image type="content" source="media/second-login.png" alt-text="Perform a second login.":::

1. In **User-defined domains**, enter all the domains you want to associate with this app, and then select **Save**.

   > [!NOTE]
   > You can use the * wildcard character as a placeholder for any character. When adding domains, decide whether you want to add specific domains (`sub1.contoso.com`,`sub2.contoso.com`) or multiple domains (`*.contoso.com`). This is only supported for specific domains (`*.contoso.com`) and not for top-level domains (`*.com`).
   
1. Repeat the following steps to install the **Current CA** and **Next CA** self-signed root certificates.

   1. Select the certificate.
   1. Select **Open**, and when prompted select **Open** again.
   1. Select **Install certificate**.
   1. Choose either **Current User** or **Local Machine**.
   1. Select **Place all certificates in the following store** and then select **Browse**.
   1. Select **Trusted Root Certificate Authorities** and then select **OK**.
   1. Select **Finish**.

   > [!NOTE]
   > For the certificates to be recognized, once you have installed the certificate, you must restart the browser and go to the same page.
1. Select **Continue**.
1. Check that the application is available in the table.

   ![Onboard with session control.](media/proxy-deployment-aad/onboard-with-session-control.png)

To verify that the application is being proxied, first perform either a hard sign-out of browsers associated with the application or open a new browser with incognito mode.

Open the application and perform the following checks:

- Check that the URL contains the `.mcas` suffix
- Visit all pages within the app that are part of a user's work process and verify that the pages render correctly.
- Verify that the behavior and functionality of the app isn't adversely affected by performing common actions such as downloading and uploading files.
- Review the list of domains associated with the app.

If you encounter errors or issues, use the admin toolbar to gather resources such as `.har` files and recorded sessions for filing a support ticket.

Once you're ready to enable the app for use in your organization's production environment, do the following steps.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **Connected apps**, select **Conditional Access App Control apps**.
1. In the list of apps, on the row in which the app you're deploying appears, choose the three dots at the end of the row, and then choose **Edit app**.
1. Select **Use the app with session controls** and then select **Save**.
1. In Azure AD, under **Security**, select **Conditional Access**.
1. Update the policy you created earlier to include the relevant users, groups, and controls you require.
1. Under **Session** > **Use Conditional Access App Control**, if you selected **Use Custom Policy**, go to Defender for Cloud Apps and create a corresponding session policy. For more information, see [Session policies](session-policy-aad.md).

## Next steps

> [!div class="nextstepaction"]
> [PREVIOUS: Deploy Conditional Access App Control for catalog apps](proxy-deployment-aad.md)

> [!div class="nextstepaction"]
> [NEXT: How to create a session policy](session-policy-aad.md)

## See also

> [!div class="nextstepaction"]
> [Introduction to Conditional Access App Control](proxy-intro-aad.md)

> [!div class="nextstepaction"]
> [Troubleshooting access and session controls](troubleshooting-proxy.md)

[!INCLUDE [Open support ticket](includes/support.md)]
