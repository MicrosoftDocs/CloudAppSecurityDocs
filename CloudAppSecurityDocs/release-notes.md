---
title: What's new 
description: This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.
ms.date: 04/14/2024
ms.topic: overview
---

# What's new in Microsoft Defender for Cloud Apps

*Applies to: Microsoft Defender for Cloud Apps*

This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.

RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://aka.ms/mda/rss`

For more information on what's new with other Microsoft Defender security products, see:

- [What's new in Microsoft Defender XDR](/microsoft-365/security/defender/whats-new)
- [What's new in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/whats-new-in-microsoft-defender-endpoint)
- [What's new in Microsoft Defender for Identity](/defender-for-identity/whats-new)

For news about earlier releases, see [Archive of past updates for Microsoft Defender for Cloud Apps](release-note-archive.md).

## April 2024

### Enable data encryption from the Microsoft Defender portal

Now you can complete the process for encrypting Defender for Cloud Apps data at rest with your own key by enabling data encrpytion from the **Settings** area of the Microsoft Defender portal.

This feature is now limited on the classic Microsoft Defender for Cloud Apps portal, and is available only from the Microsoft Defender portal.

For more information, see [Encrypt Defender for Cloud Apps data at rest with your own key (BYOK)](ems-cloud-app-security-govt-service-byok.md).

## March 2024

### New log collector version released

We released a new version of a log collector with the latest vulnerability fixes. The new version is `columbus-0.272.0-signed.jar`, and the image name is `mcaspublic.azurecr.io/public/mcas/logcollector`, with the tag `latest/0.272.0`.

Changes include upgrading dependencies, such as:

- amazon-corretto
- ubuntu
- libssl
- oauthlib
- logback
- setuptools

For more information, see [Advanced log collector management](log-collector-advanced-management.md#update-the-log-collector-version).
 
### Podman supported for automatic log collection (Preview)

Microsoft Defender for Cloud Apps log collector now supports [Podman](https://docs.podman.io/en/latest/), and you can configure automatic log collection on Podman for continuous reporting with Defender for Cloud Apps. 

Automatic log collection is supported using a Docker container on multiple operating systems. For Linux distributions using RHEL version 7.1 and higher, you must use Podman as the container's runtime system.

For more information, see [Configure automatic log upload using Podman](discovery-linux-podman.md).

### New anomaly data for the advanced hunting CloudAppEvents table

Defender for Cloud Apps users who use advanced hunting in the Microsoft Defender portal can now use the new *LastSeenForUser* and *UncommonForUser* columns columns for queries and detections rules. Using this data assists in ruling out false positives and finding anomalies.

For more information, see [Advanced Hunting "CloudAppEvents" Data schema](/microsoft-365/security/defender/advanced-hunting-cloudappevents-table).

### New threat detections for Microsoft Copilot for Microsoft 365

Defender for Cloud Apps now provides new detections for risky user activities in Microsoft Copilot for Microsoft 365 with the Microsoft 365 connector.

- Related alerts are shown together with other Microsoft Defender XDR alerts, in the Microsoft Defender portal.
- Copilot for Microsoft 365 activities are available in the Defender for Cloud Apps activity log.
- In the Microsoft Defender portal's **Advanced hunting** page, Copilot for Microsoft 365 activities are available in the **CloudAppEvents** table, under the **Microsoft Copilot for Microsoft 365** application.

For more information, see:

- [Get started with Microsoft Copilot for Microsoft 365](/microsoft-365-copilot/microsoft-365-copilot-setup)
- [How Defender for Cloud Apps helps protect your Microsoft 365 environment](protect-office-365.md)
- [Investigate alerts in Microsoft Defender XDR](/microsoft-365/security/defender/investigate-alerts)
- [Defender for Cloud Apps Activity log](activity-filters.md)
- [Proactively hunt for threats with advanced hunting](/microsoft-365/security/defender/advanced-hunting-overview)
- [CloudAppEvents table in the advanced hunting schema](/microsoft-365/security/defender/advanced-hunting-cloudappevents-table)

### Data in motion protection for Edge for Business users (Preview)

Defender for Cloud Apps users who use Microsoft Edge for Business and are subject to session policies are now protected directly from within the browser. In-browser protection reduces the need for proxies, improving both security and productivity.

Protected users experience a smooth experience with their cloud apps, without latency or app compatibility issues, and with a higher level of security protection.

In-browser protection is turned on by default, and is being gradually rolled out across tenants, starting early in March 2024.

For more information, see [In-browser protection with Microsoft Edge for Business (Preview)](in-browser-protection.md), [Protect apps with Microsoft Defender for Cloud Apps Conditional Access App Control](proxy-intro-aad.md), and [Session policies](session-policy-aad.md).
  
### Defender for Cloud Apps in the Microsoft Defender portal now available to all Defender for Cloud Apps roles

The Defender for Cloud Apps experience in the Microsoft Defender portal is now available for all Defender for Cloud Apps roles, including the following roles that were previously limited:

- App/Instance admin
- User group admin
- Cloud Discovery global admin
- Cloud Discovery report admin

For more information, see [Built-in admin roles in Defender for Cloud Apps](manage-admins.md#built-in-admin-roles-in-defender-for-cloud-apps).

## February 2024

### SSPM support for more connected apps in general availability

Defender for Cloud Apps provides you with security recommendations for your SaaS applications to help you prevent possible risks. These recommendations are shown via Microsoft Secure Score once you have a connector to an application.

Defender for Cloud Apps has now enhanced its SSPM support in general availability by including the following apps:

- [Atlassian](protect-atlassian.md)
- [Dropbox](protect-dropbox.md)
- [Zendesk](protect-zendesk.md)

SSPM is also now supported for [Google Workspace](protect-google-workspace.md) in General Availability.

> [!NOTE]
> If you already have a connector to one of these apps, your score in Secure score might automatically update accordingly.

For more information, see:

- [SaaS security posture management (SSPM)](security-saas.md)
- [User, app governance, and security configuration visibility](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#user-app-governance-and-security-configuration-visibility)
- [Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score)

### New App governance alerts for Credential Access and Lateral Movement

We've added the following new alerts for App governance customers:

- [Application initiating multiple failed KeyVault read activity with no success](app-governance-anomaly-detection-alerts.md#application-initiating-multiple-failed-keyvault-read-activity-with-no-success)
- [Dormant OAuth App predominantly using MS Graph or Exchange Web Services recently seen to be accessing ARM workloads](app-governance-anomaly-detection-alerts.md#dormant-oauth-app-predominantly-using-ms-graph-or-exchange-web-services-recently-seen-to-be-accessing-arm-workloads)

For more information, see [App governance in Microsoft Defender for Cloud Apps](app-governance-manage-app-governance.md).

## January 2024

### SSPM support for multiple instances of the same app (Preview)

Defender for Cloud Apps now supports SaaS security posture management (SSPM) across multiple instances of the same app. For example, if you have multiple instances of AWS, you can configure Secure Score recommendations for each instance individually. Each instance will show up as a separate item on the **App Connectors** page. For example:

:::image type="content" source="media/security-saas-choose-secure-score-main-instance.png" alt-text="Screenshot of the Turn on Secure Score recommendations option." lightbox="media/classic-security-saas-choose-secure-score-main-instance.png":::

For more information, see [SaaS security posture management (SSPM)](security-saas.md).

### Limitation removed for the number of files that can be controlled for uploading in session policies (Preview)

Session policies now support control over uploading folders with more than 100 files, with no limit to the number of files that can be included in the upload.

For more information, see [Protect apps with Microsoft Defender for Cloud Apps Conditional Access App Control](proxy-intro-aad.md).

### Automatic redirection for the classic Defender for Cloud Apps portal (Preview)

The classic Microsoft Defender for Cloud Apps portal experience and functionality have been converged into the Microsoft Defender XDR Portal. As of January 9th, 2024, customers using the classic Defender for Cloud Apps portal with Preview features are automatically redirected to Microsoft Defender XDR, with no option to revert back to the classic portal.

For more information, see:

- [Microsoft Defender for Cloud Apps in Microsoft Defender XDR](/microsoft-365/security/defender/microsoft-365-security-center-defender-cloud-apps)
- [Preview features in Microsoft Defender for Cloud Apps](preview-features.md)

## December 2023

### New IP addresses for portal access and SIEM agent connection

The IP addresses used for portal access and SIEM agent connections have been updated. Make sure to add the new IPs to your firewall's allowlist accordingly to keep the service fully functional. For more information, see:

- [Portal access network requirements](network-requirements.md#portal-access)
- [SIEM agent connection network requirements](network-requirements.md#siem-agent-connection)

### Backlog period alignments for initial scans

We've aligned the backlog period for initial scans after connecting a new app to Defender for Cloud Apps. The following app connectors all have an initial scan backlog period of seven days:

- [Dropbox](protect-dropbox.md)
- [Salesforce](protect-salesforce.md)
- [ServiceNow ](protect-servicenow.md)
- [Okta](protect-okta.md)

For more information, see [Connect apps to get visibility and control with Microsoft Defender for Cloud Apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

### SSPM support for more connected apps

Defender for Cloud Apps provides you with security recommendations for your SaaS applications to help you prevent possible risks. These recommendations are shown via [Microsoft Secure Score](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) once you have a connector to an application.

Defender for Cloud Apps has now enhanced its SSPM support by including the following apps: (Preview)

- [Atlassian](protect-atlassian.md)
- [Dropbox](protect-dropbox.md)
- [NetDocuments](protect-netdocuments.md)
- [Workplace](protect-workplace.md)
- [Zendesk](protect-zendesk.md)

SSPM is also now supported for [Google Workspace](protect-google-workspace.md) in General Availability.

> [!NOTE]
> If you already have a connector to one of these apps, your score in Secure score might automatically update accordingly.

For more information, see:

- [SaaS security posture management (SSPM)](security-saas.md)
- [User, app governance, and security configuration visibility](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#user-app-governance-and-security-configuration-visibility)
- [Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score)

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

For more information, see [Diagnose and troubleshoot with the Admin View toolbar](troubleshooting-proxy.md#diagnose-and-troubleshoot-with-the-admin-view-toolbar) and [Test mode](troubleshooting-proxy.md#test-mode).

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

## Next steps

- For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[!INCLUDE [Open support ticket](includes/support.md)]


