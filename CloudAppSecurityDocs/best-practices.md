---
# required metadata
title: Best practices for protecting your organization - Cloud App Security
description: This article provides a set of best practices for protecting your organization.
author: ShlomoSagir-MS
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: conceptual
ms.date: 9/8/2019

# optional metadata
#ROBOTS: NOINDEX # Used to prevent showing on search pages
#services: na
#ms.subservice: na
ms.collection: M365-security-compliance
---

# Cloud App Security best practices

*Applies to: Microsoft Cloud App Security*

This article provides best practices for protecting your organization by using Microsoft Cloud App Security. These best practices come from our experience with Cloud App Security and the experiences of customers like you.

The best practices discussed in this article include:

- Discover and assess cloud apps

## Discover and assess cloud apps

Integrating Cloud App Security with Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) gives you the ability to use Cloud Discovery beyond your corporate network or secure web gateways. With the combined user and machine information, you can identify risky users or machines, see what apps they are using, and investigate further in the Microsoft Defender ATP portal.

**Best practice**: Enable Shadow IT Discovery using Microsoft Defender ATP<br>
**Detail**: Cloud Discovery analyzes traffic logs collected by Microsoft Defender ATP and assesses identified apps against the cloud app catalog to provide compliance and security information. By configuring Cloud Discovery, you gain visibility into cloud use, Shadow IT, and continuous monitoring of the unsanctioned apps being used by your users.<br>
**For more information**:

- [Microsoft Defender ATP integration with Cloud App Security](wdatp-integration.md)
- [Set up Cloud Discovery](set-up-cloud-discovery.md)
- [Discover and manage shadow IT in your network](tutorial-shadow-it.md)

**Best practice**: Configure App Discovery policies to proactively identify risky, non-complaint and trending apps<br>
**Details**: App discovery policies make it easier to track of the significant discovered applications in your organization to help you manage these applications efficiently. Create Cloud Discovery policies to receive alerts when discovering newly discovered apps that are identified as either risky, non-compliant, trending or high-volume.<br>
**For more information**:

- [Cloud Discovery policies](cloud-discovery-policies.md)
- [Cloud Discovery anomaly detection policy](cloud-discovery-anomaly-detection-policy.md)
- [Get instantaneous behavioral analytics and anomaly detection](anomaly-detection-policy.md)
