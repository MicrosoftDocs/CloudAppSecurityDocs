---
# required metadata

title: How to find deprecated built-in reports in Cloud App Security | Microsoft Docs
description: This topic provides instructions for generating deprecated reports in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod:
ms.app: cloud-app-security
ms.technology:
ms.assetid: a9660e5b-d5bd-4a32-8cb9-0de70af6f1e9

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



# How to find built-in deprecating reports


In an ongoing effort to improve our Microsoft  Cloud App Security reporting, we are updating the functionality of built-in reports by embedding this experience in other parts of the portal.

This table helps you view the information that was provided by the deprecating reports by using other Cloud App Security functionality:

|Report type|Built-in report name|Description|New location of the data|
|----|----|----|----|----|
|Security|Activity|This enables you to view a list of the countries from which activity originated in your cloud apps, and different parameters representing the volume of activity from each country, such as the number of events, number of users, etc. It helps you get an overview of the geographic distribution of your users.|This information is available for specific apps, users, and IP addresses. For each app, click on the app. From there you can see the activity map with all locations. For each user, click on the user and then the user insight drawer. There you can see the recently used Locations, and the number of IP addresses and ISPs used. For each IP address, click on the specific IP address. In the IP address drawer you can see how many users and admins used it.|
|Security|Browse use|Browser-based attacks are among the most common attack vectors. Vendors invest enormous amounts of resources in securing browsing software, creating an effective update mechanism to disseminate updates to endpoints. Using deprecated browsers long after their update is due makes it an easy target for threat actors using available exploit kits. This enables you to get a list of the outdated browsers used in the last 7 days by users accessing your cloud apps. It also lets you know if the outdated browser use was performed by a robot.|Go to the **Activity log**, and open **Advanced filters**. Then set the filter for **User agent tag** equals **Outdated browser** and **Outdated operating system** to see a list of all outdated browsers and OS in use.|
|Security|IP addresses - privileged accounts|This lists IP addresses used by devices to perform administrative activities in the last 7 days, in your cloud environment protected by Cloud App Security. The date is based on audit logs accumulated by Cloud App Security. IP addresses are associated with a geographical location and with a source organization. This lets you identify suspicious IP addresses connecting to your protected apps. You may view the audit logs for each IP address by clicking on it.|Click on a specific user. Then, in the user insight drawer you can see the recently used Locations, and the number of IP addresses and ISPs used.|
|User management|Inactive accounts|Inactive accounts are accounts that have access to your cloud instance, yet they have not performed any events during the last 60 days. This suggests that these accounts are no longer active and should be suspended to prevent future access by threat actors or by leaving employees. Following this best-practice not only improves your security posture, but also reduces operational costs.|Go to the **Users and accounts** page, use the **Last seen** filter to generate a list of all users who have not performed any activity recently.|
|User management|Privileged users|This lists the users who have elevated privileges in corporate apps, such as administrators, in the last 7 days. Privileged accounts such as these are a preferred attack vector for threat actors since they may allow them to gain substantial access to corporate information and network configuration. If there are privileged accounts that were not used recently, it might indicate a lack of IT security awareness in enterprises, potentially paving the way for a wave of data breaches. You may further investigate the use of elevated user privileges through the Audit log, and consider revoking privileges when unnecessary.|Go to the **Users and accounts** page, use the **Groups** filter to generate a list of privileged users who belong to the Administrators group.|
|User management|Special privileged accounts|Salesforce has several types of privileged accounts, including Modify all data, View all data, and Manage all users. Because privileged accounts such as these are a preferred attack vector for threat actors since they may allow them to gain substantial access to corporate information and configurations, it is useful to view a list of privileged accounts.|Go to Salesforce. Click on the **Special privileged accounts** tab.|
|Data management|Data sharing overview|This lists the number of files stored in your cloud apps, divided according to access permissions. Sharing has been made easy with cloud apps because of the ease of access and ubiquity. A file that is not shared with anyone except its owner is referred to as a private file. If the file is shared, Cloud App Security differentiates between four types of states: <br> - A publicly shared (web) file is a file that can be accessed without any authentication, even through a search engine result.<br> - A publicly shared file is a file that can be accessed without any authentication, using a link.<br> - An externally shared file is a file that can be accessed by individuals outside the organization, after authenticating themselves to the cloud app.<br> - An internally shared file is a file that can be accessed by all or by some of your organization's users.|Go to **Files**. In the upper right hand corner, click the three dots and under **Data management reports**, select **Data sharing overview**.|
|Data management|Outbound sharing by domain|This lists the domains with which corporate files are shared by your employees. For each domain, the report details which corporate users are sharing files with that domain, which files are shared, and who are the collaborators files are shared with. It is advised that you manage the sharing with these domains via the Files tab in the app page of each relevant app.|Go to **Files**. In the upper right hand corner, click the three dots and under **Data management reports**, select **Outbound sharing by domain**.|
|Data management|Owners of shared files|This lists users who are sharing corporate files with the outside world. Externally shared files are shared with specific external collaborators. Publicly shared files are accessible to anyone on the Internet, via a private link, and can be found only by those who are explicitly exposed to the link. Publicly shared files (Internet) are accessible to anyone on the Internet even through a search engine result. If you find users that share an excessive number of files, it is advised that you investigate the nature of these excessive sharing permissions using the Files tab and contact these users to further understand their usage of external sharing.|Go to **Files**. In the upper right hand corner, click the three dots and under **Data management reports**, select **Owners of shared files**.|



  
## See Also 
[Control](control.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  