---
# required metadata

title: Protect your data with Cloud App Security and Azure Information Protection | Microsoft Docs
description: This topic describes the process for setting up near real time data protection for sensitive data in your organization.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/29/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: f3d01d43-0018-40e5-b7c7-8384d37bad52

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protecting your organization's data

Properly training all your employees in information protection can be expensive and sometimes impossible. For companies that have a lot of vendors and partners with access to SharePoint sites and Dropbox locations, it's hard to make sure that your data is secure at all times. That's where Cloud App Security's integration with Azure Information Protection comes in. This better-together cloud app super team enables you to protect your data in near real-time. 

## THE THREAT
A user in your organization saves confidential customer information files to Box. The user doesn't realize that in addition to their immediate team, the entire support staff has access to that Box account, including vendors, partners and visitors who occasionally stop into the office. Any person with access to your organization's Box account now has access to that information. Not only can that be dangerous for your organization, it can be against PII regulations in many countries, causing potential legal issues.

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
    4. Click **Create**. 
   
     
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
  
  