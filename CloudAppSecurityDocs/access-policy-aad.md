---
# required metadata

title: Create Cloud App Security access policies to allow and block access
description: This article describes the procedure for setting up a Cloud App Security Conditional Access App Control access policy to allow and block access to apps connected through Azure AD using reverse proxy capabilities.
keywords:
author: rkarlin
ms.author: rkarlin
manager: angrobe
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 9095cff1-f8b0-44a7-b1df-a83e674abbc6



# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Access policies

*Applies to: Microsoft Cloud App Security*

>[!div class="step-by-step"]
[« PREVIOUS: How to create a session policy](session-policy-aad.md)<br>
[NEXT: Explore popular use cases »](use-case-proxy-block-session-aad.md)

Microsoft Cloud App Security access policies enable real-time monitoring and control over access to cloud apps based on user, location, device, and app. You can create access policies for any device, including devices that aren't domain joined, and not managed by Windows Intune by rolling out client certificates to managed devices or by using existing certificates, such as third-party MDM certificates. For example, you can deploy client certificates to managed devices, and then block access from devices without a certificate. 

> [!NOTE]
> Instead of allowing or blocking access completely, with [session policies](session-policy-aad.md) you can allow access while monitoring the session and/or limit specific session activities. 

## Prerequisites to using access policies

- Azure AD Premium P1 license
- The relevant apps should be [deployed with Conditional Access App Control](proxy-deployment-aad.md)
- An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Microsoft Cloud App Security, as described below.

> [!NOTE]
> - Access policies also support apps that are configured with identity providers other than Azure AD. For more information send an email to mcaspreview@microsoft.com.

## Create an Azure AD conditional access policy

Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app. To set up a conditional access policy in Azure AD, follow this procedure:

1. Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users and the app you want to control with Conditional Access App Control. 

   > [!NOTE]
   > Only apps that were [deployed with Conditional Access App Control](proxy-deployment-aad.md) will be affected by this policy. 

2. Route users to Microsoft Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** under **Session**.
 
## Create a Cloud App Security access policy 

To create a new access policy, follow this procedure:

1. In the portal, select **Control** followed by **Policies**.
2. In the **Policies** page, click **Create policy** and select **Access policy**.  

3. In the **Access policy** window, assign a name for your policy, such as *Block access from unmanaged devices*.

4. In the **Activities matching all of the following** section, Under **Activity source**, select additional activity filters to apply to the policy. Filters include the following options: 
     
   - **Device tags**: Use this filter to identify unmanaged devices.

   - **Location**: Use this filter to identify unknown (and therefore risky) locations. 

   - **IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags. 

   - **User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps. This filter can be set to equals or does not equal. The values should be tested against your mobile and desktop apps for each cloud app.
  
5. Under **Actions**, select one of the following options: 

    - **Allow**: Set this action to explicitly allow access according to the policy filters you set.

    - **Block**: Set this action to explicitly block access according to the policy filters you set. 

6. You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.



>[!div class="step-by-step"]
[« PREVIOUS: How to create a session policy](session-policy-aad.md)<br>
[NEXT: Explore popular use cases »](use-case-proxy-block-session-aad.md)

 
## Next steps  
[Blocking downloads on unmanaged devices using Azure AD Conditional Access App Control capabilities](use-case-proxy-block-session-aad.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
