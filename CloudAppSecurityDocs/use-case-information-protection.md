---
# required metadata

title: Automatically apply Azure Information Protection classification labels
description: This tutorial describes how to automatically apply Azure Information Protection classification labels in Microsoft Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: angrobe
ms.date: 3/5/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
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
ms.custom: seodec18
#Customer intent: As a sec op, I want to apply AIP labels automatically so that I can monitor classified files.

---
# Tutorial: Automatically apply Azure Information Protection classification labels

*Applies to: Microsoft Cloud App Security*

In a perfect world, all your employees understand the importance of information protection and work within your policies. But in a real world, it's probable a partner who works with accounting uploads a document to your Box repository with the wrong permissions. A week later you realize your enterprise's confidential information was leaked to your competition. Microsoft Cloud App Security helps you prevent this kind of disaster before it happens. This feature is available for Box, SharePoint and OneDrive for Business. Applying an Azure Information Protection label is one of a long list of available [governance actions](governance-actions.md).

This tutorial helps you identify which public permissions are set on a document that's saved in your cloud storage, so you are alerted when a breach occurs. In addition, you can automatically apply your Azure Information Protection **Confidential** classification label to provide added encryption to files.

> [!div class="checklist"]
> * Set up data protection 
> * Validate your policy


## Enhanced data-level encryption protection

Cloud App Security integration with Azure Information Protection enables an added level of protection by automatically encrypting files. When Azure Information Protection encrypts files, applications that support Azure Information Protection like Office 365, know how to open the files and honors permissions set in the classification labels. Use labels to apply specific protection rules. For example, set a file that can be opened but not shared, printed, forwarded, or edited.

This strong level of protection travels with the file. The file is still protected if you send the file, copy it, or store it in your online storage app. If one of your employees loses a thumb drive with the file on it, the file will be locked. Should someone try to open the file, the file owner will receive an alert. With Cloud App Security, you can apply protection automatically. For example, set all files that have credit card numbers, or were uploaded by the finance department and are shared externally, to be automatically protected with a classification label.

## The threat

A user in your organization saves confidential customer information files to Box and sets it to be shared with everyone in the organization. The user doesn't realize that not only their immediate team, but the entire support staff has access to that Box account. This access includes vendors, partners, and visitors who occasionally stop into the office. Any person with access to your organization's Box account now has access to that information. Not only can that access be dangerous for your organization, it can be against personal information regulations in many countries, causing potential legal issues.

## The solution

Use Cloud App Security with Azure Information Protection to embed classification and protection information for persistent protection that follows your data — so it stays protected no matter where it’s stored or who it’s shared with. This protection enables you to share data safely with coworkers, customers, and partners. Define who can access data and what they can do with it. For instance, allow users to view and edit files but not print or forward. You can also add other [governance actions](governance-actions.md) supported by Cloud App Security to the files such as remove collaborators and remove sharing abilities.

## Prerequisites

- [Enable Cloud App Security and Azure Information Protection](azip-integration.md) for your tenant.
- [Connect Box](connect-box-to-microsoft-cloud-app-security.md) to Cloud App Security.

## Set up data protection

Let's set up a policy that looks for credit card numbers in files stored in your Box account. When files are found, automatically apply an Azure Information Protection label and control what happens to all files with that label.

1. Start protecting the data you store in Box by setting up a policy that will encrypt any sensitive data stored in Box:

    1. On the **Control** tab, click [**Policies**](control-cloud-apps-with-policies.md). 

    2. Click **Create policy** and select **File policy**.

    3. Call the policy *Box data protection*.

    4. Under **Create a filter for the files this policy will act on**, target your proprietary and sensitive data.
        - For example, select **Parent folder** equals **Customer data** in Box and select **Owner** equals the finance team.

    5. Within that folder, look for files containing credit card information. Under **Content inspection method**, select **Built-in DLP**, select **Include files that match a preset expression**, and select **All countries:Finance:Credit card number**.

    6. Under **Governance**, open the **Box** section and select **Apply classification label**. Select the label you want to apply.

    7. Because [Cloud App Security is integrated with Azure Information Protection](azip-integration.md), you can select from your existing list of classification labels to be used to protect the data.

    8. Click **Create**. 

   ![Add classification label to policy](./media/aip-auto-policy.png)

2. Investigating your matches

    1. In the **Policies** page, click on the policy name to go to the **Policy report**. Review the matches that were triggered for the policy.

    2. You can investigate the match by clicking on a specific match to open the file drawer. In the drawer, you can see the other policies that this file matched.

## Validate your policy

1. To simulate an alert, go to your Box account and try to access a file in the folder **Customer data**.
2. Go to the policy report. A file policy match should appear shortly. 
3. You can click on the match to see which files were protected. The match itself will be masked to protect the sensitive data.

>[!NOTE]
>
> - Cloud App Security currently supports automatic application of Azure Information Protection labels on Box, GSuite, SharePoint and OneDrive for business.
> - When a document is labeled by using Cloud App Security, visual markings are not immediately applied but are applied when that document is opened in an Office app and the document is first saved. For more information, see [How to configure a label for visual markings for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-markings#when-visual-markings-are-applied).

## Next steps

[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
