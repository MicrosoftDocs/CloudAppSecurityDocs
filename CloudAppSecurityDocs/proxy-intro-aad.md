---
# required metadata

title: Protect with Microsoft Cloud App Security Conditional Access App Control
description: This article provides information about how the Cloud App Security Conditional Access App Control reverse proxy works.
keywords:
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 1/29/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
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
ms.custom: seodec18

---
# Protect apps with Microsoft Cloud App Security Conditional Access App Control

*Applies to: Microsoft Cloud App Security*

>[!div class="step-by-step"]
[NEXT: Deploy Conditional Access App Control »](proxy-deployment-aad.md)


In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact. You want to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. It's important to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time. Together with Azure Active Directory, Microsoft Cloud App Security delivers these capabilities in a holistic and integrated experience with Conditional Access App Control.

> [!NOTE]
> To use Cloud App Security Conditional Access App Control, you need an [Azure Active Directory P1 license](https://azure.microsoft.com/pricing/details/active-directory/) and an active Microsoft Cloud App Security subscription.
>

## How it works

Conditional Access App Control uses a reverse proxy architecture and is uniquely integrated with Azure AD conditional access. Azure AD conditional access allows you to enforce access controls on your organization’s apps based on certain conditions. The conditions define *who* (user or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a conditional access policy is applied to. After you’ve determined the conditions, you can route users to Microsoft Cloud App Security where you can protect data with Conditional Access App Control by applying access and session controls.

Conditional Access App Control enables user app access and sessions to be monitored and controlled in real time based on access and session policies. Access and session policies are used within the Cloud App Security portal to further refine filters and set actions to be taken on a user. With the access and session policies, you can:

- **Block on download**: You can block the download of sensitive documents. For example, on unmanaged devices.

- **Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be protected via encryption on download. This encryption makes sure the document is protected and user access is authenticated if the data is downloaded to an untrusted device. 

- **Monitor low-trust user sessions**: Risky users are monitored when they sign into apps and their actions are logged from within the session. You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future. 

- **Block access**: You can completely block access to specific apps for users coming from unmanaged devices or from non-corporate networks.

- **Create read-only mode**: By monitoring and blocking custom in-app activities, you can create a read-only mode to specific apps for specific users.  

- **Restrict user sessions from non-corporate networks**: Users accessing a protected app from a location that isn't part of your corporate network are allowed restricted access. The download of sensitive materials is blocked or protected.

### How session control works

Creating a session policy with Conditional Access App Control enables you to control user sessions by redirecting the user through a reverse proxy instead of directly to the app. From then on, user requests and responses go through Microsoft Cloud App Security rather than directly to the app.

To keep the user within the session, all the relevant URLs, Java scripts, and cookies within the app session are replaced with Microsoft Cloud App Security URLs. For example, if the app returns a page with links whose domains end with myapp.com, the link is replaced with domains ending with something like: myapp.com.us.cas.ms 

This method doesn't require you to install anything on the device. This method is ideal when monitoring sessions from unmanaged devices. 

After a session is directed through Microsoft Cloud App Security, the following actions can be done:

1. Inspect the traffic for user activities
2. Display the identified activities in the Microsoft Cloud App Security Activity log
3. Save the traffic logs and analyze them
4. Enable the admin to export the traffic logs
5. Enforce policies on the session

## Managed device identification

Conditional Access App Control enables you to create policies that take into account whether a device is managed or not. To identify whether a device is managed or not, the feature uses:

- Compliant devices
- Domain-joined devices
- Client certificates deployment
 
### Compliant and domain joined devices

Azure AD conditional access enables compliant and domain-joined device information to be passed directly to Microsoft Cloud App Security. From there, an access policy or a session policy can be developed that uses device state as a filter.
For more information, see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction). 

### Client-certificate authenticated devices

The device identification mechanism can request authentication from relevant devices using client certificates. You can either use existing client certificates already deployed in your organization or roll out new client certificates to managed devices. You then use the presence of those certificates to set access and session policies. For information on how to deploy client certificates see [Deploy Conditional Access App Control for Azure AD apps](proxy-deployment-aad.md).
 
## Supported apps and clients

Conditional Access App Control currently supports SAML and Open ID Connect apps configured with single sign-on, along with web apps hosted on-prem configured with the [Azure AD App Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
> [!NOTE]
> Conditional Access App Control also supports apps that are configured with identity providers other than Azure AD. For more information about this scenario, send an email to mcaspreview@microsoft.com.

**Session control is available for any browser on any major platform on any operating system**. Mobile apps and desktop apps can also be blocked or allowed. By natively integrating with Azure AD, any apps that are configured with SAML or Open ID Connect apps with single sign-on in Azure AD can be supported, including the following featured apps:

- AWS
- Azure DevOps (Visual Studio Team Services) (preview)
- Azure portal (preview)
- Box
- Concur
- CornerStone on Demand
- DocuSign
- Dropbox
- Egnyte
- Exchange Online (preview)
- G Suite
- GitHub
- HighQ
- JIRA/Confluence
- OneDrive for Business (preview)
- LinkedIn Learning
- Power BI (preview)
- Salesforce
- ServiceNow
- SharePoint Online (preview)
- Slack
- Tableau
- Microsoft Teams (preview)
- Workday
- Workiva
- Workplace by Facebook
- Yammer (preview)




Additional apps are being continuously on-boarded to session control. If you're interested in a specific app that isn't mentioned here, [send us details about the app](mailto:casfeedback@microsoft.com). Be sure to send the use case you're interested in for on-boarding it.



>[!div class="step-by-step"]
[NEXT: Deploy Conditional Access App Control »](proxy-deployment-aad.md)


## Next steps
[Deploy Conditional Access App Control for Azure AD apps](proxy-deployment-aad.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  


