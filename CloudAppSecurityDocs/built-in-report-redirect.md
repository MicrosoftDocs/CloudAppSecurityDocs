---
# required metadata

title: How to find deprecated built-in reports in Cloud App Security | Microsoft Docs
description: This topic provides instructions for generating deprecated reports in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/17/2018
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

# How to find built-in deprecated reports


In an ongoing effort to improve our Cloud App Security reporting, we are updating the functionality of built-in reports by embedding this experience in other parts of the portal.

This table helps you recreate the deprecating reports by using other Cloud App Security functionality:

|Report type|Built-in report name|Description|Old location of the data|New location of the data|
|----|----|----|----|----|
|Security|Activity|This report lists the countries from which activity originated in your cloud apps, and different parameters representing the volume of activity from each country, such as the number of events, number of users, etc. Use it to get an overview of the geographic distribution of your users.||Per each App you can see the activity map with all locations. For each user, in the user insight drawer you can see the recently used Locations, and the number of IPs and ISPs used. For each IP, in the IP address drawer you can see how many users and Admins used it.|
|Security|Browse Use|Browser-based attacks are among the most common attack vectors. Vendors invest enormous amounts of resources in securing browsing software, creating an effective update mechanism to disseminate updates to endpoints. Using deprecated browsers long after their update is due makes it an easy target for threat actors using available exploit kits. This report lists the outdated browsers used in the last 7 days by users accessing your cloud apps. The report also lets you know if the outdated browser use was performed by a robot.||In the Activity Log, you can see a report of all outdated browsers and OS in use.|
|Security|IP addresses - privileged accounts|For each user, in the user insight drawer you can see the recently used Locations, and the number of IPs and ISPs used.|For each user, in the user insight drawer you can see the recently used Locations, and the number of IPs and ISPs used.|For each user, in the user insight drawer you can see the recently used Locations, and the number of IPs and ISPs used.|
|User Management|Inactive accounts|In the Accounts page, you can see a report of all users that did not perform any activity in the last X days.|In the Accounts page, you can see a report of all users that did not perform any activity in the last X days.|In the Accounts page, you can see a report of all users that did not perform any activity in the last X days.|
|User Management|Privileged users|In the Accounts page, you can see a report of privileged users that belong to the Administrators group.|In the Accounts page, you can see a report of privileged users that belong to the Administrators group.|In the Accounts page, you can see a report of privileged users that belong to the Administrators group.|
|User Management|Special privileged accounts|Will be kept as is but moved to a different page in the portal.|Will be kept as is but moved to a different page in the portal.|Will be kept as is but moved to a different page in the portal.|
|Data Management|Data sharing overview|For each App you can see the sharing overview in the Insights tab.|For each App you can see the sharing overview in the Insights tab.|For each App you can see the sharing overview in the Insights tab.|
|Data Management|Outbound sharing by domain|Will be kept as is but moved to a different page in the portal.|Will be kept as is but moved to a different page in the portal.|Will be kept as is but moved to a different page in the portal.|
|Data Management|Owners of shared files|Will be kept as is but moved to a different page in the portal.|Will be kept as is but moved to a different page in the portal.|Will be kept as is but moved to a different page in the portal.|



  
## See Also 
[Built-in reports](built-in-report-reference.md) 
[Control](control.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  