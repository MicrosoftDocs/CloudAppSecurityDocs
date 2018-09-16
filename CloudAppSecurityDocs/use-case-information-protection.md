---
# required metadata

title: Automatically apply Azure Information Protection classification labels | Microsoft Docs
description: This topic describes the process to automatically apply Azure Information Protection classification labels in Microsoft Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: eac0b192-98d7-4939-9a07-1d4a7f8c39c3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
*Applies to: Microsoft Cloud App Security*



# Automatically apply Azure Information Protection classification labels  

In a perfect world, all your employees understand the importance of information protection and work within your policies. But in a real world, it's probable that a partner who works with accounting uploads a document to your Box repository with the wrong permissions, and a week later you realize that your enterprise's confidential information was leaked to your competition. 

Microsoft Cloud App Security helps you prevent this kind of disaster before it happens.

Microsoft Cloud App Security identifies that there are public permissions on a document saved in your Box account, and uses a classification engine to identify that there is confidential information in the publicly shared document. Cloud App Security sends you an alert to let you know this occurred, and in addition, it automatically applies your Azure Information Protection **Confidential** classification label to provide added encryption to the file. 

>[!NOTE]
> - Applying an Azure Information Protection label is one of a long list of available [governance actions](governance-actions.md).
> - This feature is available for Box, SharePoint and OneDrive for Business.

### Enhanced data-level encryption protection

Cloud App Security integration with Azure Information Protection enables an added level of protection by automatically encrypting files. For example, while Azure Information Protection encrypts the file, applications that support Azure Information Protection (such as Office 365) know how to open the files and honor the permissions set in the classification labels. You can use labels to apply specific protection rules. For example, you can set a file so that it can be opened but cannot be shared, printed, forwarded, or edited). 

This strong level of protection travels with the file - if you send the file, copy it, store it in your online storage app, the file is still protected. If one of your employees lost a thumbdrive with the file on it, the file will be locked and if someone tries to open it, the file owner will receive an alert. With Cloud App Security, you can apply protection automatically. For example, all files that have credit card numbers or were uploaded by the finance department and are shared externally, can be set to be automatically protected with a classification label. 

## The threat 
A user in your organization saves confidential customer information files to Box and sets it to be shared with everyone in the organization. The user doesn't realize that in addition to their immediate team, the entire support staff has access to that Box account, including vendors, partners and visitors who occasionally stop into the office. Any person with access to your organization's Box account now has access to that information. Not only can that be dangerous for your organization, it can be against PII regulations in many countries, causing potential legal issues.

## The solution
Use Cloud App Security with Azure Information Protection to embed classification and protection information for persistent protection that follows your data—ensuring it remains protected regardless of where it’s stored or who it’s shared with. This also enables you to share data safely with coworkers as well as your customers and partners. Define who can access data and what they can do with it -- such as allowing users to view and edit files but not print or forward -- in addition to other [governance actions](governance-actions.md) supported by Cloud App Security, such as remove collaborators and remove sharing abilities.

## Prerequisites

- [Enable Cloud App Security and Azure Information Protection](azip-integration.md) for your tenant.
- [Connect Box](connect-box-to-microsoft-cloud-app-security.md) to Cloud App Security.

## Setting up data protection

Let's set up a policy that looks for credit card numbers in files stored in your Box account, and when they are found, automatically apply an Azure Information Protection label and then control what happens to all files with that label.

1. Start protecting the data you store in Box by setting up a policy that will encrypt any sensitive data stored in Box:

    1. On the **Control** tab, click [**Policies**](control-cloud-apps-with-policies.md). 
    
    2. Click **Create policy** and select **File policy**.
    
    3. Call the policy *Box data protection*.
    
    4. Under **Create a filter for the files this policy will act on**, target your proprietary and sensitive data.<br></br>
    For example, select **Parent folder** equals **Customer data** in Box and select **Owner** equals and select the finance team.
    
    4. Within that folder, look for files that contain Credit Card information as follows: Under **Content inspection method** select **Built-in DLP** and then select **Include files that match a preset expression** and select **All countries:Finance:Credit card number**.
    
    5. Under **Governance**, open the **Box** section and select **Apply classification label** and select the label you want to apply.
    
    6. Because [Cloud App Security is integrated with Azure Information Protection](azip-integration.md), you can select from your existing list of classification labels to be used to protect the data.
 
    7. Click **Create**. 
   
   ![Add classification label to policy](./media/aip-auto-policy.png)
     
2. Investigating your matches
    
    1. In the **Policies** page, click on the policy name to go to the **Policy report** and review the matches that were triggered for the policy.

    2. You can investigate the match by clicking on a specific match to open the file drawer. In the drawer, you can see the other policies that this file matched. 
     
## Validating your policy

1. To simulate an alert, go to your Box account and attempt to access a file in the folder **Customer data**.
3. Go to the policy report. A file policy match should appear shortly. 
4. You can click on the match to see which files were protected. The match itself will be masked to protect the sensitive data. 

>[!NOTE]
> - Cloud App Security currently supports automatic application of Azure Information Protection labels on Box, SharePoint and OneDrive for business.
> - When a document is labeled by using Cloud App Security, visual markings are not immediately applied but are applied when that document is opened in an Office app and the document is first saved. For more information, see [How to configure a label for visual markings for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-markings#when-visual-markings-are-applied).

 ## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  