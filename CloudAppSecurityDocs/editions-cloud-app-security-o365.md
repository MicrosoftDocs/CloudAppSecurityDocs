---
title: Differences between Defender for Cloud Apps and Microsoft 365 Cloud App Security
description: This article describes the differences between Defender for Cloud Apps and Microsoft 365 Cloud App Security.
ms.date: 01/29/2023
ms.topic: overview
---
# What are the differences between Microsoft Defender for Cloud Apps and Microsoft 365 Cloud App Security?

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article describes the differences between Defender for Cloud Apps and Microsoft 365 Cloud App Security.

For information about licensing, see the [Microsoft 365 licensing datasheet](https://aka.ms/M365EnterprisePlans).

## Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps is a comprehensive cross-SaaS solution bringing deep visibility, strong data controls, and enhanced threat protection to your cloud apps. With this service, you can gain visibility into Shadow IT by discovering cloud apps in use. You can control and protect data in the apps once you sanction them to the service.

## Microsoft 365 Cloud App Security

Microsoft 365 Cloud App Security is a subset of Microsoft Defender for Cloud Apps that provides enhanced visibility and control for Microsoft 365. Microsoft 365 Cloud App Security includes threat detection based on user activity logs, discovery of Shadow IT for apps that have similar functionality to Microsoft 365 offerings, control app permissions to Microsoft 365, and apply access and session controls. Microsoft 365 Cloud App Security has access to all of the features of Microsoft Defender for Cloud Apps, but supports only the Microsoft 365 app connector.

> [!NOTE]
> Microsoft 365 Cloud App Security is accessed through the same portal as Microsoft Defender for Cloud Apps. It is bundled with the [Microsoft 365 E5 subscription](https://www.microsoft.com/microsoft-365/enterprise/office-365-e5). Depending on your license, you'll either have access to Microsoft 365 Cloud App Security or the entire Defender for Cloud Apps solution.

### Feature support

|Capability|Feature|Microsoft Defender for Cloud Apps|Microsoft 365 Cloud App Security|
|----|----|----|----|
|Cloud Discovery|Discovered apps |31,000 + cloud apps  |750+ cloud apps with similar functionality to Microsoft 365|
||Deployment for discovery analysis|<li> Manual upload <br> <li> Automated upload - Log collector and API <br> <li> Native Defender for Endpoint integration |Manual log upload|
||Log anonymization for user privacy|Yes||
||Access to full Cloud App Catalog|Yes||
||Cloud app risk assessment|Yes||
||Cloud usage analytics per app, user, IP address|Yes||
||Ongoing analytics & reporting|Yes||
||Anomaly detection for discovered apps|Yes||
|Information Protection|Data Loss Prevention (DLP) support|Cross-SaaS DLP and data sharing control|Uses existing Office DLP (available in Office E3 and above)|
||App permissions and ability to revoke access|Yes|Yes|
||Policy setting and enforcement|Yes||
||Integration with Azure Information Protection |Yes||
||Integration with third-party DLP solutions|Yes||
|Threat Detection|Anomaly detection and behavioral analytics|For Cross-SaaS apps including Microsoft 365|For Microsoft 365 apps |
||Manual and automatic alert remediation|Yes|Yes|
||SIEM connector|Yes. Alerts and activity logs for cross-SaaS apps.|For Microsoft 365 alerts only|
||Integration to Microsoft Intelligent Security Graph|Yes|Yes|
||Activity policies|Yes|Yes|
|Conditional Access App Control|Real-time session monitoring and control|Any cloud and on-premises app|For Microsoft 365 apps|
|Cloud Platform Security|Security configurations|For Azure, AWS, and GCP|For Azure|

## Next steps

- Read about the basics in [Getting started with Defender for Cloud Apps](./get-started.md).

[!INCLUDE [Open support ticket](includes/support.md)]
