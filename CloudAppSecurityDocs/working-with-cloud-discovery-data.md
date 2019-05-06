---
# required metadata

title: Use Cloud Discovery data to detect risky behavior - Cloud App Security | Microsoft Docs
description: This topic provides instructions for how to work with Cloud Discovery data, including working with the app risk score.
keywords:
author: rkarlin
ms.author: rkarlin
manager: angrobe
ms.date: 05/06/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: cf94b290-b7ef-4fee-854e-c8ff8d11dea9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Working with discovery data

*Applies to: Microsoft Cloud App Security*

The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization. It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, the risk levels of apps in your organization. It also shows you who your top app users are and provides an App Headquarter location map. The Cloud Discovery Dashboard has many options for filtering the data. Filtering allows you to generate specific views depending on what you're most interested in using easy-to-understand graphics to give you the full picture at a glance.

![cloud discovery dashboard](./media/cloud-discovery-dashboard.png)

## Review the Cloud Discovery Dashboard

The first thing you should do to get a general picture of your Cloud Discovery apps is review the following information in the Cloud Discovery Dashboard:
 
1. First look at the overall cloud app use in your organization in the **High-level usage overview**.

2. Then, dive one level deeper to see which are the **top categories** used in your org for each of the different use parameters. You can see how much of this usage is by Sanction apps.

3. Go even deeper and see all the apps in a specific category in the **Discovered apps** tab.

4. You can see the **top users and source IP addresses** to identify which users are the most dominant users of cloud apps in your organization.
5. Check how the discovered apps spread according to geographic location (according to their HQ) in the **App Headquarters map**.

6. Finally, don’t forget to review the risk score of the discovered app in the **App risk overview**. Check the **discovery alerts status** to see how many open alerts should you investigate.

## Exclude entities

If you have system users, IP addresses, or machines that are noisy but uninteresting or apps that aren't relevant, you may want to exclude their data from the Cloud Discovery data that is analyzed. For example, you might want to exclude all information originating from 127.0.0.1 or local host.  
  
To create an exclusion:  
  
1. In the portal, under the settings icon, select **Cloud Discovery settings**.  
2. Click the **Exclude entities** tab.  
3. Choose either the **Excluded users**, **Excluded IP addresses**, or **Excluded machines** tab and click the + button to add your exclusion.
4. Add a user alias, IP address, or machine name. We recommend adding information about why the exclusion was made.
  
     ![exclude user](./media/exclude-user.png "exclude user")  

## Manage continuous reports

Custom continuous reports provide you more granularity when monitoring your organization's Cloud Discovery log data. By creating custom reports, it's possible to filter on specific geographic locations, networks and sites, or organizational units. By default, only the following reports appear in your Cloud Discovery report selector:  
  
- The **Global report** consolidates all the information in the portal from all the data sources you included in your logs.  The global report doesn’t include data from Microsoft Defender ATP.
  
- The **Data source specific report** displays only information from a specific data source.  
  
To create a new continuous report:  
  
1. In the portal, under the settings icon, select **Cloud Discovery settings**.  
  
2. Click the **Continuous report** tab.  
  
3. Click the **Create report** button.  
  
4. Enter a report name.  
  
5. Select the data sources you want to include (all or specific).  
  
6. Set the filters you want on the data. These filters can be **User groups**, **IP address tags**, or **IP address ranges**. For more information on working with IP address tags and IP address ranges, see [Organize the data according to your needs](ip-tags.md).  
  
    ![create custom continuous report](./media/create-custom-continuous-report.png) 

> [!NOTE]
> All custom reports are limited to a maximum of 1 GB of uncompressed data. If there is more than 1 GB of data, the first 1 GB of data will be exported into the report.

## Deleting Cloud Discovery data

There are a number of reasons why you may want to delete your Cloud Discovery data. We recommend deleting it in the following cases:  
  
- If you manually uploaded log files and a long time passed before you updated the system with new log files and you don't want old data affecting your results.  
  
- When you set a new custom data view, it will apply only to new data from that point forward. So, you may want to erase old data and then upload your log files again to enable the custom data view to pick up events in the log file data.  
  
- If many users or IP addresses recently started working again after being offline for some time, their activity will be identified as anomalous and may give you false positive violations.  
  
To delete Cloud Discovery data:  
  
1. In the portal, under the settings icon, select **Cloud Discovery settings**.  
  
2. Click the **Delete data** tab.  
  
    It's important to be sure you want to delete data before continuing - it can't be undone and it deletes **all** Cloud Discovery data in the system.  
  
3. Click the **Delete** button.  
  
    ![delete data](./media/delete-data.png "delete data")  
  
   > [!NOTE]  
   >  The deletion process takes a few minutes and is not immediate.


 
## Next steps

[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
