---
# required metadata

title: Cloud App Security versions | Microsoft Docs
description: This topic provides infomration about Cloud App Security versions and the difference between Cloud App Security and Advanced Security Management.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/11/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 8fa8b046-e5cc-4384-94ac-76a4b36d2912

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Cloud App Security versions

**Cloud App Security**: The standalone version of Cloud App Security provides 
**ASM**: Office 365 Advanced Security Management gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues. Advanced Security Management is powered by Cloud App Security. With Advanced Security Management, you can:

- See how your organization's data in Office 365 is accessed and used

- Control access to Office 365 data on mobile devices/apps

- Define policies that trigger alerts for atypical or suspicious activities

- Suspend user accounts exhibiting suspicious activity

- Require users to log back in to Office 365 apps after an alert has been triggered

Office 365 Advanced Security Management allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see Overview of Advanced Security Management in Office 365.


## CAS certifications

| |Title|Description|
|----|----|----|
|![logo csa](./media/csastar-attest.png)|CSA STAR Attestation|Azure and Intune were awarded Cloud Security Alliance STAR Attestation based on an independent audit.|
|![logo csa](./media/csastar.png)|CSA STAR Certification|Azure, Intune, and Power BI were awarded Cloud Security Alliance STAR Certification at the Gold level.|
|![logo EU model clauses](./media/eu-model-icon.png)|EU Model Clauses|Microsoft offers EU Standard Contractual Clauses, guarantees for transfers of personal data.|
|![logo privacy shield](./media/privacy_shield.png)|EU-U.S. Privacy Shield|Microsoft complies with this framework for protecting personal data transferred from the EU to the US.|
|![logo FISC](./media/logo_fisc.png)|FISC|Microsoft meets the requirements of the Financial Industry Information Systems v8 standard in Japan.|
|![logo HIPAA](./media/hipaa-logo.png)|HIPAA/HITECH|Microsoft offers Health Insurance Portability & Accountability Act Business Associate Agreements (BAAs).|
|![logo iso 9001](./media/iso-9001.png)|ISO 9001|Microsoft is certified for its implementation of these quality management standards.|
|![logo iso 27001](./media/iso-27001.png)|ISO 27001|Microsoft is certified for its implementation of these information security management standards.|
|![logo iso 27018](./media/iso-27018.png)|ISO 27018|Microsoft was the first cloud provider to adhere to this code of practice for cloud privacy.|
|![logo PCI](./media/pci-logo.png)|PCI DSS|Azure complies with Payment Card Industry Data Security Standards Level 1 version 3.1.|
|![logo SOC](./media/soc-logo.png)|SOC 1 Type II Report|Microsoft cloud services comply with Service Organization Controls standards for operational security.|
|![logo SOC](./media/soc-logo.png)|SOC 2 Type II Report|Microsoft cloud services comply with Service Organization Controls standards for operational security.|
|![logo SOC](./media/soc-logo.png)|SOC 3|Microsoft cloud services comply with Service Organization Controls standards for operational security.|
|![logo g-cloud](./media/g-cloud.png)|UK G-Cloud|The Crown Commercial Service renewed the Microsoft cloud services classification to Government Cloud v6.|

For more information, go to [Microsoft Compliance Offerings] (https://go.microsoft.com/fwlink/?linkid=842039) and select Cloud App Security.  


## GDPR – ADIR
In May 2018, a European privacy law, the General Data Protection Regulation (GDPR), is due to take effect. The GDPR imposes new rules on companies, government agencies, non-profits, and other organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data tied to EU residents. The GDPR applies no matter where you are located.
Microsoft has extensive expertise in protecting data, championing privacy, and complying with complex regulations. We believe that the GDPR is an important step forward for clarifying and enabling individual privacy rights. We want to help you focus on your core business while efficiently preparing for the GDPR.
We are committed to GDPR compliance across Cloud App Security when enforcement begins May 25, 2018, and provide [GDPR related assurances in our contractual commitments](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx).

## PII 
When Cloud App Security performs content inspection, data privacy is enforced. The file content is not stored in the Cloud App Security database; only the metadata of the file records and any violations that were identified are stored in the Cloud App Security database. Cloud App Security does store IP addresses which some companies consider Private Information.

For more information about data retention, see our [privacy policy](http://go.microsoft.com/fwlink/?LinkId=512132) and the [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/You-are-in-control-of-your-data).

## Do not track
Cloud App Security enables you to set certain users to Do Not Track (DNT). To enable this feature, speak to your Microsoft representative about enabling preview features.

## Anonymization 

Cloud Discovery data anonymization enables you to protect user privacy. Once the data log is uploaded to the Cloud App Security portal, the log is sanitized and all username information is replaced with encrypted usernames. This way, all cloud activities are kept anonymous. When necessary, for a specific security investigation (for example, due to a security breach or suspicious user activity), admins can resolve the real username. If an admin has a reason to suspect a specific user, he can also look up the encrypted username of a known username, and then start investigating using the encrypted username. Each username conversion is audited in the portal’s **Governance log**.

No private information is stored or displayed, only encrypted information. Private data is encrypted using AES-128 with a dedicated key per tenant. Resolving usernames is performed ad-hoc, per-username by deciphering a given encrypted username.

## Encryption at rest
All data stored in Cloud App Security is encrypted. All the sensitive fields are stored using the same advanced encryption features as in Azure, such as Key Vault.

## Geofencing
The Cloud App Security enables you to limit access of administrators to the portal based on geolocation using Azure AD to limit access.

## Permissions
Cloud App Security supports Role based access control. By default, the following Office 365 and Azure AD admin roles have access to Cloud App Security:

- Global administrator and Security administrator: Admins will **Full access** will have full permissions in Cloud App Security to add admins, add policies and settings, upload logs and perform governance actions.

- Security reader: Has read-only permissions and can manage alerts. The Security reader is restricted from performing the following:
      - Create policies or edit and change existing ones 
      - Performing any governance actions 
      - Uploading discovery logs
      - Banning or approving third party apps
      - Accessing and viewing the IP address range settings page
      - Accessing and viewing any settings pages 
      - Acccessing and viewing the Discovery settings 
      - Accessing and vieweing the App connectors page
      - Accessing and viewing the Governance log 
      - Accessing and viewing the Manage snapshot reports page 

For more information see [Assigning administrator roles in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles).

## Multi-factor authentication
It is possible to require multi-factor authentication to access the Cloud App Security portal by using the Azure Active Directory access to Cloud App Security. 

## Audit logs

All Cloud App Security configuration changes are audited in the Windows Event Log.

## Data retention

Cloud App Security retains data as follows: 
 
- Activity log: 180 days 
- Discovery data: 90 days 
- Alerts: 180 days 

After data is collected from these sources, Cloud App Security runs sophisticated analysis on the data. It immediately alerts you to anomalous activities, and gives you deep visibility into your cloud environment. You can configure a policy in Cloud App Security and use it to protect everything in your cloud environment.  

**ADIR** Where do we store data? We only store it in our data centers and right now that’s in US West * not sure if we want to expose this information

## See Also  

Read about the basics in [Getting started with Cloud App Security](getting-started-with-cloud-app-security.md).    
For technical support, go to the [Cloud App Security assisted support](http://support.microsoft.com/oas/default.aspx?prid=16031) page.   
Premier customers also can choose Cloud App Security directly from the [Premier portal](https://premier.microsoft.com/).   
