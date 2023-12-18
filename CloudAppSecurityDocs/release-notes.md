---
title: What's new 
description: This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.
ms.date: 12/17/2023
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

## January 2024

### Automatic redirection for the classic Defender for Cloud APps portal (Preview)

The classic Microsoft Defender for Cloud Apps portal experience and functionality have been converged into the Microsoft Defender XDR Portal. As of January 9th, 2024, customers using the classic Defender for Cloud Apps portal with Preview features are automatically redirected to Microsoft Defender XDR, with no option to revert back to the classic portal.

For more information, see:

- [Microsoft Defender for Cloud Apps in Microsoft Defender XDR](/microsoft-365/security/defender/microsoft-365-security-center-defender-cloud-apps)
- [Preview features in Microsoft Defender for Cloud Apps](preview-features.md)

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


## Next steps

- For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[!INCLUDE [Open support ticket](includes/support.md)]


