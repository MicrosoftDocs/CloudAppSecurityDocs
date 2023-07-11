---
title: What's new 
description: This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.
ms.date: 05/15/2023
ms.topic: overview
---
# What's new in Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

*Applies to: Microsoft Defender for Cloud Apps*

This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.

RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://aka.ms/mda/rss`

> [!NOTE]
>
> Threat protection product names from Microsoft are changing. Read more about this and other updates [here](https://www.microsoft.com/security/blog/?p=91813). We'll be using the new names in future releases.

For more information on what's new with other Microsoft Defender security products, see:

- [What's new in Microsoft 365 Defender](/microsoft-365/security/defender/whats-new)
- [What's new in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/whats-new-in-microsoft-defender-endpoint)
- [What's new in Microsoft Defender for Identity](/defender-for-identity/whats-new)

> [!NOTE]
> As of August 28 2022, users who were assigned an Azure AD **Security Reader** role won't be able to manage the Microsoft Defender for Cloud Apps alerts. This change will be gradually rolled out to all customers over the next several weeks. To continue to manage alerts, the user's role should be updated to an Azure AD **Security Operator**.

## July 2023

### Session and access policy consolidation

Defender for Cloud Apps now simplifies working with both session and access policies. Previously, in order to create a session or access policy for a host happ, such as Exchange, Teams, or Gmail, customers would need to create a separate policy for any relevant resource app, such as SharePOint, OneDrive, or Google Drive. Starting on July 11, 2023, you now only need to create a single policy on the hosted app.

For more information, see:

- [Control cloud apps with policies](/defender-cloud-apps/control-cloud-apps-with-policies)
- [Access policies in Microsoft Defender for Cloud Apps](/defender-cloud-apps/access-policy-aad)
- [Session policies](/defender-cloud-apps/session-policy-aad)

## June 2023

> [!NOTE]
> Starting in June 2023, updates for app governance are listed together with other Microsoft Defender for Cloud features. For information about earlier releases, see [What's new in the app governance add-on to Defender for Cloud Apps](app-governance-whats-new.md).

### New IP addresses for access and session controls 

The IP addresses used for our access and session controls services have been updated.  Make sure to update your firewall's allowlist accordingly to keep the service fully functional. Newly added addresses include:

|Data center|Public IPs|
|----|----|
|**Brazil South**  | 191.235.54.192, 191.235.58.85, 191.235.59.0, 191.235.58.255, 191.235.58.203, 191.235.57.180, 191.235.58.56, 191.235.58.201, 20.206.229.223, 191.235.55.73, 20.206.75.66, 20.226.100.200, 20.206.231.146, 104.41.37.185 |
|**West US 3**  |20.14.38.222, 20.14.38.249, 20.150.153.126, 20.150.157.146, 20.150.157.211, 20.150.152.101, 20.106.80.235, 20.106.81.123, 20.150.158.183, 20.150.153.110, 20.118.150.70, 20.118.145.8, 20.150.143.88, 20.125.76.39, 20.106.103.34, 20.163.100.176  |
|**North Europe**|  20.166.182.165, 20.166.182.171, 20.166.182.163, 20.166.182.193, 4.231.129.248, 20.54.22.195, 4.231.129.246, 20.67.137.212, 40.127.131.206, 20.166.182.159, 20.166.182.182, 68.219.99.39, 20.166.182.204, 68.219.99.63 |
|**Canada Central** | 20.175.151.201, 20.175.142.34, 20.175.143.233, 4.205.74.15, 20.175.142.19, 20.175.142.143, 20.175.140.191, 20.175.151.166, 20.175.140.185, 20.175.143.220, 20.175.140.128, 20.104.25.35, 4.205.74.7, 20.220.128.26 |
|**East Asia** | 20.195.89.186, 20.195.89.213, 20.195.89.128, 20.195.89.62, 20.195.89.219, 20.239.27.66, 20.239.26.193, 20.195.89.72, 20.195.89.166, 20.195.89.56, 20.187.114.178, 20.239.119.245, 20.205.119.72, 20.187.116.207 |
|**Australia Southwest**| 20.211.237.204, 20.92.29.167, 4.198.154.86, 4.198.66.117, 4.198.66.135, 20.11.210.40, 4.198.66.90, 20.92.8.154, 4.198.66.105, 4.198.66.78, 20.190.102.146, 4.198.66.126, 4.198.66.94, 4.198.66.92 |
|**Central India**| 20.219.226.117, 20.204.235.50, 20.235.81.243, 20.204.235.230, 20.219.226.224, 20.204.236.111, 20.204.236.147, 20.204.236.213, 20.204.236.115, 20.204.236.74, 20.204.236.17, 20.235.115.136, 20.219.218.134, 20.204.251.239, 4.224.61.207 |
|**Southeast Asia** | 20.24.14.233 |
|**France Central** | 20.74.115.131, 20.74.94.109, 20.111.40.153, 20.74.94.42, 20.74.94.220, 51.103.31.141, 20.74.95.102, 20.74.94.113, 51.138.200.138, 20.74.94.139, 20.74.94.136, 51.103.95.227, 20.74.114.253, 20.74.94.73 | 
|**West Europe** | 20.76.199.12, 20.160.197.20, 20.76.199.126, 20.76.198.169, 20.4.196.150, 20.76.199.32, 13.69.81.118, 20.76.151.201, 20.76.199.49, 20.76.198.36, 20.76.199.14, 20.76.198.91, 20.93.194.151, 20.229.66.63 |
|**UK West** | 20.90.53.127, 51.142.187.141, 20.68.122.206, 20.90.53.162, 20.90.53.126, 20.90.50.109, 20.90.53.132, 20.90.53.133, 20.68.124.199, 20.90.49.200, 51.142.187.196, 20.254.168.148, 51.137.144.240, 20.90.50.115 |
|**East US** | 40.117.113.165, 20.168.249.164, 172.173.135.148, 52.142.27.43, 20.237.22.163, 20.121.150.131, 20.237.18.20, 20.237.16.199, 20.237.16.198, 20.237.23.162, 20.124.59.116, 20.237.18.21, 20.124.59.146, 20.237.22.162 |

For more information, see [Network requirements](network-requirements.md).

### App governance now available as part of Defender for Cloud Apps license

App governance is now included as part of the [Microsoft Defender for Cloud Apps licenses](app-governance-get-started.md#licensing) and no longer requires an add-on license.

In the Microsoft 365 Defender portal, go to **Settings > Cloud apps > App governance > Service status** to either enable app governance if available, or sign up for the waitlist. 

Existing holders of trial licenses for the app governance add-on have until **July 31, 2023** to enable the toggle and retain their app governance access. 

For more information, see:

- [App governance Defender for Cloud Apps in Microsoft 365 Defender](app-governance-manage-app-governance.md)
- [Turn on app governance for Microsoft Defender for Cloud Apps](app-governance-get-started.md).

### App governance OAuth convergence

For customers who've enabled app governance, we've consolidated monitoring and policy enforcement capabilities for all OAuth apps in app governance. 

In the Microsoft 365 Defender portal, we've merged all capabilities originally under **Cloud apps > OAuth apps under  App governance**, where you can manage all OAuth apps under a single pane of glass.

For more information, see [View your apps](app-governance-visibility-insights-view-apps.md).

### Enhanced hunting experience for OAuth app activities

App governance now makes it easy for you to take hunting with app data to the next level by providing deeper OAuth app insights, helping your SOC identify an app’s activities and the resources it has accessed.

OAuth app insights include:

- Out-of-the-box queries that help to streamline the investigation
- Visibility into the data using the results view
- The ability to include OAuth app data such as resource, app, user, and app activity details in custom detections.

For more information, see [Hunt for threats in app activities](app-activity-threat-hunting.md).

### App hygiene update with  Microsoft Entra

Starting June 1, 2023, management of unused apps, unused credentials, and expiring credentials will only be available to app governance customers with Microsoft Entra Workload Identities Premium.

For more information, see [Secure apps with app hygiene features](app-governance-secure-apps-app-hygiene-features.md) and [What are workload identities?](/azure/active-directory/workload-identities/workload-identities-overview).

## May 2023

- **Behavior-generating policies no longer generate alerts** (Preview). Starting May 28, 2023, policies that generate *behaviors* in Microsoft 365 Defender advanced hunting do not generate alerts. The policies will continue generating *behaviors* regardless of being enabled or disabled in the tenant's configuration.

    For more information, see [Investigate behaviors with advanced hunting (Preview)](behaviors.md).

- **Non-blockable applications** (Preview): To prevent users from accidentally causing downtime, Defender for Cloud Apps now prevents you from blocking business-critical Microsoft services.
    For more information, see [Govern discovered apps](governance-discovery.md#non-blockable-applications).

## April 2023

### Defender for Cloud Apps release 251-252

April 30, 2023

- **The Microsoft Defender for Cloud Apps integration into Microsoft 365 Defender is Generally Available (GA)**. For more information, see [Microsoft Defender for Cloud Apps in Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-security-center-defender-cloud-apps).

- **The automatic redirection option is Generally Available (GA)**. Admins can use this option to redirect users from the standalone Defender for Cloud Apps portal to Microsoft 365 Defender. 

    By default, this option is set to **Off**. Admins must explicitly opt in by switching the toggle to **On** to exclusively use the Microsoft 365 Defender experience. 
    
    For more information, see [Redirecting accounts from Microsoft Defender for Cloud Apps to Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-security-mda-redirection).

- **Settings pages updates**:

    The capabilities on the following pages are fully integrated into Microsoft 365 Defender, and therefore don't have their own standalone experience in Microsoft 365 Defender:
  
    - [Settings > Azure AD Identity Protection](/microsoft-365/security/defender/investigate-alerts)
    - [Settings > App Governance](app-governance-get-started.md)
    - [Settings > Microsoft Defender for Identity](/defender-for-identity/deploy-defender-identity)
  
    The following pages are planned for deprecation together with the Microsoft Defender for Cloud Apps portal:

    - **Settings > Export settings**
    - **Activity log > Web traffic log**

### Defender for Cloud Apps release 250

April 24, 2023

- Zoom App connector for SSPM (Public preview)

    Defender for Cloud apps now supports a new Zoom App connector for SSPM. For more information, see [Connect Zoom to Microsoft Defender for Cloud Apps](connect-zoom.md).  


April 2, 2023

- New "behaviors" data type in Microsoft 365 Defender advanced hunting (Preview)  
To enhance our threat protection and reduce alert fatigue, we've added a new data layer called "behaviors" to the Microsoft Defender for Cloud Apps experience in Microsoft 365 Defender advanced hunting. This feature is intended to provide relevant information for investigations by identifying anomalies or other activities that may be related to security scenarios, but don't necessarily indicate malicious activity or a security incident. In this first stage, some of the Microsoft Defender for Cloud App anomaly detections will also be presented as behaviors. In future phases, these detections will only generate behaviors and not alerts. For more information, see [Investigate behaviors with advanced hunting (Preview)](behaviors.md).

## March 2023
### Defender for Cloud Apps release 249

March 19, 2023

- **Automatic redirection from Microsoft Defender for Cloud Apps to the Microsoft 365 Defender portal (Preview)**  
A new automatic redirection toggle will allow you to trigger the automatic redirection from Microsoft Defender for Cloud Apps to Microsoft 365 Defender. Once the redirection setting is enabled, users accessing the Microsoft Defender for Cloud Apps portal will be automatically routed to the Microsoft 365 Defender portal. The toggle default value is set to **Off**, and admins will need explicitly to opt-in to the automatic redirection and start using the Microsoft 365 Defender exclusively. You still have an option to opt-out from the Microsoft 365 Defender experiences and to use Microsoft Defender for Cloud Apps standalone portal. This can be done by switching off the toggle. For more information, see [Redirecting accounts from Microsoft Defender for Cloud Apps to Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-security-mda-redirection).

### Defender for Cloud Apps release 248

March 5, 2023

- **Faster load time for protected sessions**  
We've made significant improvements to the loading time of web pages protected by session policies. End users that are scoped to session policies, either from a desktop or mobile device, can now enjoy a faster and more seamless browsing experience.
We've witnessed an improvement of between 10% and 40%, depending on the application, the network, and the complexity of the web page.

- **Support for Tokyo ServiceNow version**  
The Defender for Cloud Apps connector for ServiceNow now supports the ServiceNow Tokyo version. With this update, you can protect the latest versions of ServiceNow using Defender for Cloud Apps. For more information, see [Connect ServiceNow to Microsoft Defender for Cloud Apps](connect-servicenow.md).

## February 2023

### Defender for Cloud Apps release 246 and 247

February 19, 2023

- **SaaS Security Posture Management (SSPM) capabilities update announcements (GA and Public preview)**  
We have made important improvements to our governance and protection of third-party software-as-a-service (SaaS) applications. These improvements include assessments to identify risky security configurations using Microsoft Defender for Cloud Apps, as well as smoother integration into the Microsoft Secure Score experience. We have now released Salesforce and ServiceNow to general availability, while Okta, GitHub, Citrix ShareFile, and DocuSign are currently in public preview. For more information, see [Connect apps to get visibility and control with Microsoft Defender for Cloud Apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

- **Malware detection policy governance actions now available (preview)**  
Automatic actions for files detected by the malware detection policy are now available as part of the policy configuration. The actions differ from app to app. For more information, see [Malware governance actions (Preview)](governance-actions.md#malware-governance-actions-preview).

- **Log Collector Version Update**  

    We've released a new log collector version with the latest vulnerabilities fixes.

    New version: **columbus-0.246.0-signed.jar**  
    Image name: **mcaspublic.azurecr.io/public/mcas/logcollector tag: latest/0.246.0 image id : eeb3c4f1a64c**

    The Docker image was rebuilt with these updates:

    | Dependency  name               | From  version        | To  version          | Comments                                                     |
    | ------------------------------ | -------------------- | -------------------- | ------------------------------------------------------------ |
    | amazon-corretto                | 8.222.10.1-linux-x64 | 8.352.08.1-linux-x64 |                                                              |
    | openssl  1.1.1                 | 1.1.1q               | 1.1.1s               | The  1.1.1 series is available and is supported until Sep 11, 2023. |
    | Pure  ftpd                     | 1.0.49               | 1.0.50               |                                                              |
    | fasterxml.jackson.core.version | 2.13.3               | 2.14.1               | 2.14  was released in Nov 2022                               |
    | org.jacoco                     | 0.7.9                | 0.8.8                | Version  0.8.8 from Apr 05, 2022                             |

    To begin using the new version, you'll need to stop your log collectors, remove the current image, and install the new one.

    To verify the new version is running, run the following command inside the Docker container:

    `cat /var/adallom/versions | grep columbus-`

## January 2023
### Defender for Cloud Apps release 244 and 245

January 22, 2023

- **File policy – exploring multiple SITs**  
Defender for Cloud Apps already includes the ability to explore policy file matches that contain sensitive information types (SITs). Now, Defender for Cloud Apps also allows you to differentiate between multiple SITs in the same file match. This feature, known as short evidence, lets Defender for Cloud Apps better manage and protect your organization's sensitive data. For more information, see [Examine evidence (preview)](dcs-inspection.md#examine-evidence-preview).


## Next steps

- For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[!INCLUDE [Open support ticket](includes/support.md)]
