---
# required metadata

title: Frequently Asked Questions - Cloud App Security | Microsoft Docs
description: This article provides frequently asked questions and answers about Cloud App Security.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Frequently asked questions

*Applies to: Microsoft Cloud App Security*

This article provides frequently asked questions and answers about Cloud App Security.

## What kind of permissions do I need to access Cloud App Security?

You have to be a Global admin, Compliance admin, or Security admin in Azure Active Directory. It isn't enough to just have these roles in the Office 365 Security and Compliance Center. You can use PowerShell to set a user as a Global admin, Compliance admin, or Security admin in Azure Active Directory. Run the following cmdlets below:

```powershell

 $cred = Get-Credential
 Connect-MsolService -credential $cred
 Add-MsolRoleMember -RoleName "Compliance Administrator" -RoleMemberEmailAddress "XX@XX.XX"
```

 OR

```powershell
 Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress “XX@XX.XX”
```

## Next steps

To learn how to set up and use policies for controlling cloud app use, see [Control cloud apps with policies](control-cloud-apps-with-policies.md).

[!INCLUDE [Open support ticket](includes/support.md)]
