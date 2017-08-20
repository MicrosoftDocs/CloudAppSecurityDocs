---
# required metadata

title: Working with the Cloud App Security Proxy | Microsoft Docs
description: This topic provides information about how the Cloud App Security Proxy works.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/20/2017
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

In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact, you want to be able to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. 

You need to be able to enable users in your organization to make the most of the services and tools available to them in cloud apps, and to bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft in real time. 

## Introducing the Cloud App Security Proxy
Cloud App Security’s Proxy gives you the tools you need to perform real time visibility and control over access to and activities performed within in your cloud environment.
With the Cloud App Security Proxy you can protect your organization:
- Protect your data against leaks by blocking downloads or encrypting cloud data in real time
- Control access to your network from unmanaged devices and risky locations
- Gain visibility into unprotected endpoints so you can monitor who's accessing the cloud from where and what they're doing within cloud apps

To enable these unique capabilities, use the two levels of control provided by the Proxy: access control and session control. Both types of control leverage user information, location information, and device information, to make policy decisions for each app.

## Access control
Access control provides conditional access to cloud apps that are configured through non-Azure AD identity providers. This feature gives you the ability to monitor and block access to cloud apps based on app, device, user and location. In this way you can control, in real time, access to your cloud apps.

Access control lets you to create powerful policies, such as:
- block access to all cloud apps from unmanaged devices
- limit access to cloud apps to specific users and user groups
- monitor access to specific cloud apps from specific locations


### How access control works

The app in the identity provider reroutes login requests to the Proxy. The Proxy then can decide, based on the app, user, location, and device whether to grant access. 

### Supported apps and identity providers

Access control supports any app and any identity provider that supports either SAML or WS-Federation protocols. The Cloud App Security team tested the leading identity providers and the leading apps with the access control capabilities. However, since there are many identity providers and many cloud apps, we recommend testing the single sign-on process with your identity provider and app in a sandbox or testing environment before deploying it in a production environment.

## Session control

Session control provides an additional layer of control by providing insight into activities in user sessions, for both Azure AD apps and apps configured by other identity providers. Session control enables session-level monitoring, affording you granular visibility into cloud apps even from unmanaged devices and devices that are off-premises. Instead of allowing and blocking access completely, with session control you can limit specific session activities. 

For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the application, but limit the download of sensitive files. 

### How session control works

The Proxy’s session control is built on top of access control. After you control access to an app, you can set session policies that will redirect user sessions to the Proxy’s session control. From then on, user requests and responses go through the Proxy rather than directly to the app.

To keep the user within the session, the Proxy replaces all the relevant URLs, Java scripts, and cookies within the app to pages duplicated in the Proxy. For example: if the app returns a page with links whose domain ends with *myapp.com*, the Proxy will replace the links with domains such as: *myapp.com.cas.ms*.

After a session is directed through the Proxy, the Proxy can inspect the traffic, display the events it identifies in the Cloud App Proxy portal, and enforce policies on the session.

## Device identification

Cloud App Security enables you to identify and create Access and Session policies based on device posture. In order to identify whether a device is managed or not, Cloud App Security leverages:
 - Intune compliant devices* 
 - Azure AD domain joined devices* 
 - Client certificates deployment

* Only available for Azure AD apps where conditional access is available

## Architecture

The Cloud App Security Proxy is automatically integrated with Azure AD Premium P2. You can also leverage Azure AD domain joined and Intune compliant devices for device identification in policy creation and investigation. 

To set other identity providers and apps to work with the Proxy, both need to be configured to redirect login requests to the Proxy.

In addition, in order identify managed devices, the Proxy can request client certificates from managed devices. Once a client certificate is authenticated by the Proxy, the device is considered managed and policies on managed and unmanaged devices take effect. This can be leveraged by both apps configured by Azure AD and apps configured by other identity providers. 

For more information about the deployment process, see [Proxy deployment](proxy-deployment.md).

![Cloud App Security Proxy architecture](./media/proxy-architecture.png)

## User login flow

1. User sends a request to the identity provider and provides credentials.
2.  If access is allowed, the identity provider redirects the user to the Cloud App Security Proxy.
3.  If the user has a client certificate installed, and there is a relevant policy that checks for managed or unmanaged devices, then the user is prompted to provide client certificates. Either way, an access policy is evaluated.
4.   At this point, there are 3 possible options:
    -   The user is allowed to access the app
    -   The user is blocked from accessing the app
    -   The user is allowed to access the app, but in monitored mode
        -   In this case, the user is redirected again to the Cloud App Security Proxy, which monitors the entire session between the user and the app. While monitoring, the Proxy evaluates the session policies and can perform blocking actions accordingly.

>[!NOTE]
> The diagram above depicts an *Identity provider initiated login*. If the user starts from the app, a *Service provider initiated login*, they are directed to the Cloud App Security Proxy and then to the identity provider, before completing the *Identity provider initiated login* flow.

## Managed devices flow

To identify managed devices not managed by Azure AD, the Proxy uses the mechanism of Client certificates. The mechanism works as follows:

1   If the user has a client certificate installed on her device, and there is a relevant policy that checks for managed or unmanaged devices.
   -   When the user arrives at the Proxy page during the login phase, the Proxy requests a client certificate from the user’s device.

   -   The user device is prompted to provide the client certificate, and if she approves, the client certificate is sent to the Proxy.

   -   The Proxy then authenticates the client certificate against the root certificate provided by the admin.

   -   If the client certificate provided by the device is successfully authenticated with the root certificate, then the device is considered managed.

-   If any of the previous phases is not completed, the device is considered unmanaged.



## See Also  
[Proxy deployment](proxy-deployment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  