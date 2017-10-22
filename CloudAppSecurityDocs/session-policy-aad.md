---
# required metadata

title: Create session policies to gain deep visibility into user session activities and block downloads | Microsoft Docs
description: This topic describes the procedure for setting up a Cloud App Security Proxy session policy gain deep visibility into user session activities and block downloads.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/18/2017
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

> [!NOTE]
> This is a preview feature.

Cloud App Security session policies enable real-time session-level monitoring, affording you granular visibility into cloud apps and the ability to take different actions depending on the filters you set for a user session. Instead of allowing or blocking access completely, with session control you can allow access while monitoring the session and/or limit specific session activities. 

For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the app, but also limit the download of sensitive files or require that certain documents be protected upon download. Session policies enable you to set these user-session controls. 

## Prerequisites to using session policies

- Azure AD Premium P2 license
- The relevant apps should be [deployed with proxy](proxy-deployment-aad.md)
- An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to the Cloud App Security proxy, as described below.


## Create an Azure AD conditional access policy

Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app. To set up a conditional access policy in Azure AD, follow this procedure:

1. Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users and the SAML app you want to control with the Cloud App Security proxy. 

  > [!NOTE]
  > Only apps that were [deployed with proxy](proxy-deployment-aad.md) will be affected by this policy.

2. Route users to the Cloud App Security proxy by selecting the **Use proxy enforced restrictions** in the **Session** blade.

 ![Proxy restrictions Azure AD conditional access](./media/proxy-deploy-restrictions-aad.png)

## Create a Cloud App Security session policy 

To create a new session policy, follow this procedure:

1. In the portal, select **Control** followed by **Policies**.
3. In the **Policies** page, click **Create policy** and select **Session policy**.  

 ![Create session policy](./media/create-session-policy.png)

4. In the **Session policy** window, assign a name for your policy, such as *Block Download of Sensitive Documents in Box for Marketing Users*.

 ![New session policy](./media/new-session-policy.png)

5. In the **Session control type** field: 

    1. Select **Monitor all activities** if you only want to monitor activities by users.

    2. Select **Monitor all activities & control file download** if you want to monitor  user activities and take additional actions, such as block or protect downloads for users.

    ![session policy control type](./media/session-policy-control-type.png)

6. Under **Activity source** in the **Activities matching all of the following** section, select additional activity filters to apply to the policy, these can include the following options: 

     - **Device tags**: Use this filter to identify unmanaged devices.

     - **Location**: Use this filter to identify unknown (and therefore risky) locations. 

     - **IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags. 

     - **User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps. This filter can be set to equals or does not equal **Native app** and should be tested against your mobile and desktop apps for each cloud app.

     ![session policy activity source](./media/session-policy-activity-filters.png)

7. If you selected the option to **Monitor all activities & control file download**:

    1. Under **Activity source** in the **Files matching all of the following** section, select additional file filters to apply to the policy. These can include the following options:

        - **Classification label** - Use this filter if your organization uses Azure Information Protection, and your data has been protected by its Classification labels. Here you will then be able to filter files based on the Classification label you applied to them. For more information about integration between Cloud App Security and Azure Information Protection, see [Azure Information Protection integration](azip-integration.md).

        - **File name** - Use this filter to apply the policy to specific files.
    
        - **File type** - Use this filter to apply the policy to specific file types, for example, block download for all .xls files.

       ![session policy file filters](./media/session-policy-file-filters.png)

    2. In the **Content inspection** section, set whether you want to enable the DLP engine to scan documents and file content.
 
     ![session policy content inspection](./media/session-policy-content-inspection.png)

    3. Under **Actions**, select one of the following: 

        - **Allow**: Set this action to explicitly allow download according to the policy filters you set.

        - **Block**: Set this action to explicitly block download according to the policy filters you set. For more information, see [How block download works](#block-download).

        - **Protect**: If your organization uses Azure Information Protection, you can set an **Action** to apply a classification label set in Azure Information Protection to the file. For more information, see [How protect download works](#protect-download).

         ![session policy actions](./media/session-policy-actions.png)

10. You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.

    ![session policy alert](./media/session-policy-alert.png)


## How block download works <a name="block-download"></a>

When **Block** is set as the **Action** you want to take in the Cloud App Security proxy session policy, the proxy prevents a user from downloading a file in accordance with the policy’s file filters. A download event is recognized by the proxy for each SAML app and when a user initiates this event, the proxy intervenes in real time to prevent it from running. When the signal is received that a user has initiated a download, the proxy returns a **Download restricted** message to the user and replaces the downloaded file with a text file that contains a customizable message to the user, which can be configured from the proxy session policy.  

## How to protect download works <a name="protect-download"></a>

When **Protect** is set as the **Action** to be taken in the Cloud App Security proxy session policy, the proxy enforces the labeling and subsequent protection of a file in accordance with the policy’s file filters. Labels are configured in the Azure Information Protection console in Azure and **Protect** must be selected within the label for the label to appear as an option in the Cloud App Security
 policy. When a label is selected, and a file is downloaded that meets the criteria of the Cloud App Security policy, the label, and corresponding protection (with permissions) is applied to the file upon download. The original file remains as-is in the cloud app while the downloaded file is now protected. Users who attempt to access the file must meet the permission requirements determined by the protection applied.  
 
  
## See Also  
[Blocking downloads on unmanaged devices using Azure AD proxy capabilities](use-case-proxy-block-session-aad.md)   
[For technical support, visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  