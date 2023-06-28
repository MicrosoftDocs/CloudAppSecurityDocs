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

## June 2023

> [!NOTE]
> Starting in June 2023, updates for app governance are listed together with other Microsoft Defender for Cloud features. For information about earlier releases, see [What's new in the app governance add-on to Defender for Cloud Apps](app-governance-whats-new.md).

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
