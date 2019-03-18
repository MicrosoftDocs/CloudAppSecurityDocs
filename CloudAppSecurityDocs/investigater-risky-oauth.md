---
# required metadata

title: Investigate risky OAuth apps - Cloud App Security | Microsoft Docs
description: This article provides information on how to investigate risky OAuth apps in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 3/17/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 4118681e-362f-4b10-aa08-39691aa7800a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Investigate risky OAuth apps

*Applies to: Microsoft Cloud App Security*

OAuth is an open standard for token-based authentication and authorization. OAuth enables a user's account information to be used by third-party services, without exposing the user's password. OAuth acts as an intermediary on behalf of the user, providing the service with an access token that authorizes specific account information to be shared.

Many third-party apps that might be installed by business users in your organization, request permission to access user information and data and sign in on behalf of the user in other cloud apps. When users install these apps, they often click **accept** without closely reviewing the details in the prompt, including granting permissions to the app.

Accepting third-party app permissions is a potential security risk to your organization, therefore, Microsoft Cloud App Security provides you with the ability to investigate and monitor the app permissions your users granted. This article is dedicated to helping you investigate the OAuth apps in your organization, and focus on the apps that are more likely to be suspicious. 

Our recommended approach is to investigate the apps by using the abilities and information provided in the Cloud App Security portal to filter out apps with a low chance of being risky, and focus on the suspicious apps. 

## How to investigate 

1.	Out of all the connected OAuth apps query using the filters in the portal. Recommended filters and queries are: 
    1. Permission level high and community use not common. Using this filter would help you focus on app with a high-risk potential, in which the user is likely missed understood the risk. 
    2. Specific risky permissions related to a specific type of apps (for example, apps with full access to all mailboxes). Using this filter would help you investigate in a specific context, and by that find apps seem legit but contains irrelevant permissions. Those apps are more likely to be malicious. 
    3. Apps authorized by external users. Using this filter would help you to find apps that might not be inline with your company’s security standards. 
2.	Focus on following apps, which might be suspicions: 
    1. Apps with a low number of “Authorized by”. Focusing on those apps, might help you find malicious apps that were authorized by a compromised user. 
    2. Apps with permissions that don’t suit the app’s purpose (for example, a clock app with full access to all mailboxes). Focusing on those apps might help you find apps that seems legitimate but are actually malicious. 
    3. Apps with suspicious name, publisher or website. Focusing on those apps might help you to quickly find suspicions apps. 
    4. Apps with old “last authorized”. Focusing on those apps might help you find apps that are not longer required. 
3. Use the related activities link and view in the activity log page activities performed be the app. Please note that this automatically generates a filter for activities which the user equals to the app’s name. However, some apps might perform activities as one of the users. Those events would be available in the activity log but might be filtered out. 
4. If an app seems suspicions, it is recommended to check the app’s name and publisher in the different app stores. Focus on following apps, which might be suspicions: 
    1. App with a low number of downloads.
    2. App with a low score or bad comments.
    3. App with a suspicious publisher or website.
    4. App with an old date of last update, might indicate on an app that is no longer supported. 
    5. Apps that don’t suit their permissions, might indicate that this app is malicious. 
5. If the app is still suspicious you can search the app name publisher and URL online. 

## Example 

Choose the “OAuth apps” option under the investigation icon
 
Use the filter options to filter the apps (equivalent to step 1)
 

Investigate a suspicious app using the available information in the portal (equivalent to step 2)
 

Use the activity log (equivalent to step 3)
 

References 
https://searchmicroservices.techtarget.com/definition/OAuth
https://docs.microsoft.com/cloud-app-security/manage-app-permissions


 
## Next steps
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md) 

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/) 
 
