---
title: What's new 
description: This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.
ms.date: 12/12/2023
ms.topic: overview
---

# What's new in Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

*Applies to: Microsoft Defender for Cloud Apps*

This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.

RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://aka.ms/mda/rss`

For more information on what's new with other Microsoft Defender security products, see:

- [What's new in Microsoft Defender XDR](/microsoft-365/security/defender/whats-new)
- [What's new in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/whats-new-in-microsoft-defender-endpoint)
- [What's new in Microsoft Defender for Identity](/defender-for-identity/whats-new)

For news about earlier releases, see [Archive of past updates for Microsoft Defender for Cloud Apps](release-note-archive.md).

## December 2023

### SSPM support for more connected apps

Defender for Cloud Apps provides you with risk security configuration assessments for your SaaS applications to make sure you prevent possible risks. These recommendations are shown via [Microsoft Secure Score](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) once you have a connector to an application.

Defender for Cloud Apps has now enhanced its SSPM support by including the following apps:

- [Atlassian](protect-atlassian.md)
- [Dropbox](protect-dropbox.md)
- [NetDocuments](protect-netdocuments.md)
- [Workplace](protect-workplace.md)
- [Zendesk](protect-zendesk.md)

For more information, see [SaaS security posture management (SSPM)](security-saas.md) and [User, app governance, and security configuration visibility](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#user-app-governance-and-security-configuration-visibility).

## November 2023

### Defender for Cloud Apps application certificate rotation

Defender for Cloud Apps plans to rotate its application certificate. If you’ve previously explicitly trusted the legacy certificate and currently have SIEM agents running on newer versions of the Java Development Kit (JDK), you must trust the new certificate to ensure continued SIEM agent service. While it’s likely no action is needed, we recommend running the following commands to validate:
1. In a command line window, switch to the bin folder of your Java installation, for example:

    ```powershell
    cd "C:\Program Files (x86)\Java\jre1.8.0_291\bin"
    ```
1. Run the following command:
    
    ```powershell
    keytool -list -keystore ..\lib\security\cacerts

1. If you see the following 4 aliases, that means you have previously explicitly trusted our certificate and need to take action. If those aliases are not present, no action should be needed.
    - *azuretls01crt*
    - *azuretls02crt*
    - *azuretls05crt*
    - *azuretls06crt*


If you are in need of action, we recommend that you already trust the new certificates to prevent issues once the certificates are fully rotated.

For more information, see our [Issue with new versions of Java](troubleshooting-siem.md#issue-with-new-versions-of-java) troubleshooting guide.

### CSPM support in Microsoft Defender for Cloud

With the continual Microsoft Defender for Cloud Apps convergence into Microsoft Defender XDR, cloud security posture management (CSPM) connections are fully supported via Microsoft Defender for Cloud.

We recommend that you connect your Azure, AWS, and Google Cloud Platform (GCP) environments to Microsoft Defender for Cloud to get the latest CSPM capabilities.

For more information, see:

- [What is Microsoft Defender for Cloud?](/azure/defender-for-cloud/defender-for-cloud-introduction)
- [Cloud Security Posture Management (CSPM)](/azure/defender-for-cloud/concept-cloud-security-posture-management) in Defender for Cloud
- [Connect your Azure subscriptions](/azure/defender-for-cloud/connect-azure-subscription) to Microsoft Defender for Cloud
- [Connect your AWS account to Microsoft Defender for Cloud](/azure/defender-for-cloud/quickstart-onboard-aws)
- [Connect your GCP project to Microsoft Defender for Cloud](/azure/defender-for-cloud/quickstart-onboard-gcp)

> [!NOTE]
> Customers still using the [classic Defender for Cloud Apps portal](classic-cas-compliance-trust.md) no longer see [security configuration assessments](classic-security-config.md) for Azure, AWS, and GCP environments.
>

### Test mode for admin users (Preview)

As an admin user, you might want to test upcoming proxy bug fixes before the latest Defender for Cloud Apps release is fully rolled out to all tenants. To help you do this, Defender for Cloud Apps now provides a test mode, available from the **Admin View** toolbar.  

When in test mode, only admin users are exposed to any changes provided in the bug fixes. There is no effect on other users. We encourage you to send feedback about the new fixes to the Microsoft support team to help speed up release cycles.

When you're finished testing the new fix, turn test mode off to return to regular functionality. 

For example, the following image shows the new **Test Mode** button in the **Admin View** toolbar, laid over OneNote being used in a browser.

:::image type="content" source="media/release-notes/test-mode-new.png" alt-text="Screenshot of the new Test Mode button." lightbox="media/release-notes/test-mode-new.png":::

For more information, see [Diagnose and troubleshoot with the Admin View toolbar](troubleshooting-proxy.md#diagnose-and-troubleshoot-with-the-admin-view-toolbar) and [Test mode](troubleshooting-proxy.md#test-mode-preview).

### New cloud app catalog category for Generative AI

The Defender for Cloud Apps app catalog now supports the new **Generative AI** category for large language model (LLM) apps, like Microsoft Bing Chat, Google Bard, ChatGPT, and more. Together with this new category, Defender for Cloud Apps has added hundreds of generative AI-related apps to the catalog, providing visibility into how generative AI apps are used in your organization and helping you manage them securely.

:::image type="content" source="media/release-notes/generative-ai.png" alt-text="Screenshot of the new Generative AI category." lightbox="media/release-notes/generative-ai.png":::

For example, you may want to use Defender for Cloud Apps' [integration with Defender for Endpoint](mde-integration.md) to approve or block the usage of specific LLM apps based on a policy.

For more information, see [Find your cloud app and calculate risk scores](risk-score.md).

### General availability for more discovery Shadow IT events with Defender for Endpoint

Defender for Cloud Apps can now discover Shadow IT network events detected from Defender for Endpoint devices that are working in the same environment as a network proxy, in general availability.

For more information, see [Discover apps via Defender for Endpoint when the endpoint is behind a network proxy](mde-investigation.md#discover-apps-via-defender-for-endpoint-when-the-endpoint-is-behind-a-network-proxy) and [Integrate Microsoft Defender for Endpoint](mde-integration.md).

## October 2023

### Automatic redirect to Microsoft Defender XDR general availability 

Now, all customers are automatically redirected to Microsoft Defender XDR from the classic Microsoft Defender for Cloud Apps portal, as the redirect is in general availability. Admins can still update the redirect setting as needed to continue using the classic Defender for Cloud Apps portal.

Integrating Defender for Cloud Apps inside Microsoft Defender XDR streamlines the process of detecting, investigating, and mitigating threats to your users, apps, and data – so that you can review many alerts and incidents from a single pane of glass, in one XDR system.

For more information, see [Microsoft Defender for Cloud Apps in Microsoft Defender XDR](/microsoft-365/security/defender/microsoft-365-security-center-defender-cloud-apps#redirection-from-the-classic-microsoft-defender-for-cloud-apps-portal-to-microsoft-defender-xdr).

## September 2023

### More discovery for Shadow IT events (Preview)

Defender for Cloud Apps can now discover Shadow IT network events detected from Defender for Endpoint devices that are working in the same environment as a network proxy.

For more information, see [Discover apps via Defender for Endpoint when the endpoint is behind a network proxy (Preview)](mde-investigation.md#discover-apps-via-defender-for-endpoint-when-the-endpoint-is-behind-a-network-proxy) and [Integrate Microsoft Defender for Endpoint](mde-integration.md).

### Continuous NRT frequency supported for CloudAPPEvents table (Preview)

Defender for Cloud Apps now supports the [Continuous (NRT) frequency](/microsoft-365/security/defender/custom-detection-rules#continuous-nrt-frequency) for detection rules using the **CloudAppEvents** table. 

Setting a custom detection to run in Continuous (NRT) frequency allows you to increase your organization's ability to identify threats faster. For more information, see [Create and manage custom detections rules](/microsoft-365/security/defender/custom-detection-rules).

## August 2023

### New security recommendations in Secure Score (Preview)

New Microsoft Defender for Cloud Apps recommendations have been added as Microsoft Secure Score improvement actions. For more information, see [What's new in Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score-whats-new) and [Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score).

### Microsoft 365 connector updates
We've made the following updates to Defender for Cloud Apps's Microsoft 365 connector:

- (Preview) Updated SSPM support with new [CIS benchmark](https://www.cisecurity.org/cis-benchmarks) security recommendations.
- Aligned the names of existing recommendations to match the CIS benchmark.
  
To view related data, make sure that you've configured the Microsoft 365 connector. For more information, see [Connect Microsoft 365 to Microsoft Defender for Cloud Apps](connect-office-365.md).

## July 2023

### Log collector version 0.255.0

Defender for Cloud Apps has released the Defender for Cloud Apps log collector version 0.255.0, including updates to the *amazon-corretto* and *openssl* dependencies.

The new version filename is `columbus-0.255.0-signed.jar`, and the image name is `mcaspublic.azurecr.io/public/mcas/logcollector`, with the `latest/0.255.0` tag.

To update your log collector, make sure to stop the log collector in your environment, remove the current image, install the new one, and update the certificates.

For more information, see [Advanced log collector management](log-collector-advanced-management.md).

### ServiceNow connector now supports Utah version

The Defender for Cloud Apps ServiceNow connector now supports the ServiceNow *Utah* version. For more information, see [Connect ServiceNow to Microsoft Defender for Cloud Apps](connect-servicenow.md)

### Google Workspace connector updates

The Google Workspace connector now supports:

- (Preview) SaaS Security Posture Management (SSPM) tools for increased visibility into SaaS apps' posture misconfigurations when compared to the ideal app configurations. SSPM features help you proactively reduce the risk of breaches and attacks without needing to be a security expert for each platform.
- The **Enable multi-factor authentication** control. To view related data, make sure that you've configured the Google Workspace connector. 

For more information, see [Connect Google Workspace to Microsoft Defender for Cloud Apps](connect-google-workspace.md).

### Custom connectors with the open app connector platform (Preview)

Defender for Cloud Apps' new codeless, open app connector platform helps SaaS vendors create app connectors for their SaaS apps.

Create Defender for Cloud Apps connectors to extend app security features across customer SaaS ecosystems, safeguarding data, mitigating risks, and reinforcing overall SaaS security posture.

For more information, see [Microsoft Defender for Cloud Apps open app connector platform](connector-platform.md).

### New app connectors for Asana and Miro (Preview)

Defender for Cloud Apps now supports built-in app connectors for Asana and Miro, which both might hold critical data your organization and are therefore targets for malicious actors. Connect these apps to Defender for Cloud Apps for improved insights into your users' activities and threat detection with machine learning-based anomaly detections.

For more information, see:

- [Protect Asana](protect-asana.md)
- [Protect Miro](protect-miro.md)

### Session and access policy consolidation

Defender for Cloud Apps now simplifies working with both session and access policies. Previously, in order to create a session or access policy for a host app, such as Exchange, Teams, or Gmail, customers would need to create a separate policy for any relevant resource app, such as SharePoint, OneDrive, or Google Drive. Starting on July 11, 2023, you now only need to create a single policy on the hosted app.

For more information, see:

- [Control cloud apps with policies](/defender-cloud-apps/control-cloud-apps-with-policies)
- [Access policies in Microsoft Defender for Cloud Apps](/defender-cloud-apps/access-policy-aad)
- [Session policies](/defender-cloud-apps/session-policy-aad)

### Automatic redirect to Microsoft Defender XDR (Preview)

Customers using preview features are now automatically redirected to Microsoft Defender XDR from the classic Microsoft Defender for Cloud Apps portal. Admins can still update the redirect setting as needed to continue using the classic Defender for Cloud Apps portal.

For more information, see [Redirecting accounts from Microsoft Defender for Cloud Apps to Microsoft Defender XDR](/microsoft-365/security/defender/microsoft-365-security-mda-redirection).

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

In the Microsoft Defender Portal, go to **Settings > Cloud apps > App governance > Service status** to either enable app governance if available, or sign up for the waitlist. 

Existing holders of trial licenses for the app governance add-on have until **July 31, 2023** to enable the toggle and retain their app governance access. 

For more information, see:

- [App governance Defender for Cloud Apps in Microsoft Defender XDR](app-governance-manage-app-governance.md)
- [Turn on app governance for Microsoft Defender for Cloud Apps](app-governance-get-started.md).

### App governance OAuth convergence

For customers who have enabled app governance, we have consolidated monitoring and policy enforcement capabilities for all OAuth apps in app governance. 

In the Microsoft Defender Portal, we've merged all capabilities originally under **Cloud apps > OAuth apps under  App governance**, where you can manage all OAuth apps under a single pane of glass.

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

- **Behavior-generating policies no longer generate alerts** (Preview). Starting May 28, 2023, policies that generate *behaviors* in Microsoft Defender XDR advanced hunting don't generate alerts. The policies continue generating *behaviors* regardless of being enabled or disabled in the tenant's configuration.

    For more information, see [Investigate behaviors with advanced hunting (Preview)](behaviors.md).

- **Non-blockable applications** (Preview): To prevent users from accidentally causing downtime, Defender for Cloud Apps now prevents you from blocking business-critical Microsoft services.
    For more information, see [Govern discovered apps](governance-discovery.md#non-blockable-applications).


## Next steps

- For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[!INCLUDE [Open support ticket](includes/support.md)]


