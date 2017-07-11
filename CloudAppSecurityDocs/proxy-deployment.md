---
# required metadata

title: Deploying the Cloud App Security Proxy | Microsoft Docs
description: This topic provides information about how to deploy the Cloud App Security Proxy.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/10/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 75094bde-e135-47fb-b5c6-7e1168919771

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Deploying the Cloud App Security Proxy

> [!NOTE]
> It is strongly recommended to try the installation in a sandbox or testing
environment before installing it in a production environment.

The steps described below must be taken to deploy the Cloud App Security Proxy
and enable both access control and session control.

## Prerequisites

-   A working environment in which your cloud app is configured with an identity
    provider. The installation process involves configuration changes in both
    the app and the identity provider.

-   Gather the following information from the app and the identity provider:

    -   The identity provider SAML metadata file

    -   The app SAML metadata file

        -   If the app does not provide a metadata file, you will need to
            provide the app Single sign-on login URL and the app SAML
            certificate if such a certificate exists. They should be available
            in the Single Sign on settings page of the app.

    -   If addition, you might need to provide the binding method used in the
        SAML login process, which is either POST or GET (a.k.a. HTTP-Redirect).
        This should also appear in the Single sign-on settings page of the app.

> [!NOTE]
> If you use single logout, you will need to gather the same parameters for
the log out process.

After gathering all the information described above, send the information to the
Cloud App Security team. In response, you will receive the following information
that you will use for the installation:

1.  A new URL for the identity provider

2.  A new URL for the app

3.  An app ID number

The Cloud App Security team will also enable the Proxy capabilities on your
tenant.

## Deploy the Proxy

If you are installing the Proxy in a production environment, we recommend
finding a time when most of the users are not using the app, usually late at
night or over the weekend, and communicate to your users that there might be a
short app downtime.

Before starting to make configuration changes, check that your current
configuration works. After this is verified, perform the following steps.

### Step 1: In the Cloud App Security portal

1.  In the Cloud App Security portal, under the settings cog, choose **Proxy.**

2.  In the **Proxy apps** table, locate the relevant app and click on Edit
    settings…

3.  Upload your app’s identity provider SAML certificate and download a new
    Cloud App Security SAML certificate. Save it for later, you will need to add
    it to your app.

4.  If relevant, upload the app’s SAML certificate in the same page, and
    download another new Cloud App Security SAML certificate. This new
    certificate might be later added to the identity provider.

### Step 2: In the identity provider settings

1.  Create a new custom app.

2.  Copy the exact configuration for your app in the identity provider, and fill
    in the relevant fields with the same values, with the following exceptions:

    1.  Use the *new URL for the identity provider* provided by Cloud App
        Security (above) as the login URL (this is sometimes called Assertion
        Consumer Service or ACS URL).

    2.  Add a new SAML attribute called **McasAppId** and set it to be the *app
        ID number* provided by Cloud App Security (above). Make sure to use the
        same casing.

    3.  If there is an option to upload an app certificate, and the app has a
        SAML certificate, upload the new certificate downloaded from the Cloud
        App Security portal.

### Step 3: In the app’s single sign-on settings

1.  Change the login URL (this is sometimes called Assertion Consumer Service or
    ACS URL) to the *new URL for the app* provided by Cloud App Security.

2.  Upload the new SAML certificate that was download from the Cloud App
    Security portal.

### Step 4: Test the configuration

1.  Try to log in to the app.

2.  In the Cloud App Security portal, under **Investigate**, select **Activity
    log** and make sure there are **single sign-on log on** events captured by
    the Access Proxy.



## See Also  
[Working with the Cloud App Security Proxy](proxy-intro.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  