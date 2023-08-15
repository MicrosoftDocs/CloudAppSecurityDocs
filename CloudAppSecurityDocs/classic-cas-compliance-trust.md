---
title: Classic portal -  Data security and privacy practices
description: Classic portal -  This article describes the Defender for Cloud Apps compliance offering, trust center, privacy, and data security.
ms.date: 01/19/2023
ms.topic: overview
ROBOTS: NOINDEX
---
# Classic portal: Data security and privacy practices for Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

[!INCLUDE [Handle personal data](../includes/gdpr-intro-sentence.md)]

Microsoft Defender for Cloud Apps is a critical component of the Microsoft Cloud Security stack. It's a comprehensive solution that helps your organization take full advantage of the promise of cloud applications. Defender for Cloud Apps keeps you in control through comprehensive visibility, auditing, and granular controls over your sensitive data.

Defender for Cloud Apps has tools that help uncover shadow IT and assess risk while enabling you to enforce policies and investigate activities. It helps you control access in real time and stop threats so your organization can more safely move to the cloud.

## Defender for Cloud Apps compliance

In a world where data breaches and attacks are daily occurrences, it's essential for organizations to choose a Cloud Access Security Broker (CASB) that makes every effort to protect their data. Defender for Cloud Apps, like all Microsoft cloud products and services, is built to address the rigorous security and privacy demands of our customers.

To help organizations comply with national/regional and industry-specific requirements governing the collection and use of individuals' data, Defender for Cloud Apps provides a comprehensive set of compliance offerings. The compliance offerings include certifications and attestations.

### Compliance framework and offerings

Defender for Cloud Apps meets many international and industry-specific compliance standards including, but not limited to:

| Organization |Title|Description|
|----|----|----|
|![logo csa attestation.](media/classic-csastar-attest.png)|CSA STAR Attestation|Azure and Intune were awarded Cloud Security Alliance STAR Attestation based on an independent audit.|
|![logo csa certification.](media/classic-csastar.png)|CSA STAR Certification|Azure, Intune, and Power BI were awarded Cloud Security Alliance STAR Certification at the Gold level.|
|![logo EU model clauses.](media/classic-eu-model-icon.png)|[EU Model Clauses](/compliance/regulatory/offering-EU-Model-Clauses)|Microsoft offers EU Standard Contractual Clauses, guarantees for transfers of personal data.|
|![logo HIPAA.](media/classic-hipaa-logo.png)|[HIPAA/HITECH](/compliance/regulatory/offering-hipaa-hitech)|Microsoft offers Health Insurance Portability & Accountability Act Business Associate Agreements (BAAs).|
|![logo iso 9001.](media/classic-iso-9001.png)|ISO 9001|Microsoft is certified for its implementation of these quality management standards.|
|![logo iso 27001.](media/classic-iso-27001.png)|[ISO/IEC 27001](/compliance/regulatory/offering-ISO-27001)|Microsoft is certified for its implementation of these information security management standards.|
|![logo iso 27018.](media/classic-iso-27018.png)|[ISO/IEC 27018](/compliance/regulatory/offering-ISO-27018)|Microsoft was the first cloud provider to adhere to this code of practice for cloud privacy.|
|![logo PCI.](media/classic-pci-logo.png)|PCI DSS|Azure complies with Payment Card Industry Data Security Standards Level 1 version 3.1.|
|![logo SOC.](media/classic-soc-logo.png)|[SOC 1 and SOC 2 Type 2 Reports](/compliance/regulatory/offering-home)|Microsoft cloud services comply with Service Organization Controls standards for operational security.|
|![logo SOC.](media/classic-soc-logo.png)|SOC 3|Microsoft cloud services comply with Service Organization Controls standards for operational security.|
|![logo g-cloud.](media/classic-g-cloud.png)|UK G-Cloud|The Crown Commercial Service renewed the Microsoft cloud services classification to Government Cloud v6.|

For more information, go to [Microsoft Compliance Offerings](/compliance/regulatory/offering-home).  

## Privacy

### You're the owner of your data

- In Defender for Cloud Apps, your administrators can view the identifiable personal data stored in the service from the portal using the Search bar.
- Admins can search for a specific user's metadata or user's activity. Clicking on an entity opens the [**Users and accounts**](accounts.md). The **Users and accounts** page provides you with comprehensive details about the entity that are pulled from connected cloud applications. It also provides the user's activity history and security alerts related to the user.

- You own your data and can cancel subscriptions and request deletion of your data at any time. If you don't renew your subscription, your data will be deleted within the timeline specified in the [Online Services Terms](https://www.microsoft.com/licensing/docs?DocumentTypeId=31&redirected=true&Mode=3).

- If you ever choose to terminate the service, you can take your data with you.

### Defender for Cloud Apps is the processor of your data

- Defender for Cloud Apps uses your data only for purposes that are consistent with providing the services to which you subscribe.

- If a government approaches Microsoft for access to your data, Microsoft redirects the inquiry to you, the customer, whenever possible. Microsoft has challenged legal demands that weren't valid, which prohibited disclosure of [a government request](https://www.microsoft.com/corporate-responsibility/law-enforcement-requests-report) for customer data. Learn more about [who can access your data and on what terms](https://www.microsoft.com/trust-center/privacy/data-access).

### Privacy controls

- Privacy controls help you configure who in your organization has access to  the service and what they can access.

## Updating personal data

Personal data about users is derived from the user's object in the SaaS applications used. Because of this, any changes made to the user profile in these applications are reflected in Defender for Cloud Apps.

## Data location

Defender for Cloud Apps currently operates in datacenters in the European Union, the United Kingdom, and the United States (each a "Geo"). Customer data collected by the service is stored at rest as follows (a) for customers whose tenants are provisioned in the European Union or the United Kingdom, in either the European Union or the United Kingdom; (b) else, a data center in the Geo that is nearest to the location of where the customer's Azure Active Directory tenant has been provisioned; or (c) if Defender for Cloud Apps uses another Microsoft online service (such as Azure Active Directory or Azure CDN) to process such data, the data geolocation will be as defined by the data storage rules of that other online service.

> [!NOTE]
> Defender for Cloud Apps uses Azure Data Centers around the world to provide optimized performance through geolocation. This means that a user's session may be hosted outside of a particular region, depending on traffic patterns and their location. However, to protect your privacy, no session data is stored in these data centers.

[Learn more about privacy](https://www.microsoft.com/trustcenter/privacy)

## Transparency

Microsoft provides transparency about its practices:

- Sharing with you where your data is stored.
- Affirming that your data is used only to deliver agreed-upon services.
- Specifying how Microsoft engineers and approved subcontractors use this data to provide services.

Microsoft uses strict controls to govern access to customer data, granting the lowest level of access required to complete key tasks and revoking access when it's no longer needed.

### Data protection

Defender for Cloud Apps enforces data protection during content inspection. File content isn't stored in the Defender for Cloud Apps datacenter. Only the metadata of the file records and any matches that were identified are stored.

### Data retention

Defender for Cloud Apps retains data as follows:

- Activity log: 180 days
- Discovery data: 90 days
- Alerts: 180 days
- Governance log: 120 days

You can learn more about Microsoft data practices by reading the [Online Service Terms](https://www.microsoft.com/licensing/docs?DocumentTypeId=31&Mode=3).

[Learn more about transparency](https://www.microsoft.com/trust-center/privacy/data-management)

### Deleting personal data

After a user's account  is deleted from a connected cloud application, Defender for Cloud Apps will automatically delete the copy of the data within two years.

### Exporting personal data

Defender for Cloud Apps provides you with the ability to [export](activity-filters.md#export-activities) to CSV all user activity and security alert information.

### Data flow

Defender for Cloud Apps provides you with the convenience of working with some data, such as alerts and activities, without disrupting your usual security workflow. For example, SecOps may prefer to view alerts in their preferred SIEM product such as [Microsoft Sentinel](siem-sentinel.md). To enable such workflows, when integrating with Microsoft or third-party products, Defender for Cloud Apps exposes some data through them.

The following table show what data is surfaced for each product integration:

#### Microsoft products

| Product | Exposed data | Configuration |
| --- | --- | --- |
| Microsoft 365 Defender | Alerts and user activities | Enabled automatically on Microsoft 365 Defender upon onboarding |
| Microsoft Sentinel | Alerts and discovery data | [Enabled in Defender for Cloud Apps](siem-sentinel.md) and [configured in Microsoft Sentinel](/azure/sentinel/data-connectors-reference#microsoft-defender-for-cloud-apps) |
| Microsoft Purview compliance portal | Alerts for Microsoft 365 | Automatically streamed to Microsoft Purview compliance portal  |
| Microsoft Defender for Cloud | Alerts for Azure | Enabled by default in Defender for Cloud Apps; can be disabled in Microsoft Defender for Cloud |
| Microsoft Graph Security API | Alerts | [Available via Microsoft Graph Security API](/graph/api/resources/security-api-overview) |
| Microsoft Power Automate | Alerts sent to trigger an automated flow | [Configured in Defender for Cloud Apps](flow-integration.md) |
| Microsoft Azure AD Identity Protection | Subset of alerts for identity risk model | Enabled automatically on Azure AD Identity Protection upon onboarding |

#### Third-party products

| Integration type | Exposed data | Configuration |
| --- | --- | --- |
| Using a SIEM agent | Alerts and events | [Enabled and configured in Defender for Cloud Apps](siem.md) |
| Using the Defender for Cloud Apps REST API | Alerts and events | [Enabled and configured in Defender for Cloud Apps](api-authentication.md) |
| ICAP connector | File for DLP scan | [Enabled and configured in Defender for Cloud Apps](icap-stunnel.md) |

> [!NOTE]
> Other products may not enforce Defender for Cloud Apps role-based security permissions to control who has access to what data. Therefore, before integrating with other products, make sure you understand what data is sent to the product you want to use and who has access to it.

## Security

### Encryption

Microsoft uses encryption technology to protect your data while at rest in a Microsoft database and when it travels between user devices and Defender for Cloud Apps datacenters. Additionally, all communication between Defender for Cloud Apps and connected apps is encrypted using HTTPS.

> [!NOTE]
> Defender for Cloud Apps leverages Transport Layer Security (TLS) protocols 1.2+ to provide best-in class encryption. Native client applications and browsers that do not support TLS 1.2+, will not be accessible when configured with session control. However, SaaS apps that use TLS 1.1 or lower will appear in the browser as using TLS 1.2+ when configured with Defender for Cloud Apps.

### Identity and access management

Defender for Cloud Apps enables you to limit access of administrators to the portal based on geolocation using Azure Active Directory. It's possible to require multi-factor authentication to access the Defender for Cloud Apps portal by using Azure Active Directory.

### Permissions

Defender for Cloud Apps supports role-based access control. Microsoft 365 and Azure Active Directory Global admin and Security admin roles have full access to Defender for Cloud Apps, and Security readers have read access. [For more information](manage-admins.md).

## Customer controls for organizational compliance

### Scoped deployment

Defender for Cloud Apps enables you to scope your deployment. Scoping enables you to govern only specific groups using Defender for Cloud Apps, or to exclude specific groups from Defender for Cloud Apps governance. For more information, see [Scoped deployment](scoped-deployment.md).

### Anonymization

You can choose to keep **Cloud Discovery** reports anonymous. After your log files are uploaded to Microsoft Defender for Cloud Apps, all username information is replaced with encrypted usernames. For specific security investigations, you can resolve the real username. Private data is encrypted using AES-128 with a dedicated key per tenant. [For more information](cloud-discovery-anonymizer.md).

## Security and Privacy for Defender for Cloud Apps US Government GCC High customers

For information on Defender for Cloud Apps compliance standards and the location of data for US Government GCC High customers, see [Enterprise Mobility + Security for US Government service description](/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description).

## Next steps

- [Defender for Cloud Apps overview](https://www.microsoft.com/security/business/cloud-apps-defender)
- [Defender for Cloud Apps documentation](index.yml)
- [Sign up for Defender for Cloud Apps](https://signup.microsoft.com/create-account/signup?ali=1&products=757c4c34-d589-46e4-9579-120bba5c92ed&OfferId=757c4c34-d589-46e4-9579-120bba5c92ed)

Get a free trial of Defender for Cloud Apps, and see how it meets your business challenges.
