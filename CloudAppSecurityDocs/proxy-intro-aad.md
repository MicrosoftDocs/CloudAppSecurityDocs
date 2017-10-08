---
# required metadata

title: Working with the Cloud App Security proxy | Microsoft Docs
description: This topic provides information about how the Cloud App Security proxy works.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/8/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 35a43120-bf67-4cf9-9b48-ebe157dbbd18

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Working with the Cloud App Security proxy

In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact, you want to be able to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. You need to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft in real time. Together with Azure Active Directory, the Cloud App Security proxy delivers these capabilities in a holistic and integrated experience.

## Cloud App Security proxy data protection
The Cloud App Security proxy gives you the tools you need to have real-time visibility and control over access to and activities performed within your cloud environment.
With the proxy, you can protect your organization:
- Avoid data leaks by blocking downloads before they happen
- Minimize your exposure to ransomware by managing and blocking access to your network from unmanaged devices that may not be password protected or have antivirus software installed
- Set rules that force data stored in and downloaded from the cloud to be protected with encryption
- Gain visibility into unprotected endpoints so you can monitor what's being done on unmanaged devices
- Control access from risky IP addresses and legacy identity providers

To enable these unique capabilities, use the two levels of control provided by the proxy: conditional access and session control. Both types of control leverage user information, location information, and device information, to make policy decisions for each app.

## Better together Cloud App Security and Azure AD

Azure AD conditional access is a capability that allows you to enforce access controls on your organization’s apps based on certain conditions. Azure AD conditions define who (for example a user, or group of users) and what (what cloud app) a conditional access policy is applied on. After you’ve determined the conditions, you set the controls in a Cloud App Security session policy. After the conditional access policy is set and the Cloud App Security proxy is selected, Azure AD evaluates each user’s sign in and routes the user to the proxy when applicable. The Cloud App Security proxy is then used to control and limit actions within the browser-based session.

## Protection with Cloud App Security proxy

After a user is routed to the Cloud App Security proxy, their app session can be monitored and controlled in real time. Session policies are utilized within the Cloud App Security portal to further refine session filters and set actions to be taken on a user. 
With the proxy, you can:
-	Restrict user sessions from non-corporate networks: Users accessing a protected app, from a location that is not part of your corporate network, are allowed restricted access and the download of sensitive materials are blocked.  
-	Monitor low-trust user sessions: Risky users are monitored when they sign into apps and their actions are logged from within the session. You can perform investigation and analysis into user behavior to understand where, and under what conditions, session policies should be applied in the future. 
-	Block on download: You can restrict the download of sensitive documents on unmanaged devices or from users accessing the application from unknown or non-corporate network locations. 
-	Protect on download: Instead of blocking the download of sensitive documents, you can instead require documents to be protected via encryption on download. This ensures that the document is protected, and user access authenticated, if the data is downloaded to an untrusted device or from an untrusted location. 

These key use cases ensure you have a robust protection strategy that allows you to: 
-	Avoid data leaks by blocking downloads before they happen.
-	Minimize your exposure to ransomware by managing and blocking access to your network from unmanaged devices that may not be password protected or have antivirus software installed.
-	Enforce data protection for data stored in, and downloaded from, the cloud. 
-	Gain visibility into unprotected endpoints so you can monitor what's being done on unmanaged devices.
-	Control access from risky IP addresses. 


## Session control

Session control provides an additional layer of control by providing insight into activities in user sessions, for both Azure AD apps and apps configured by other identity providers. Session control enables session-level monitoring, affording you granular visibility into cloud apps even from unmanaged devices and devices that are off-premises. Instead of allowing and blocking access completely, with session control you can limit specific session activities.  

For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the application, but limit the download of sensitive files. 

### How session control works

The proxy’s session control is built on top of conditional access. After you control access to an app, you can set session policies that will redirect user sessions to the proxy’s session control. From then on, user requests and responses go through the proxy rather than directly to the app.

To keep the user within the session, the proxy replaces all the relevant URLs, Java scripts, and cookies within the app to pages duplicated in the proxy. For example: if the app returns a page with links whose domain ends with *myapp.com*, the proxy will replace the links with domains such as: *myapp.com.Cloud App Security.ms*

After a session is directed through the proxy, the proxy can inspect the traffic, display the events it identifies in the Cloud App proxy portal, and enforce policies on the session.

## Architecture

Integration with proxy capabilities is made simple with Azure Active Directory. To set other identity providers and apps to work with the proxy, both need to be configured to redirect login requests to the proxy.

In addition, in order identify managed devices, you can leverage Azure AD domain joined and Intune compliant devices for easy device identification in policy creation. Alternatively, the proxy can request client certificates to identify managed devices. Once a client certificate is authenticated by the proxy, the device is considered managed and policies on managed and unmanaged devices take effect.

For more information about the deployment process, see [Proxy deployment](proxy-deployment.md).

![Cloud App Security proxy architecture](./media/proxy-architecture.png)

### User login flow
1. User accesses an SSO-configured app with Azure AD credentials.  
2. Azure AD evaluates the single-sign on request for presence of conditional access policies governing both the user and the app in question.  
3. If unconditional access is allowed, the user proceeds to application.  
4. If conditional access is invoked, Azure AD redirects the user to the Cloud App Security proxy.  
5. The Cloud App Security proxy evaluates the user for a relevant session policy; if no policy is in place the user will bypass the proxy. 
6. If a session policy is in place and checks for managed devices, then the user is prompted to provide client certificates. Information on domain-joined or compliant devices was received from the Azure AD redirect in step 4.  
7. At this point, there are 3 possible options: 
    1. The user is blocked from accessing the app. 
    2. The user is allowed access to the app, but is under one of the following actions:  
        - Monitor 
        - Monitor and block download 
        - Monitor and protect download  

## Device identification

Cloud App Security enables you to identify and create policies based on device posture. In order to identify whether a device is managed or not, Cloud App Security leverages:
 - Intune compliant devices* 
 - Azure AD domain joined devices* 
 - Client certificates deployment (for all apps)

* Only available for Azure AD apps where conditional access is available

### Intune compliant devices 
Devices can be marked as compliant either by Intune or by a third party mobile device management (MDM) system for Windows 10 devices. Only Azure AD connected devices can be compliant.  

### Azure AD domain joined devices

Azure AD conditional access enables compliant or domain-joined device information to be passed directly to the Cloud App Security proxy. From there, a session policy can be developed that uses device state as a filter.  
For more information see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction). 

To connect a device to Azure AD, the device must either be Azure AD registered, joined or Hybrid Azure AD joined. Registering a device in Azure AD enabled the device’s identity to be used during authentication to Azure AD. Joining a device to Azure AD takes this one step further and allows a user to sign in to a device using an organizational account.  

### Client-certificate authenticated devices


## Supported apps and identity providers

Azure AD conditional access supports most SAML apps for browser-based sessions. The Cloud App Security team tested many popular SAML apps with the conditional access capabilities. However, since there are many cloud apps, we recommend first testing the conditional access and proxy flows with your application in a sandbox or testing environment before deploying it in a production environment. 





## See Also  
[Deploy the Cloud App Security proxy](proxy-deployment-aad.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  


