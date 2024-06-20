---
title:  Microsoft Defender for Cloud Apps – privacy
description: Learn about how Microsoft Defender for Cloud Apps manages user privacy.
ms.date: 06/19/2024
ms.topic: concept-article
---
# Privacy with Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps is a critical component of the Microsoft cloud security stack, which helps you stay in control over your cloud applications with comprehensive visibility, auditing, and granular controls over your sensitive data.

This article provides an overview of the data security and privacy practices for Microsoft Defender for Cloud Apps.

## Data collected by Defender for Cloud Apps

Microsoft Defender for Cloud Apps collects information from your configured cloud apps and data sources. Information collected from those sources includes:

- Network data
- OAuth app configuration and usage
- Audits on cloud app usage by users and other apps
- File metadata and content
- System settings and policies
- User and group configurations

## Data storage location

Defender for Cloud Apps operates in the Microsoft Azure data centers in the following geographical regions: 

|Customer provisioning location  |Data storage location  |
|---------|---------|
|**Customers whose tenants are provisioned in the United States**     |  United States       |
|**Customers whose tenants are provisioned in the European Union or the United Kingdom**     |    Either the European Union and/or the United Kingdom      |
|**Customers whose tenants are provisioned in the Asia Pacific**     |   Either Asia Pacific and/or the United States      |
|**Customers whose tenants are provisioned in Canada**     |  Canada and/or the United States       |
|**Customers whose tenants are provisioned in India**     |   Either India and/or the United States      |
|**Customers whose tenants are provisioned in any other region**     |     The United States and/or a data center in the region that's nearest to the location of where the customer's Microsoft Entra tenant has been provisioned    |

Customer data collected by Defender for Cloud Apps is either stored in your tenant location, as described in the previous table, or in the geographic location of another online service that Defender for Cloud Apps shares data with, as defined by the data storage rules of that online service.

If Defender for Cloud Apps data is stored in your tenant location, your tenant isn't movable after having been created. To view your Defender for Cloud Apps tenant location in the Microsoft Defender portal, go to **Settings > Cloud Apps > About > Region**.
 
## Data retention

Data from Microsoft Defender for Cloud Apps is retained for up to 180 days, and is visible across the portal.  

Your data is kept and is available to you while the license is under grace period or suspended mode. At the end of this period, that data is erased from Microsoft's systems to make it unrecoverable, no later than 180 days from contract termination or expiration.

## Data sharing for Microsoft Defender for Cloud Apps

Defender for Cloud Apps shares data, including customer data, among the following Microsoft products also licensed by the customer:

- Microsoft Defender XDR
- Microsoft Defender for Cloud
- Microsoft Sentinel
- Microsoft Defender for Endpoint
- Microsoft Security Exposure Management (Preview)
- Microsoft Purview
- Microsoft Entra ID Protection

## Related content

For more information, see the [Microsoft Service Trust portal](https://www.microsoft.com/en-us/trust-center/product-overview).