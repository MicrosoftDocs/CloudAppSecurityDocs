---
# required metadata

title: Deploy Cloud App Security Conditional Access App Control for non-featured apps
description: This article provides information about how to deploy the Microsoft Cloud App Security Conditional Access App Control reverse proxy features for non-featured apps.
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
# Deploy Conditional Access App Control for non-featured apps

*Applies to: Microsoft Cloud App Security*

>[!div class="step-by-step"]
[« Previous: Introduction to Conditional Access App Control](proxy-intro-aad.md)<br>
[Next: How to create a session policy »](session-policy-aad.md)

Session controls in Microsoft Cloud App Security can be configured to work with any web apps. These are apps that are featured by Cloud App Security to work out-of-the-box.

This article describes how to onboard custom line-of-business apps, non-featured SaaS apps, and on-premise apps hosted via the Azure AD Application Proxy with Session controls.

## Prerequisites

- Your organization must have the following licenses to use Conditional Access App Control:

    - Azure Active Directory Premium edition
    - Cloud Apps Security

- Apps must be configured with single sign-on in Azure AD
- Apps must use SAML or Open ID Connect 2.0 protocols

## To deploy non-featured apps

Follow these steps to configure non-featured apps to be controlled by Cloud App Security Conditional Access App Control.

**Step 1: [Configure the conditional access policy feature of Azure Active Directory to route relevant apps to Cloud App Security](#conf-azure-ad).**

**Step 2: [Configure the users that will deploy the apps](#conf-users).**

**Step 3: If you did not select a built-in Cloud App Security policy in Azure AD or if you want to apply the policy to a non-featured app, [go to the Cloud App Security portal](#portal)**

[**Step 4: Test the deployment**](#test)

> [!NOTE]
> To deploy Conditional Access App Control for Azure AD apps, you need a valid [license for Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) as well as a Cloud App Security license.

## Step 1: Configure the conditional access policy feature of Azure Active Directory to route relevant apps to Cloud App Security<a name="conf-azure-ad"></a>  

1. In Azure Active Directory, under **Security**, click **Conditional Access**.

1. On the **Conditional Access** page, in the toolbar on the top, click **New policy**.

1. On the **New** page, in the **Name** textbox, type **TEST**.

1. On the **Users and groups** page, assign the relevant test users that will be onboarding the apps.

1. On the **Cloud apps** page, assign the apps you want to control with Conditional Access App Control.

1. Under **Session**, select **Use Conditional Access App Control** and then select **Monitor only**.

1. Add any applicable **Condition assignments** or **Grant controls** (optional).

   ![Azure AD conditional access](./media/azure-ad-caac-policy.png)

1. Click **Enable** and **Save**.
 
## Step 2: Configure the users that will deploy the apps<a name="conf-users"></a>

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and select **Settings**.

1. Under **Conditional Access App Control**, select **App onboarding/maintenance**.

## Step 3: Configure advanced controls and non-featured apps in the Cloud App Security portal <a name="portal"></a>

The instructions above helped you create a built-in Cloud App Security policy for featured apps directly in Azure AD.

To configure an advanced policy, create an [access policy](access-policy-aad.md) or a [session policy](session-policy-aad.md) in Cloud App Security.

To apply the policy to a non-featured application, follow the instructions to self-onboard a non-featured application for use with Conditional Access App Control.

To request support for a non-featured application:

1. In the Cloud App Security portal, go to the settings cog and choose **Conditional Access App Control**. You should see a message letting you know that new Azure AD apps were discovered by Conditional Access App Control. 

    ![Conditional access app control menu](./media/caac-menu.png)

2. Click **View new apps**.

    ![Conditional access app control view new apps](./media/caac-view-apps.png)

3. In the screen that opens, you can see all the apps that you logged into in the previous step. For each app, click on the + sign, and then click **Add**.

   > [!NOTE]
   > If an app does not appear in the Cloud App Security app catalog, it will appear in the dialog under unidentified apps along with the login URL. When you click the + sign for these apps, you can onboard the application as a custom app.

   ![Conditional access app control discovered Azure AD apps](./media/caac-discovered-aad-apps.png)

4. In the Conditional Access App Control apps table, look at the **Available controls** column and verify that both **Azure AD conditional access** and **Session control** appear. 
   
   > [!NOTE]
   > If Session control doesn't appear for an app, it's not yet available for that specific app. You'll see the **Request session control** link instead. 
  
     ![Conditional access app control request](./media/caac-request.png)
   

5. Click **Request session control** to request that the app be onboarded to session control. The onboarding process will be performed with you by the Microsoft Cloud App Security team.
 

6.	Identify devices using client certificates (optional).
    1.	Go to the settings cog and choose **Device identification**.
    2.	Upload one or more root or intermediate certificates.
   
    3. After the certificate is uploaded, you can create access policies and session policies based on **Device tag** and **Valid client certificate**.

       ![Conditional access app control device ID](./media/caac-device-id.png)

> [!NOTE]
> A certificate is only requested from a user if the session matches a policy that uses the valid client certificate filter.


## Step 4: Test the deployment <a name="test"></a>

1. First sign out of any existing sessions. Then, try to sign in to each app that was successfully deployed. Sign in using a user that matches the policy configured in Azure AD. 

2. In the Cloud App Security portal, under **Investigate**, select **Activity log**, and make sure the login activities are captured for each app.

3. You can filter by clicking on **Advanced**, and then filtering using **Source equals Access control**.

    ![Filter using Azure AD conditional access](./media/sso-logon.png)

4. It's recommended that you sign into mobile and desktop apps from managed and unmanaged devices. This is to make sure that the activities are properly captured in the activity log.<br></br>
   To verify that the activity is properly captured, click on a single sign-on log on activity so that it opens the activity drawer. Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).
 
> [!NOTE]
> After it is deployed, you can't remove an app from the Conditional Access App Control page. As long as you don't set a session or access policy on the app, the Conditional Access App Control won't change any behavior for the app. 

>[!div class="step-by-step"]
[« Previous: Introduction to Conditional Access App Control](proxy-intro-aad.md)<br>
[Next: How to create a session policy »](session-policy-aad.md)


## Next steps 
[Working with the Cloud App Security Conditional Access App Control](proxy-intro-aad.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
