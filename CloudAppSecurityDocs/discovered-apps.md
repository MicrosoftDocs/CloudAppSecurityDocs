---
# required metadata

title: Working with Cloud Discovery in Cloud App Security | Microsoft Docs
description: This topic describes the process for working with discovered apps in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/21/2017
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
use recomended queries, list filters

## Suggest a change


## The Cloud App Catalog
Cloud Discovery analyzes your traffic logs against Cloud App Security's cloud app catalog of over 14,000 cloud apps that are ranked and scored based on more than 50 attributes, to provide you with ongoing visibility into cloud use, Shadow IT, and the risk Shadow IT poses into your organization.
The **Cloud app catalog** rates risk for your cloud apps based on regulatory certification, industry standards, and best practices. Four complementary processes run in the Cloud app catalog to keep it up to date:
1.	Automated data extraction directly from the cloud app (for attributes such as SOC 2 compliance).
2.	Automated advanced data extraction for data by Cloud App Security's algorithms (for attributes such as HTTP security headers).
3.	Continuous analysis by the Cloud App Security cloud analyst team (for attributes such as encryption at rest).
4.	Customer-based revision requests, based on customer submission requests for changes to the Cloud app catalog. All requests are reviewed by our cloud analyst team and updated based on their findings.
  
## Cloud Discovery data anonymization

Cloud Discovery data anonymization enables you to protect user privacy. Once the data log is uploaded to the Cloud App Security portal, the log is sanitized and all username information is replaced with encrypted usernames. This way, all cloud activities are kept anonymous. For more information see [Cloud Discovery anonymization](cloud-discovery-anonymizer.md).

##Remediate
sanction/unsanction
bulk actions
new policy from search

## See also
 
[Create snapshot Cloud Discovery reports](create-snapshot-cloud-discovery-reports.md)

[Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md)

[Working with Cloud Discovery data](working-with-cloud-discovery-data.md)

