---
# required metadata

title: Add custom apps to Cloud Discovery in Cloud App Security | Microsoft Docs
description: This topic provides information about how to add custom apps to Cloud Discovery in Cloud App Security to monitor Shadow IT.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/27/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 98b0d841-b33d-4ae9-b48b-d9ee77785eaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Add custom apps to Cloud Discovery
    
Cloud Discovery analyzes your traffic logs against Microsoft Cloud App Security's cloud app catalog of over 15,000 cloud apps. The catalog contains publicly available cloud apps only, for which Cloud App Security provides visibility and risk information.

In order to gain visibility into cloud apps that are excluded from the Cloud App Catalog,  Cloud App Security enables you to discover use of custom cloud apps (LOB apps) that were developed or assigned specifically for your organization.

By adding a new custom cloud app, Cloud App Security is able to match uploaded firewall and proxy traffic log messages to the app and then provide you with visibility into the use of this app across your organization in the Cloud Discovery pages, such as how many users use the app, how many unique source IP addresses use it, and how much traffic is transmitted to and from the app. 

To add a new custom cloud app:

1. In the Cloud App Security portal, click on **Discover** and then **Cloud Discovery dashboard**. 
  
   ![cloud discovery dashboard menu](./media/cloud-discovery-dashboard-menu.png)

2. In the top right corner, click the 3 dots and then select **Add new custom app**. 

   ![add custom app menu](./media/add-custom-app-menu.png)

3. Fill in the fields to define the new app record which will be listed in the Cloud App Catalog and in Cloud Discovery after it is discovered in your firewall logs.

   ![custom app](./media/add-custom-app.png)

4. Under **Domains**, fill in the unique domains that are used when accessing the custom app. These domains are used to match traffic log messages to this app. If the data source you are using doesn’t contain app URL information, make sure you fill in the **IPv4** and **IPv6** address fields.
5. It is recommended to add notes that will enable you to track changes for this record.

After the app is created, it is available for you in the Cloud App Catalog.

At any time, you can click the 3 dots at the end of the row to edit or delete a custom app.

>[!NOTE]
> - Custom apps are automatically tagged with the **Custom app** tag after you add them. This app tag cannot be removed.
In order to view all your custom apps, set the **App tag** filter to be equal to ‘Custom app’. 
> -	By default, custom apps have a risk score of 10, but you can use the **Override app score** action to change it at any time.

  
## See Also  
[User activity policies](user-activity-policies.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  