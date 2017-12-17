---
# required metadata

title: Protect with Microsoft Cloud App Security proxy | Microsoft Docs
description: This topic provides information about how the Cloud App Security proxy works.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/17/2017
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

# Protect apps with Microsoft Cloud App Security proxy

> [!NOTE]
> This is a preview feature.


In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact, you want to be able to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. It is important to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time. Together with Azure Active Directory, the Cloud App Security proxy delivers these capabilities in a holistic and integrated experience.

## How it works

The Cloud App Security proxy is integrated with Azure AD conditional access. Azure AD conditional access allows you to enforce access controls on your organization’s apps based on certain conditions. The conditions define *who* (for example a user, or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a conditional access policy is applied to. After you’ve determined the conditions, you can route users to the Cloud App Security proxy where you can apply access and session controls.

After a user is routed to the Cloud App Security proxy, their app access and sessions can be monitored and controlled in real time based on access and session policies. Access and session policies are utilized within the Cloud App Security portal to further refine filters and set actions to be taken on a user. With the access and session policies, you can:

-	**Block on download**: You can block the download of sensitive documents. For example, on unmanaged devices.

-	**Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be protected via encryption on download. This ensures that the document is protected, and user access is authenticated, if the data is downloaded to an untrusted device. 

-	**Restrict user sessions from non-corporate networks**: Users accessing a protected app from a location that is not part of your corporate network, are allowed restricted access and the download of sensitive materials is blocked or protected.

-	**Monitor low-trust user sessions**: Risky users are monitored when they sign into apps and their actions are logged from within the session. You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future. 

- **Block access**: You can completely block access to specific apps for users coming from users coming from unmanaged devices or from non-corporate networks.


### How session control works

The proxy’s session control is built on top of conditional access. After you control access to an app, you can redirect the user sessions to the proxy’s session control instead of directly to the app. From then on, user requests and responses go through the proxy rather than directly to the app.

To keep the user within the session, the proxy replaces all the relevant URLs, Java scripts, and cookies within the app session with proxy URLs. For example: if the app returns a page with links whose domains end with myapp.com, the proxy replaces the links with domains ending with something like: myapp.com.us.cas.ms 

This method does not require you to install anything on the device. This is ideal when monitoring sessions from unmanaged devices. 

After a session is directed through the proxy, the proxy can perform the following:
1. Inspect the traffic for user activities
3. Display the identified activities in the Cloud App proxy portal
2. Save the traffic logs and analyze them
3. Enable the admin to export the traffic logs
4. Enforce policies on the session

## Managed device identification

The proxy enables you to create policies that take into account whether a device is managed or not. To identify whether a device is managed or not, the proxy leverages:

-	Compliant devices 
-	Domain-joined devices 
-	Client certificates deployment
 
 
### Compliant and domain joined devices
Azure AD conditional access enables compliant and domain-joined device information to be passed directly to the Cloud App Security proxy. From there, an access policy or a session policy can be developed that uses device state as a filter.
For more information, see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction). 

### Client-certificate authenticated devices

The proxy device identification mechanism can request authentication from relevant devices using client certificates. This enables you to either leverage existing client certificates already deployed in your organization or to roll out new client certificates to managed devices, and then use the presence of those certificates to set access and session policies. For information on how to deploy client certificates see [Deploy proxy for Azure AD apps](proxy-deployment-aad.md).
 
## Supported apps and clients

The proxy currently supports apps that are configured with SAML single sign on in Azure AD. 

> [!NOTE]
> The proxy also supports apps that are configured with identity providers other than Azure AD in Private Preview. For more information about the Private Preview, send an email to mcaspreview@microsoft.com.

In addition, session control is not automatically available for all apps. The Cloud App Security team tested many popular apps with session control. Other apps may require an onboarding process that will be done with the customer.
In terms of clients, session control is available for any browser on any major platform. However, mobile apps and desktop apps are not supported by session control. 

> [!NOTE]
> Office 365 applications are not configured with SAML so they are not currently supported.


## See Also  
[Deploy the Cloud App Security proxy](proxy-deployment-aad.md)   
[For technical support, visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  


