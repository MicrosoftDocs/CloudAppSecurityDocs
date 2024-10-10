---  
title: "Caaac app onboarding"  
description:  
author:  
ms.author: adipavekatz  
manager:  
ms.date: 10/10/2024  
ms.topic:  
ms.service: defender-xdr  
ms.subservice:  
ms.localizationpriority:  
ms.collection:  
ms.custom: QuickDraft  
ms.reviewer: adipavekatz  
search.appverid: MET150  
f1.keywords:  
audience:  
ai-usage:  
- ai-assisted  
---  

**Customer Intent for this Article:** Understand how to automatically onboard applications into Microsoft Defender XDR using Entra ID and configure Conditional Access App Control.

## Overview

All SaaS applications that exist in the Entra ID catalog will be available automatically in the policy app filter. The following image shows the high-level process for configuring and implementing Conditional Access app control:

## Prerequisites

- Your organization must have the following licenses to use Conditional Access App Control:
  - Microsoft Defender for Cloud Apps
- Apps must be configured with single sign-on in Entra ID

Fully performing and testing the procedures in this article requires that you have a session or access policy configured. For more information, see:

- [Create Microsoft Defender for Cloud Apps access policies](https://example.com)
- [Create Microsoft Defender for Cloud Apps session policies](https://example.com)

## Supported Apps

All SaaS apps listed in the Entra ID catalog will be available for filtering within the Microsoft Defender for Cloud Apps session and access policies. Each app chosen in the filter will automatically be onboarded into the system and will be controlled.

If an application is not listed, you have the option to manually onboard it as outlined in the provided instructions.

**Note:** Dependency on Entra ID Conditional Access policy:

All apps listed in the Entra ID catalog will be available for filtering within Microsoft Defender for Cloud Apps session and access policies. However, only those applications that are included in Entra ID's conditional policy with Microsoft Defender for Cloud Apps permissions will be actively managed within access or session policies.

When creating a policy, if the relevant Entra ID's conditional policy is missing, an alert will appear, both during the policy creation process and upon saving the policy.

**Note:** To ensure that this policy runs as expected, we recommend checking the Entra Conditional Access policies created in Entra ID. You can see the full Entra Conditional Access policies list in a banner on the create policy page.

## Conditional Access App Control Configuration Page

Admins will be able to control app configurations such as:

1.  **Status:** App status - Disable or Enable
2.  **Policies:** Does at least one inline policy connect
3.  **IDP:** Onboarded app via IDP via Entra or Non-MS IDP
4.  **Edit app:** Edit app configuration such as adding domains or disabling the app.

All apps that automatically onboarded will be set to "enabled" by default. Following the initial login by a user, administrators will have the ability to view the application under **Settings** \> **Connected apps** \> **Conditional Access App Control apps**

## Common App Misconfigurations

1.  Second sign-in (also known as 'second login')
2.  Missing domains