---
# required metadata

title: Working with the Cloud App Security Proxy | Microsoft Docs
description: This topic provides information about how the Cloud App Security Proxy works.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/31/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 28317b70-1851-4610-b1d6-863bc5994bb6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Working with the Cloud App Security Proxy

In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact, you want to be able to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. You need to be able to enable users in your organization to make the most of the services and tools available to them in cloud apps, and to bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, ransomware attacks and mass data theft. 

## Introducing the Cloud App Security Proxy
Cloud App Security’s Proxy gives you the tools you need to perform real time monitoring and control access to your cloud environment as well as the activities performed within it.
With the Cloud App Security Proxy you can protect your organization:
- Avoid data leaks by blocking downloads before they happen
- Minimize your exposure to ransomware by managing and blocking access to your network from unmanaged devices that may not be password protected or have antivirus software installed
- Set rules that force data stored in and downloaded from the cloud to be protected with encryption
- Gain visibility into unprotected endpoints so you can monitor what's being done on unmanaged devices
- Control access from risky IP addresses and legacy identity providers

To enable these unique capabilities, use the two levels of control provided by the Proxy: access control and session control. Both types of control leverage user information, location information, and device information (used to identify which devices are managed and unmanaged), to make policy decisions for each app.

### Access control
<more information about what is access control including examples>
The Proxy’s access control enables you to create powerful access policies for your cloud apps and provides you with the following capabilities:

To use Access control in Cloud App Security, deploy the Proxy by making a few changes to your existing identity provider configuration, and set a policy to control your cloud aps. 

> [!NOTE]
> -  There is no need to change the identity provider’s existing policies.

#### Supported apps and identity providers

The Proxy’s access control is designed to support any app and any identity provider that supports either SAML or WS-Federation protocols. The Cloud App Security team is testing the leading identity providers and the leading apps with the access control capabilities. However, since there are many identity providers and many cloud apps, not every combination of identity providers and app is tested. We recommend testing the single sign-on process with your identity provider and app on a sandbox or testing environment before deploying it in a production environment.

### Session control

Session control is an additional layer of control provided by the Proxy. It allows even more granular, real-time control over your cloud applications. Instead of setting a blanket policy to allow or block access to a certain app, you can allow access adn then, while monitoring each user session in the app, limit the access in various ways. For example, you can decide that from certain devices, or for sessions coming from specific locations, you want to allow the user to access the application, but limit the download of sensitive files.

#### Supported apps and flows

Currently, Session control allows you to block file download and the export of reports in Salesforce.com. You can create policies based on user, location, and device, as well as based on the content you want to download.

In addition, this version supports limited sessions for users logging in from browsers. For example, if you want to limit access for sessions coming from native apps, you will need to define an access policy to block such access when the filter **User agent tag** equals **Native client**.

Salesforce is tested on all normal flows. However, since Salesforce has numerous 3rd party apps, there might be some 3rd party apps that were not tested and might not work with the session Control, and even cause some pages not to work. To verify that this is indeed a 3rd party app problem, remove all 3rd party apps and test the app with the session control. If everything works well, add the 3rd party apps one by one until you find the problematic app. 

## Device management

Cloud App Security enables you to identify and create Proxy policies based on device posture. In order to identify whether a device is managed or not, Cloud App Security leverages the Client Certificates mechanism, in which client certificates are deployed on the managed devices of your organization. After users perform logins to an app, they will be requested to provide the client certificate installed on their device. If a client certificate is provided, Cloud App security regards a device as managed. 
> [!NOTE]
>  The user might choose to decline sending the client certificates, and in this case, the device will be considered unmanaged.
<ok, so then you know if it's managed or not - what do you do with it?>

### Supported browsers and native apps

The Cloud App Security Proxy enables you to.... based on client certificates...

Client certificates is a well-known mechanism that browser developers and native application developers can decide to implement or not. Most browsers on most platforms do support it, but the story in native apps is more complicated.

The support for client certificates in native apps, which include both desktop apps and mobile apps, might sometimes vary depending on the platform and even on the state of the device. For example, in Salesforce1, the Salesforce mobile app, client certificates work only if there is an MDM deployed on the device and Salesforce1 is configured to send client certificates.

Client certificates were successfully tested on Internet Explorer, Edge, Chrome, Safari, and Firefox on the latest versions of Windows, OSX, Android, and iOS (each with the relevant browsers).

> [!NOTE]
> In iOS, only the Safari browser works with client certificates.

Even in cases in which browsers or native apps do support client certificates, there may be some cases where the users will have problems providing the certificate, for example, if a user declines to send a client certificate once, the browser or native app might remember the choice and will not prompt the user for a certificate again. To overcome such problems, we recommend closing all open instances of the browser and then open new ones, or clear all cookies and try again.

On the other hand, there are some browsers and native apps that support the option to suppress the pop up that requests client certificates, and instead sends them automatically.

In general, we recommend testing client certificate requests from users without enforcing policies but in a monitor mode only. You can do it by creating a **log only** policy to identify managed devices.

## Architecture

The Proxy is integrated with both your identity provider and the app, and both need to be configured to redirect login requests to the Proxy.

In addition, in order identify managed devices, the Proxy can request client certificates from managed devices. Once a client certificate is received by the Proxy, the device is considered managed and policies on managed and unmanaged devices take effect.

For more information about the deployment process, see the Deployment section.

![Cloud App Security Proxy architecture](./media/proxy-architecture.png)

## User login flow

The diagram above describes a login that starts from the identity provider, also known as *Identity provider initiated login*. If the user starts from the app, known as *Service provider initiated login*, then she is directed to the Cloud App Security Proxy which then directs the user to the identity provider, and the rest of the login process is similar to the *Identity provider initiated login* flow.

This is the *Identity provider initiated login* flow:
-   User sends a request to the identity provider and provides credentials

-   If access is allowed, the identity provider redirects the user to the Cloud App Security Proxy

-   If the user has a client certificate installed, and there is a relevant policy that checks for managed or unmanaged devices, then the user is
    prompted to provide client certificates. Either way, an access policy is evaluated

-   At this point, there are 3 possible options:

    -   The user is allowed to access the app

    -   The user is blocked from accessing the app

    -   The user is allowed to access the app, but in monitored mode

        -   In this case, the user is redirected again to the Cloud App Security Proxy, which monitors the entire session between the user and the app

        -   While monitoring, the Proxy evaluates the session policies and can perform blocking actions accordingly

## How access control works

As part of the deployment of the Proxy, you need to change configurations in both the identity provider and the app that you want to control. This includes URL changes so that both the identity provider and the app will redirect login requests to the Proxy. In addition, and if needed, certificates are replaced as well.

Once these steps are completed, all login events go through the Proxy and the Proxy can decide if they are allowed to access the app, denied access, or allowed to access in monitored mode. Note that at this stage, the Proxy can request client certificates from the device, and use the state of the device to make policy decisions.

## How session control works

The Proxy’s session control is built on top of access control. Once you control access to an app, you can decide, based on access policies, to monitor the session by redirecting its sessions to the Proxy’s session control. From then on, user requests and responses go through the Proxy rather than directly to the app.

To keep the user within the session, the Proxy replaces all the relevant URLs, Java scripts, and cookies within the app to pages duplicated in the Proxy. For example: if the app returns a page with links that end with *myapp.com*, the Proxy will replace them with pages that end with something like *myapp.com.cas.ms*.

Once a session is directed through the Proxy, the Proxy can inspect the traffic, display the events it identifies in the Cloud App Proxy portal, and enforce policies on the session.

## How identifying managed devices works

To identify managed devices, the Proxy uses the mechanism of Client certificates. The mechanism works as follows:

-   If the user has a client certificate installed on her device, and there is a relevant policy that checks for managed or unmanaged devices.

    -   When the user arrives at the Proxy page during the login phase, the Proxy requests a client certificate from the user’s device.

    -   The user device is prompted to provide the client certificate, and if she approves, the client certificate is sent to the Proxy.

    -   The Proxy then authenticates the client certificate against the root certificate provided by the admin.

    -   If the client certificate provided by the device is successfully authenticated with the root certificate, then the device is considered managed.

-   If any of the previous phases is not completed, the device is considered unmanaged.



## See Also  
[Proxy deployment](proxy-deployment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  