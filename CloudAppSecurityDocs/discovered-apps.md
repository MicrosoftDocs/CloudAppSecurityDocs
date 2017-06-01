---
# required metadata

title: Identifying risky discovered apps in Cloud App Security | Microsoft Docs
description: This topic describes the process for identifying and remediating risky cloud discovery apps in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/1/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 645fd8c7-06d0-4f93-a85c-2976e7b3766d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Working with discovered apps

## Identify risky apps
Your first important task when you see the results provided to you by Cloud App Security's Cloud Discovery, is to review which apps were discovered and determine if they are risky or not.

To do this, it's helpful to use the popular searches and the filters to review the apps that were discovered as being used in your environment.

### Discovered app filters

- **App tag**: select whether the app was sanctioned or unsactioned or not.
- **Apps and domains**: enables you to search for specific apps or apps used in specific domains 
- **Compliance risk factor**: lets you search for a specific compliance factor (CSA Star level, DMCA, FINRA, FISMA, etc.)
- **General risk factor**: lets you search for apps by Consumer popularity, Data center locale, Domain, Domain registration (before or after date), Founded during a specific year, Headquarters in a specific locale, Holding (private or public), Hosting company, Logon URL, Vendor
- **Risk score**: lets you filter apps by risk score so that you can focus on, for example, reviewing only very risky apps.
- **Security risk factor**: enables you to filter based on
- **Usage**: Lets you filter based on apps used by specific IP addresses or apps Last seen being used before a specific date (to enable you to weed out apps that are stale and no longer in use), apps with less than a specified amount of **Traffic**, apps with fewer than a specified amount of **Transactions**, apps with less than or more than a specified amount of data uploads, apps with more than or less than a specified amount of **Users**.


## The Cloud App Catalog
The Cloud App Catalog gives you a full picture of what Cloud Discovery knows how to identify. Cloud Discovery analyzes your traffic logs against Cloud App Security's cloud app catalog of over 14,000 cloud apps that are ranked and scored based on more than 50 attributes, to provide you with ongoing visibility into cloud use, Shadow IT, and the risk Shadow IT poses into your organization.
The **Cloud app catalog** rates risk for your cloud apps based on regulatory certification, industry standards, and best practices. Four complementary processes run in the Cloud app catalog to keep it up to date:
1.	Automated data extraction directly from the cloud app (for attributes such as SOC 2 compliance).
2.	Automated advanced data extraction for data by Cloud App Security's algorithms (for attributes such as HTTP security headers).
3.	Continuous analysis by the Cloud App Security cloud analyst team (for attributes such as encryption at rest).
4.	Customer-based revision requests, based on customer submission requests for changes to the Cloud app catalog. All requests are reviewed by our cloud analyst team and updated based on their findings.
  
## Cloud Discovery data anonymization

Cloud Discovery data anonymization enables you to protect user privacy. Once the data log is uploaded to the Cloud App Security portal, the log is sanitized and all username information is replaced with encrypted usernames. This way, all cloud activities are kept anonymous. For more information see [Cloud Discovery anonymization](cloud-discovery-anonymizer.md).

## Remediate

After you have reviewed the list of discovered apps in your environment, you can secure your environment against unwanted app use in the following ways.

**To generate a new block script:**


**To sanction/unsanction an app:**
You can unsanction a specific risky app by clicking the three dots at the end of the row and selecting **Unsanction**.
Unsanctioning an app doesn't block use, but enables you to more easily monitor its use with the Cloud Discovery filters. 
You can then notify users of the app that it has been unsanctioned and suggest an alternative, safe app for their use.

If you have a list of apps you want to sanction or unsanction, you can use the checkbox to select all the apps you want to manage, and then select the action.

**To create a new policy from search:**
After you have search results filtered for specific apps you want to apply specific actions to, you can create a new policy from your filtered search results.
At the top of the Discovered apps page, click the three dots and then select **Create new policy**. This will automatically open a new Discovery Policy template filtered using the filters currently applied.

## Suggest a change

If you find a new app in your environment that hasn't been scored by Cloud App Security, you can request a review of the app:

1. At the top of the Discovered apps page, click the three dots and then select **Suggest new app**. 

2. In the **Suggest new cloud app** popup, fill in details about the new app including the name and domain of the app. 

3. We recommend selecting the checkbox to enable Cloud App Security analysts to contact you in case additional information about the app is needed, and so that you can be updated when the analysis is complete.

## See also
 
[Create snapshot Cloud Discovery reports](create-snapshot-cloud-discovery-reports.md)

[Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md)

[Working with Cloud Discovery data](working-with-cloud-discovery-data.md)

