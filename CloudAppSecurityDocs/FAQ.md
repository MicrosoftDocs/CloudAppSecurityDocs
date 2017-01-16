---
# required metadata

title: Frequently Asked Questions | Microsoft Docs
description: This article provides frequently asked questions and answers about Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/11/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 081c2cf4-2750-4546-9490-4b65e87ae48c


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Frequently asked questions

## What kind of permissions do I need to have in order to access Cloud App Security?

You have to be a Global admin, Compliance admin or Security admin in Azure Active Directory. It is not enough to have these roles in the Office 365 Security and Compliance Center.
To set a user as a Global admin, Compliance admin or Security admin in Azure Active Directory, run the following in Windows PowerShell:

        $cred = Get-Credential
        Connect-MsolService -credential $cred
        Add-MsolRoleMember -RoleName "Compliance Administrator" -RoleMemberEmailAddress "XX@XX.XX"
 OR
        Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress “XX@XX.XX”

## See also  
To learn how to use and set up policies to control cloud app use, see [Control cloud apps with policies](control-cloud-apps-with-policies.md).   
For technical support, go to the [Cloud App Security assisted support](http://support.microsoft.com/oas/default.aspx?prid=16031) page.   
Premier customers can also choose Cloud App Security directly from the [Premier Portal](https://premier.microsoft.com/).  
