---
# required metadata

title: Create session policies to gain deep visibility into user session activities and block downloads | Microsoft Docs
description: This topic describes the procedure for setting up a Cloud App Security Proxy session policy gain deep visibility into user session activities and block downloads.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/3/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 745df28a-654c-4abf-9c90-203841169f90

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Session policies  
Azure AD conditional access policy and Cloud App Security proxy session policy work in tandem to examine each user session and make policy decisions for each app. **You must build both an Azure AD conditional access and a Cloud App Security proxy session policy to ensure the appropriate session controls are in place**.

## Azure AD conditional access policies  

You must configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users AND the SAML app you want to control the app with the Cloud App Security proxy.  

After establishing the conditions – who and what you want to control – you then select to route users to Cloud App Security. The Cloud App Security proxy is found under session controls, which are a specific type of access control to enable limited experiences within a cloud application. 

To create a new conditional access policy in Azure AD, follow these steps.  

### Prerequisites for creating a conditional access policy  

- Azure AD Premium 2 subscription 
- Azure portal login  
- SAML Application configured for SSO  
- Cloud App Security portal login 

### Create an Azure AD conditional access policy 

1. Sign in to the Azure portal as the tenant admin (portal.azure.com).
2. Select “Azure Active Directory”.
3. Select “Conditional Access”.
4. Select “+ New Policy” .
5. Assign a name for your policy (eg: “Route Marketing Users in Box to Cloud App Security”) 
6. Select “Users and Groups” under Assignments.
    1. Assign users or groups of users using the search function and people picker.
8. Select “Cloud Apps” under Assignments 
    1. Assign SAML app of your choice 
10. Select “Session” under Access Controls 
    1. Select “Use proxy enforced restrictions”  
11. Select “Configure Cloud App Security” . You will be redirected to the Cloud App Security portal to configure session policies.

## Create a Cloud App Security proxy session control policy 
Session controls enable deep session-level monitoring, affording you granular visibility into cloud apps and the ability to take different actions depending on the filters you’ve set for a user’s session. Instead of allowing and blocking access completely, with session control you can limit specific session activities. 

For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the app, but also limit the download of sensitive files or require that certain documents be protected upon download. The Cloud App Security proxy session policies determine the monitors and controls for a user’s session.  

To create a new proxy session policy, follow these steps.

### Prerequisites for creating a proxy session policy  

- Azure AD conditional access policy set for user(s) and app 
- App configured for SSO with Azure AD  

### Create a Cloud App Security proxy session policy

1. Sign in to Cloud App Security portal as the tenant admin 
2. Select “Control” then “Policies” 
3. Select “Create policy, session policy”  
4. Assign a name for your policy (eg “Block Download of Sensitive Documents in Box for Marketing Users”  
5. Select “Session Control Type” dropdown 
    1. Select “monitor all activities” if you only want to monitor actions by users  
    2. Select “monitor all activities & control file download” if you want to monitor and take additional actions, such as block or protect downloads for users 
6. Under “Activity source” select additional activity filters to apply to policy 
     - Device Tags: used to identify unmanaged devices. Additional information can be found below  
     - Location: can be used to identify unknown (and therefore risky) locations 
     - IP Address: can be utilized based on previously assigned IP address tags 
7. Under “Activity source” select additional file filters to apply to policy 
    - Classification label 
    - File name 
    - File type 
8. Select “content inspection” if you want to enable the DLP engine to scan documents and files  
9. Under “Actions” select one of the following: 
    - Allow: explicitly allows the download according to the policy filters set 
    - Block: explicitly blocks the download according to the policy filters set  
    - Protect: applies a classification label set in Azure Information Protection to the file 


## How session control works 

The Proxy’s session control is built on top of conditional access. After you control access to an app, your session policies will then determine the controls over a user’s session. From single sign-on through to the session itself, user requests and responses go through the proxy rather than directly to the app. 
To keep the user within the session, the Proxy replaces all the relevant URLs, Java scripts, and cookies within the app to pages duplicated in the Proxy. For example: if the app returns a page with links that end with myapp.com, the proxy will replace them with pages that end with something like myapp.com.Cloud App Security.ms. 
Once a session is directed through the Proxy, the Proxy can inspect the traffic, display the events it identifies in the Cloud App Proxy portal, and enforce policies on the session. 

## How block download works 

When “block” is selected under “actions” in the Cloud App Security proxy session policy, the proxy will prevent a user from downloading a file in accordance with the policy’s file filters. A download event is recognized by the proxy for each SAML app and when a user initiates this event, the proxy intervenes real time to prevent it from executing. When the signal is received that a user has initiated a download, the proxy returns a “download restricted” message to the user and replaces the downloaded file with a text file that contains a customizable message to the user, which can be configured from the proxy session policy.  

## How protect download works 

When “protect” is selected under “actions in the Cloud App Security proxy session policy, the proxy will enforce the labelling and subsequent protection of a file in accordance with the policy’s file filters. Labels are configured in Azure Information Protection console in the Azure portal and “protect” must be selected within the label for the label to appear as an option in the Cloud App Security policy. When a label is selected, and a file is downloaded that meets the criteria of the Cloud App Security policy, the label and corresponding protection (with permissions) is applied to the file upon download. The original file remains as-is in the cloud app while the downloaded file is now protected. Users wishing to access the file must meet the permissions requirements determined by the protection applied.  
 
  
## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  