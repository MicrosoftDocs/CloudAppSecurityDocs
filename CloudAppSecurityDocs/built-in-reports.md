---
# required metadata

title: How to generate reports in Microsoft Cloud App Security | Microsoft Docs
description: This topic provides instructions for generating data management reports in Microsoft Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/10/2018
ms.topic: article
ms.prod:
ms.app: cloud-app-security
ms.technology:
ms.assetid: 0dcc3c35-f787-4822-84c6-d4dff897dd6c

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



# Generate data management reports

Microsoft Cloud App Security enables you to generate reports that provide you with an overview of files in your cloud apps.

To generate these reports

1. Go to **Files**. 
2. In the upper right-hand corner, click the three dots and under **Data management reports**, select one of the following reports.

   ![reports](./media/reports.png)
I
## Data sharing overview 

This lists the number of files stored in your cloud apps, divided according to access permissions. Sharing has been made easy with cloud apps because of the ease of access and ubiquity. A file that is not shared with anyone except its owner is referred to as a private file. If the file is shared, Cloud App Security differentiates between four types of states: <br> - A publicly shared (web) file is a file that can be accessed without any authentication, even through a search engine result.<br> - A publicly shared file is a file that can be accessed without any authentication, using a link.<br> - An externally shared file is a file that can be accessed by individuals outside the organization, after authenticating themselves to the cloud app.<br> - An internally shared file is a file that can be accessed by all or some users in your organization.

## Outbound sharing by domain

This lists the domains with which corporate files are shared by your employees. For each domain, the report details, which corporate users are sharing files with that domain, which files are shared, and who are the collaborators files are shared with. It is advised that you manage the sharing with these domains via the Files tab in the app page of each relevant app.

## Owners of shared files

This lists users who are sharing corporate files with the outside world. Externally shared files are shared with specific external collaborators. Publicly shared files are accessible to anyone on the Internet, via a private link, and can be found only by people who are explicitly exposed to the link. Publicly shared files (Internet) are accessible to anyone on the Internet even through a search engine result. If you find users that share an excessive number of files, it is advised that you investigate the nature of these excessive sharing permissions using the Files tab and contact these users to further understand their usage of external sharing.


  
## See Also 
[Control](control.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  