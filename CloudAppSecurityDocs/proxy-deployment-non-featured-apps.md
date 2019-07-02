---
# required metadata

title: Deploy Cloud App Security Conditional Access App Control for any apps
description: This article provides information about how to deploy the Microsoft Cloud App Security Conditional Access App Control reverse proxy features for any apps.
keywords:
author: ShlomoSagir-MS
ms.author: ShlomoSagir-MS
manager: ShlomoSagir-MS
ms.date: 6/24/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 2490c5e5-e723-4fc2-a5e0-d0a3a7d01fc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Deploy Conditional Access App Control for any apps

*Applies to: Microsoft Cloud App Security*

>[!div class="step-by-step"]
[« Previous: Introduction to Conditional Access App Control](proxy-intro-aad.md)<br>
[Next: How to create a session policy »](session-policy-aad.md)

Session controls in Microsoft Cloud App Security can be configured to work with any web apps. This article describes how to deploy custom line-of-business apps, non-featured SaaS apps, and on-premise apps hosted via the Azure AD Application Proxy with Session controls.

For a list of apps that are featured by Cloud App Security to work out-of-the-box, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](proxy-intro-aad.md).

## Prerequisites

- Your organization must have the following licenses to use Conditional Access App Control:

  - Azure Active Directory Premium edition
  - Cloud Apps Security

- Apps must be configured with single sign-on in Azure AD
- Apps must use SAML or Open ID Connect 2.0 protocols

## To deploy a non-featured app

Follow these steps to configure non-featured app to be controlled by Cloud App Security Conditional Access App Control.

**Step 1: [Configure the conditional access policy feature of Azure Active Directory to route relevant apps to Cloud App Security](#conf-azure-ad).**

**Step 2: [Configure the users that will deploy the app](#conf-users).**

**Step 3: [Configure the app that you are deploying](#conf-apps)**

**Step 4: [Verify that the app is working correctly](#verify-app)**

**Step 5: [Enable the app for use in your organization](#enable-app)**

**Step 6: [Update the Azure AD policy](#update-azure-ad)**

> [!NOTE]
> To deploy Conditional Access App Control for Azure AD apps, you need a valid [license for Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) as well as a Cloud App Security license.

## Step 1: Configure the conditional access policy feature of Azure Active Directory to route relevant apps to Cloud App Security<a name="conf-azure-ad"></a>  

1. In Azure Active Directory, under **Security**, click **Conditional Access**.

1. On the **Conditional Access** page, in the toolbar on the top, click **New policy**.

1. On the **New** page, in the **Name** textbox, type **TEST**.

1. On the **Users and groups** page, assign the relevant test users that will be onboarding the apps.

1. On the **Cloud apps** page, assign the apps you want to control with Conditional Access App Control.

1. Under **Session**, select **Use Conditional Access App Control** and then select **Monitor only**.

   ![Azure AD conditional access](./media/azure-ad-caac-policy.png)

1. Click **Enable** and **Save**.

## Step 2: Configure the users that will deploy the app<a name="conf-users"></a>

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and select **Settings**.

1. Under **Conditional Access App Control**, select **App onboarding/maintenance**.

1. Enter the user principal name or email for the users that will be onboarding the app, and then click **Save**.

    ![Screenshot of settings for App onboarding and maintenance.](media/app-onboarding-settings.png)

## Step 3: Configure the app that you are deploying<a name="conf-apps"></a>

1. Go to the app that you are deploying. If your app domain is recognized, you will be prompted to continue the app configuration process. If your app domain is not recognized, you will be prompted to configure your app's domain. Click **Configure app** and follow the instructions in step 4.2.4.

    > [!NOTE]
    > For recognized app domains, make sure the app is configured with all domains required for the app to function correctly.

1. Repeat the following steps to install the **Current CA** and **Next CA** self-signed root certificates.
    1. Select the certificate.
    1. Click **Open**, and when prompted click **Open** again.
    1. Click **Install certificate**.
    1. Choose either **Current User** or **Local Machine**.
    1. Select **Place all certificates in the following store** and then click **Browse**.
    1. Select **Trusted Root Certificate Authorities** and then click **OK**.
    1. Click **Finish**.

    > [!NOTE]
    > For the certificates to be recognized, once you have installed the certificate, you must restart the browser and go to the same page. You'll see a check-mark by the certificates links confirmation they are installed.

1. Click **Continue**.

## Step 4: Verify that the app is working correctly<a name="verify-app"></a>

1. Verify that the sign-in flow correctly works.
    > [!NOTE]
    > Some apps issue a nonce hash during authentication that may break the sign-in process. If this happens, see the Troubleshooting Guide to resolve the issue.
1. Once you are in the app, perform the following checks:
    1. Visit all pages within the app that are part of a users’ work process and verify that the pages render correctly.
1. Verify that the behavior and functionality of the app is not adversely affected by performing common actions such as downloading and uploading files.

## Step 5: Enable the app for use in your organization<a name="enable-app"></a>

Once you are ready to enable the app for use in your organization's production environment, do the following steps.

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and select **Conditional Access App Control**.
1. In the list of apps, on the row in which the app you are deploying appears, choose the three dots at the end of the row, and then choose **Edit app**.
1. Select **Use with Conditional Access App Control** and then click **Save**.

## Step 6: Update the Azure AD policy<a name="update-azure-ad"></a>

1. In Azure Active Directory, under **Security**, click **Conditional Access**.
1. Update the policy you created in [step 1](#conf-azure-ad) to include the relevant users, groups, and controls you require.
1. Under **Session** > **Use Conditional Access App Control**, if you selected **Use Custom Policy**, go to Cloud App Security and create a corresponding session policy. For more information, see [Session policies](session-policy-aad.md).

>[!div class="step-by-step"]
[« Previous: Deploy Conditional Access App Control for Azure AD apps](proxy-deployment-aad.md)<br>
[Next: How to create a session policy »](session-policy-aad.md)

## Next steps 
[Working with the Cloud App Security Conditional Access App Control](proxy-intro-aad.md)

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)