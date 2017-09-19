---
# required metadata

title: How to protect your data with Cloud App Security | Microsoft Docs
description: This topic describes the ways in which Cloud App Security enables you to protect your data and information in real time.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/19/2017
ms.topic: article
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

# Microsoft world-class data protection  

In a perfect world, all your employees understand the importance of information protection and work within your policies. But in a real world, a partner who works with accounting uploads a document to your Box repository, and a week later you realize that all your private information was leaked to the Internet. 

Cloud App Security helps you prevent this kind of disaster before it happens.

Cloud App Security identifies that there are public permissions on a document saved in your Box account, and uses the new Microsoft Classification Engine unified engine, the same engine you used to set up your Office 365 data leak prevention policies, to see that there is confidential information in the publicly shared document. Cloud App Security sends you an alert to let you know this occurred, and in addition, applies your Azure Information Protection confidential classification label to automatically provide added encryption to the file.

## One unified classification engine

Cloud App Security's full integration with the Microsoft Classification Engine (MCE) enables you to leverage of all the enterprise-ready, world-class data leak prevention technology built-into Microsoft's security products. Cloud App Security uses the Microsoft Classification Engine to scan your files for things like credit card numbers and identification numbers. You will be able to take advantage of the 82 data protection templates available for Office files, a list that is constantly growing as sensitive information types are constantly added. In addition, it provides you with the ability to configure one set of policies, on one engine, and get one unified set of results.

## Enhanced data-level encryption protection

Full integration with Azure Information Protection's native protection enables an added level of protection by automatically encrypting files in partnership with the app. For example, Office files are encrypted using Azure Information Protection and Office can read the encrypted file and apply the permissions and limitations. You can use labels to apply protection types that create custom permissions and limitations (for example, you can set a file so that it can be opened but while open, you can't present, print, forward, or edit the document). 

This strong level of protection travels with the file - if you send the file, copy it, store it in your online storage app, the file is still protected. If one of your employees lost a thumbdrive with the file on it, the file will be locked and if someone tries to open it, the file owner will receive an alert. With Cloud App Security, you can apply native protection automatically. For example, all files that have credit card numbers or were uploaded by the finance department and are shared externally, can be set to be automatically protected with a classification label. 

## Third-party DLP integration

You may already have a DLP solution, and what's more important, you may have already taken the time to create and fine-tune policies in that DLP. To enable you to leverage those solutions and all the time you spent on them, Cloud App Security can connect to your existing DLP and allow or block file download. 

## THE THREAT
A user in your organization saves confidential customer information files to Box and sets it to be shared with everyone. The user doesn't realize that in addition to their immediate team, the entire support staff has access to that Box account, including vendors, partners and visitors who occasionally stop into the office. Any person with access to your organization's Box account now has access to that information. Not only can that be dangerous for your organization, it can be against PII regulations in many countries, causing potential legal issues.

## THE SOLUTION
Use Azure Information Protection with Cloud App Security to embed classification and protection information for persistent protection that follows your data—ensuring it remains protected regardless of where it’s stored or who it’s shared with. This also enables you to share data safely with coworkers as well as your customers and partners. Define who can access data and what they can do with it—such as allowing to view and edit files but not print or forward. In addition, remove collaborators and remove sharing abilities.

## Prerequisites

- Enable Cloud App Security and Azure Information Protection for your tenant
- [Connect Box](connect-box-to-microsoft-cloud-app-security.md) to Cloud App Security.

## Setting up data protection

1. Start protecting the data you store in Box by setting up a policy that will encrypt any sensitive data stored in Box:

    1. On the **Control** tab, click [**Policies**](control-cloud-apps-with-policies.md). 
    
    2. Click **Create policy** and select **File policy**.
    
    3. Call the policy Box data protection and under **Create a filter for the files this policy will act on**, target your proprietary and sensitive data.<br></br>
    For example, select **Parent folder** equals **Customer data** and select **Owner** equals and select the finance team.
    
    4. Under **Governance**, open the **Box** section and select **Protect**.
    
    5. Because [Cloud App Security is integrated with Azure Information Protection](azip-integration.md), you can select from your existing list of classification labels to be used to protect the data.
    
    6. To work with your MCE policies,, under **Content inspection method**, select **Microsoft Classification Engine**. Then you select one or more sensitive file types and then choose **Any** of these or **All of these**.
    
    7. Click **Create**. 
   
     
2. Investigating your matches
    
    1. In the **Policies** page, click on the policy name to go to the **Policy report** and review the matches that were triggered for the policy.

    2. You can investigate the match by clicking on a specific match to open the file drawer. In the drawer, you can see the other policies that this file matched. 
     
## Validating your policy

1. To simulate an alert, go to your Box account and attempt to access a file in the folder **Customer data**.
3. Go to the policy report. A file policy match should appear shortly. 
4. You can click on the match to see which files were protected. The match itself will be masked to protect the sensitive data. 



 ## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  