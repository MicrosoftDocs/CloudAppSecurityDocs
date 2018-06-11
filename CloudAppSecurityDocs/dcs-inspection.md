---
# required metadata

title: How Cloud App Security performs content inspection using Microsoft Data Classification Service| Microsoft Docs
description: This article describes the process Cloud App Security follows when performing DLP content inspection using Microsoft Data Classificatin Service. 
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/11/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: bf25d1e6-e5dc-449f-b50e-1cd4a21b6d3d

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



# Integration with Microsoft Data Classification

Enterprises in the cloud live in a dynamic and bustling world in which security
administrators monitor multiple screens across multiple systems to make sure
your users and assets are protected. In a modern, cloud environment like this,
Microsoft understands how important it is to make the most of your time and
thought investments and enable you to benefit from a more holistic,
cross-service paradigm.

You may have already invested a lot of time and research to determine which data can be shared and which data may be more sensitive. You may have different
classifications for different workloads or different sites. You may need to
create multiple custom sensitive types to account for the myriad of files and
file types you need to secure. And you don’t want to have to repeat this process again for each security service running on your cloud.

Microsoft Cloud App Security now enables you to utilize the Microsoft Data
Classification Service natively, to classify the files in your cloud apps.
Microsoft Data Classification Service provides a unified information protection
experience across Office 365, Azure Information Protection, and Microsoft
Cloud App Security, and allows you to extend your data classification efforts to the third-party cloud apps that are protected by Microsoft Cloud App Security, leveraging the decisions you already made across and even greater number of apps.

With no additional configuration required, when creating a data leak prevention
policy for your files in Microsoft Cloud App Security, you will automatically
have the option to set the **Inspection method** to use the **Microsoft Data
Classification Service**.

![data classification service setting](./media/dcs-enable.png)

To enable content inspection with Data Classification Services:

1. In the [file policy](data-protection-policies.md) page, under **Inspection method** select **Data Classification Service**.
2. Select whether the policy should apply when **any** or **all** of the criteria are met.
3. Choose your content inspection type by selecting the sensitive information types.
 ![data classification service setting](./media/dcs-sensitive-information-type.png)

5. You can use the [default sensitive information types](https://support.office.com/article/what-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b) as well as the [custom sensitive information types](https://support.office.com/article/create-a-custom-sensitive-information-type-82c382a5-b6db-44fd-995d-b333b3c7fc30) (which support complex patterns with Regex, keywords, and large dictionary) that you created in Office 365, and reuse them to define what happens to files
protected by Microsoft Cloud App Security.

6. Optionally, you can unmask the last four characters of a match. By default, matches are masked and shown in their context, and include the 40 characters before and after the match. If you select this checkbox, it will unmask the last four characters of the match itself.

7. You can also set alerts and governance actions for the policy. For more information, see [file policies](data-protection-policies.md) and [governance actions](governance-actions.md).

Setting these policies in Microsoft Cloud App Security enables you to easily
extend the strength of the Office 365 DLP capabilities to all your other
sanctioned cloud apps and protect the data stored in them with the full toolset
provided to you by Microsoft Cloud App Security – such as the ability to
[automatically apply Azure Information Protection classification labels](azip-integration.md) and the ability to control sharing permissions.



## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  