---
# required metadata

title: Create session policies to gain deep visibility into user session activities and block downloads | Microsoft Docs
description: This topic describes the procedure for setting up a Cloud App Security Proxy session policy gain deep visibility into user session activities and block downloads.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/8/2017
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
Azure Active Directory conditional access policies and Cloud App Security proxy session policies work in tandem to examine each user session and make policy decisions for each app. **Create both an Azure AD conditional access policy and a Cloud App Security Session policy to make sure the appropriate session controls are in place**.

## How session control works 

The Proxy’s session control is built on top of conditional access. After you control access to an app, your session policies will then determine the controls over a user’s session. From single sign-on through to the session itself, user requests and responses go through the proxy rather than directly to the app. 
To keep the user within the session, the Proxy replaces all the relevant URLs, Java scripts, and cookies within the app to pages duplicated in the Proxy. For example, if the app returns a page with links that end with myapp.com, the proxy replaces them with pages that end with something like myapp.com.Cloud App Security.ms. 
After a session is directed through the Proxy, the Proxy can inspect the traffic, display the events it identifies in the Cloud App Proxy portal, and enforce policies on the session. 

## Azure AD conditional access policies  

Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users AND the SAML app you want to control with the Cloud App Security proxy.  

First establish the conditions: who and what you want to control. Then route users to Cloud App Security. The Cloud App Security proxy is found under Session controls, which are a specific type of access control that enables limited experiences within a cloud application. 

To create a new conditional access policy in Azure AD, follow these steps.  

### Prerequisites for creating an Azure AD conditional access policy  

- Azure AD Premium 2 subscription 
- Azure access credentials  
- SAML application configured for SSO  
- Cloud App Security portal access 

### Create an Azure AD conditional access policy 

Sign in to the Azure as the tenant admin, and create a new **Conditional access** policy. For more information on creating Azure AD Conditional access policy, see [Conditional access in the Azure classic portal](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

 ![Azure AD conditional access](./media/aad-conditional-access.png)

Make sure that under **Access controls** you select **Session** and select **Use proxy enforced restrictions** and then **Configure Cloud App Security**. You are redirected to the Cloud App Security portal to configure your session policies.

## Create a Cloud App Security proxy session control policy 

Session controls enable deep session-level monitoring, affording you granular visibility into cloud apps and the ability to take different actions depending on the filters you set for a user session. Instead of allowing and blocking access completely, with session control you can limit specific session activities. 

For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the app, but also limit the download of sensitive files or require that certain documents be protected upon download. Cloud App Security proxy session policies enable you to set these user-session controls.  

To create a new proxy session policy, follow these steps.

### Prerequisites for creating a proxy session policy  

- Azure AD conditional access policy set for user(s) and app 
- App configured for SSO with Azure AD  

### Create a Cloud App Security proxy session policy

1. Sign in to the Cloud App Security portal as the tenant admin. 
2. Select **Control** followed by **Policies**.
3. In the **Policies** page, click **Create policy** and then select **Session policy**.  

 ![Create session policy](./media/create-session-policy.png)

4. In the **Session policy** window, assign a name for your policy, such as *Block Download of Sensitive Documents in Box for Marketing Users*.

 ![New session policy](./media/new-session-policy.png)

5. In the **Session control type** field: 
    1. Select **Monitor all activities** if you only want to monitor activities by users.  
    2. Select **Monitor all activities & control file download** if you want to monitor user activities and take additional actions, such as block or protect downloads for users.

 ![session policy control type](./media/session-policy-control-type.png)

6. Under **Activity source activities matching all of the following**, select additional activity filters to apply to the policy. 
     - **Device tags**: Use this filter to identify unmanaged devices.
     - **Location**: Use this filter to identify unknown (and therefore risky) locations. 
     - **IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags. 

 ![session policy activity source](./media/session-policy-activity-filters.png)

7. Under **Activity source files matching all of the following**, select additional file filters to apply to the policy 
    - **Classification label** - Use this filter if your organization uses Azure Information Protection, and your data has been protected by its Classification labels. Here you will then be able to filter files based on the Classification label you applied to them. For more information about integration between Cloud App Security and Azure Information Protection, see [Azure Information Protection integration](azip-integration.md).
    - **File name** - Use this filter to apply the policy to specific files.
    - **File type** - Use this filter to apply the policy to specific file types, for example, block download for all .xls files.

 ![session policy file filters](./media/session-policy-file-filters.png)

8. Set **Content inspection** if you want to enable the DLP engine to scan documents and file content.
 
 ![session policy content inspection](./media/session-policy-content-inspection.png)

9. Under **Actions**, select one of the following: 
    - **Allow**: Set this action to explicitly allow download according to the policy filters you set.
    - **Block**: Set this action to explicitly block download according to the policy filters you set. For more information, see [How block download works](#block-download)
    - **Protect**: If your organization uses Azure Information Protection, you can set an **Action** to apply a classification label set in Azure Information Protection to the file. For more information, see [How protect download works](#protect-download)

 ![session policy actions](./media/session-policy-actions.png)

10. You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.

 ![session policy alert](./media/session-policy-alert.png)


## How block download works <a name="block-download"></a>

When **Block** is set as the **Action** you want to take in the Cloud App Security proxy session policy, the proxy prevents a user from downloading a file in accordance with the policy’s file filters. A download event is recognized by the proxy for each SAML app and when a user initiates this event, the proxy intervenes in real time to prevent it from running. When the signal is received that a user has initiated a download, the proxy returns a **Download restricted** message to the user and replaces the downloaded file with a text file that contains a customizable message to the user, which can be configured from the proxy session policy.  

## How to protect download works <a name="protect-download"></a>

When **Protect** is set as the **Action** to be taken in the Cloud App Security proxy session policy, the proxy enforces the labeling and subsequent protection of a file in accordance with the policy’s file filters. Labels are configured in the Azure Information Protection console in Azure and **Protect** must be selected within the label for the label to appear as an option in the Cloud App Security policy. When a label is selected, and a file is downloaded that meets the criteria of the Cloud App Security policy, the label, and corresponding protection (with permissions) is applied to the file upon download. The original file remains as-is in the cloud app while the downloaded file is now protected. Users who attempt to access the file must meet the permission requirements determined by the protection applied.  
 
  
## See Also  
[Blocking downloads on unmanaged devices using Azure AD proxy capabilities](use-case-proxy-block-session-aad.md)   
[For technical support, visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  