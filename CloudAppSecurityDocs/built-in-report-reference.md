---
# required metadata

title: Understand the fields in the built-in reports in Cloud App Security | Microsoft Docs
description: This topic provides a list of built-in reports and their uses.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/23/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 588b3639-f748-45a6-bc4b-a6ee47c1865e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Built-in report reference
It is recommended that you create custom reports using built-in reports as a starting place, sort of like a template on which to base your custom reports. The following table provides a list of built-in reports and the types of events you might want to use them to monitor.  
  
## Built-in report list  
  
|Report type|Built-in report name|Description|  
|-----------------|---------------------------|-----------------|  
|Security|Activity by location|This report lists the countries from which activity originated in your cloud apps, and different parameters representing the volume of activity from each country, such as the number of events, number of users, etc. Use it to get an overview of the geographic distribution of your users.|  
|Security|Browser use|Browse- based attacks are among the most common attack vectors. Vendors invest enormous resources in securing browsing software, creating an effective update mechanism to disseminate updates to endpoints. Using deprecated browsers long after their update is due makes it an easy target for threat actors using available exploit kits. This report lists the browsers used in the last 30 days by users accessing your cloud services.|  
|Security|IP addresses - privileged accounts|This report lists IP addresses used by devices to perform administrative activities in the last 7 days, in your cloud environment protected by Cloud App Security. The report is based on audit logs accumulated by Cloud App Security. IP addresses are usually associated with a geographical location and with a source organization. Use this report to identify suspicious IP addresses connecting to your protected services. You may view the audit logs for each IP address by clicking on it.|  
|User management|Inactive accounts|Inactive accounts are accounts that have access to your cloud instance, yet they have not performed any events during the last 60 days. This suggests that these accounts are no longer active and should be suspended to prevent future access by threat actors or by leaving employees. Following this best-practice not only improves your security posture, but also reduces operational costs.|  
|User management|Privileged users|This report lists the users who have elevated privileges in corporate services, such as administrators, in the last 7 days. Privileged accounts such as these are a preferred attack vector for threat actors since they may allow them to gain substantial access to corporate information and network configuration. If there are privileged accounts that were not used recently, it might indicate a lack of IT security awareness in enterprises, potentially paving the way for a wave of data breaches. You may further investigate the use of elevated user privileges through the Audit Log, and consider revoking privileges when unnecessary.|  
|User management|Special privileged accounts|Salesforce has several types of privileged accounts, including Modify all data, View all data and Manage all users. Privileged accounts such as these are a preferred attack vector for threat actors since they may allow them to gain substantial access to corporate information and configurations.|  
|Data management|Data sharing overview|This report lists the number of files stored in your cloud services, divided according to access permissions. Sharing has been made very easy with cloud services because of the ease of access and ubiquity.<br /><br /> A file that is not shared with anyone except its owner is referred to as a private file. If the file is shared, Cloud App Security differentiates between four types of states:<br /><br /> A publicly shared (web) file is a file that can be accessed without any authentication, even through a search engine result.<br /><br /> A publicly shared file is a file that can be accessed without any authentication, using a link.<br /><br /> An externally shared file is a file that can be accessed by individuals outside the organization, after authenticating themselves to the cloud service.<br /><br /> An internally shared file is a file that can be accessed by all or by some of your organization's users.|  
|Data management|Outbound sharing by domain|This report lists the domains with which corporate files are shared by your employees. For each domain the report details which corporate users are sharing files with that domain, which files are shared, and who are the collaborators files are shared with. It is advised that you manage the sharing with these domains via the Files tab in the service page of each relevant service.|  
|Data management|Owners of shared files|This report lists users who are sharing corporate files with the outside world. Externally shared files are shared with specific external collaborators. Publicly shared files are accessible to anyone on the internet, via a private link, and can be found only by those who are explicitly exposed to the link. Publicly shared files (Internet) are accessible to anyone on the internet even through a search engine result.  If you find users that share an excessive amount of files, it is advised that you investigate the nature of these excessive sharing permissions using the Files tab and contact these users to further understand their usage of external sharing.|  
  
## See Also  
[Control](control.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  