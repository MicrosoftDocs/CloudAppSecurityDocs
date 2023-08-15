---
title: Protect apps with Conditional Access App Control
description: This article provides information about how the Defender for Cloud Apps Conditional Access App Control reverse proxy works.
ms.date: 03/21/2023
ms.topic: conceptual
---
# Protect apps with Microsoft Defender for Cloud Apps Conditional Access App Control

[!INCLUDE [Banner for top of topics](includes/banner.md)]

In today's workplace, it's often not enough to know what's happening in your cloud environment after the fact. You want to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. It's important to enable users in your organization to make the most of the services and tools available to them in cloud apps and let them bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time. Microsoft Defender for Cloud Apps integrates with any identity provider (IdP) to deliver these capabilities with access and session controls. If you're using Azure Active Directory (Azure AD) as your IdP, these controls are integrated and streamlined for a simpler and more tailored deployment built on Azure AD's [Conditional Access tool](/azure/active-directory/conditional-access/overview).

> [!NOTE]
>
> - In addition to a valid Defender for Cloud Apps license, to use Defender for Cloud Apps Conditional Access App Control, you also need an [Azure Active Directory P1 license](https://azure.microsoft.com/pricing/details/active-directory/), or the license required by your IdP solution.

## How it works

Conditional Access App Control uses a reverse proxy architecture and integrates with your IdP. When integrating with Azure AD Conditional Access, you can configure apps to work with Conditional Access App Control with just a few clicks, allowing you to easily and selectively enforce access and session controls on your organization's apps based on any condition in Conditional Access. The conditions define *who* (user or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a Conditional Access policy is applied to. After you've determined the conditions, you can route users to Defender for Cloud Apps where you can protect data with Conditional Access App Control by applying access and session controls.

Conditional Access App Control enables user app access and sessions to be monitored and controlled in real time based on access and session policies. Access and session policies are used within the Defender for Cloud Apps portal to further refine filters and set actions to be taken on a user. With the access and session policies, you can:

- **Prevent data exfiltration**: You can block the download, cut, copy, and print of sensitive documents on, for example, unmanaged devices.

- **Require authentication context**: You can reevaluate Azure AD Conditional Access policies when a sensitive action occurs in the session. For example, require multi-factor authentication on download of a highly confidential file.

- **Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be labeled and encrypted when you integrate with Microsoft Purview Information Protection. This action ensures the document is protected and user access is restricted in a potentially risky session.

- **Prevent upload of unlabeled files**: Before a sensitive file is uploaded, distributed, and used by others, it's important to make sure that the sensitive file has the label defined by your organization's policy. You can ensure that unlabeled files with sensitive content are blocked from being uploaded until the user classifies the content.

- **Block potential malware**: You can protect your environment from malware by blocking the upload of potentially malicious files. Any file that is uploaded or downloaded can be scanned against Microsoft threat intelligence and blocked instantaneously.

- **Monitor user sessions for compliance**: Risky users are monitored when they sign into apps and their actions are logged from within the session. You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future.

- **Block access**: You can granularly block access for specific apps and users depending on several risk factors. For example, you can block them if they're using client certificates as a form of device management.

- **Block custom activities**: Some apps have unique scenarios that carry risk, for example, sending messages with sensitive content in apps like Microsoft Teams or Slack. In these kinds of scenarios, you can scan messages for sensitive content and block them in real time.

### How session control works

Creating a session policy with Conditional Access App Control enables you to control user sessions by redirecting the user through a reverse proxy instead of directly to the app. From then on, user requests and responses go through Defender for Cloud Apps rather than directly to the app.

When a session is protected by proxy, all the relevant URLs and cookies are replaced by Defender for Cloud Apps. For example, if the app returns a page with links whose domains end with `myapp.com`, the link's domain is suffixed with something like `*.mcas.ms`, as follows:

|App URL|Replaced URL|
|---|---|
|`myapp.com`|`myapp.com.mcas.ms`|

This method doesn't require you to install anything on the device making it ideal when monitoring or controlling sessions from unmanaged devices or partner users.

> [!NOTE]
>
> - Our technology uses best-in-class patented heuristics to identify and control activities performed by the user in the target app. Our heuristics are designed to optimize and balance security with usability. In some rare scenarios, when blocking activities on the server-side renders the app unusable, we secure these activities only on the client-side, which makes them potentially susceptible to exploitation by malicious insiders.
> - Defender for Cloud Apps leverages Azure Data Centers around the world to provide optimized performance through geolocation. This means that a user's session may be hosted outside of a particular region, depending on traffic patterns and their location. However, to protect your privacy, no session data is stored in these data centers.
> - Our proxy servers do not store data at rest. When caching content, we follow the requirements laid out in [RFC 7234 (HTTP caching)](https://tools.ietf.org/html/rfc7234) and only cache public content.

## Managed device identification

Conditional Access App Control enables you to create policies that take into account whether a device is managed or not. To identify the state of a device, you can configure access and session policies to check for:

- Microsoft Intune Compliant devices [only available with Azure AD]
- Hybrid Azure AD joined devices [only available with Azure AD]
- Presence of client certificates in a trusted chain

### Intune compliant and Hybrid Azure AD Joined devices

Azure AD Conditional Access enables Intune compliant and Hybrid Azure AD Joined device information to be passed directly to Defender for Cloud Apps. From there, an access policy or a session policy can be developed that uses device state as a filter. For more information, see the [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).

> [!NOTE]
> Some browsers may require additional configuration such as installing an extension. For more information, see [Conditional Access browser support](/azure/active-directory/conditional-access/concept-conditional-access-conditions).

### Client-certificate authenticated devices

The device identification mechanism can request authentication from relevant devices using client certificates. You can either use existing client certificates already deployed in your organization or roll out new client certificates to managed devices. Make sure that the client certificate is installed in the user store and not the computer store. You then use the presence of those certificates to set access and session policies.

SSL client certificates are verified via a trust chain. You can upload an X.509 root or intermediate certificate authority (CA) formatted in the PEM certificate format. These certificates must contain the public key of the CA, which is then used to sign the client certificates presented during a session.

Once the certificate is uploaded and a relevant policy is configured, when an applicable session traverses Conditional Access App Control, the Defender for Cloud Apps endpoint requests the browser to present the SSL client certificates. The browser serves the SSL client certificates that are installed with a private key. This combination of certificate and private key is done by using the PKCS #12 file format, typically .p12 or .pfx.

When a client certificate check is performed, Defender for Cloud Apps checks for the following conditions:

1. The selected client certificate is valid and is under the correct root or intermediate CA.
1. The certificate isn't revoked (if CRL is enabled).

> [!NOTE]
>
> Most major browsers support performing a client certificate check. However, mobile and desktop apps often leverage built-in browsers that may not support this check and therefore affect authentication for these apps.

To configure a policy to leverage device management via client certificates:

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.

1. Under **Conditional Access App Control**, select **Device identification**.
1. Upload as many root or intermediate certificates as you require.

    > [!TIP]
    > To test how this works, you can use our sample root CA and client certificate, as follows:
    >
    > 1. Download the sample [root CA](https://github.com/microsoft/Microsoft-Cloud-App-Security/blob/master/Doc%20Assets/Proxy/Samples/SampleRootCA.crt.pem) and [client certificate](https://github.com/microsoft/Microsoft-Cloud-App-Security/blob/master/Doc%20Assets/Proxy/Samples/SampleClientCert.pfx).
    > 1. Upload the root CA to Defender for Cloud Apps.
    > 1. Install the client certificate (password=Microsoft) onto the relevant devices.

After the certificates are uploaded, you can create access and session policies based on **Device tag** and **Valid client certificate**.

## Supported apps and clients

Session and access controls can be applied to any interactive single sign-on, using the SAML 2.0 authentication protocol or, if you're using Azure AD, the Open ID Connect authentication protocol as well. Furthermore, if your apps are configured with Azure AD, you can also apply these controls to apps hosted on-premises configured with the [Azure AD App Proxy](/azure/active-directory/manage-apps/application-proxy). In addition, access controls can be applied to native mobile and desktop client apps.

Defender for Cloud Apps identifies Apps using information available in its Cloud App Catalog. Some organizations and users customize apps by adding plugins. However, in order for session controls to work correctly with these plugins, the associated custom domains must be added to the respective app in the catalog.

> [!NOTE]
> The Authenticator app, among other native client app sign-in flows, uses a non-interactive sign-in flow and cannot be used with access controls.

### Access controls

Many organizations that choose to use session controls for cloud apps to control in-session activities, also apply access controls to block the same set of native mobile and desktop client apps, thereby providing comprehensive security for the apps.

You can block access to native mobile and desktop client apps with access policies, by setting the **Client app** filter to **Mobile and desktop**. Some native client apps can be individually recognized, while others that are part of a suite of apps can only be identified as their top-level app. For example, apps like SharePoint Online can only be recognized by creating an access policy applied to Microsoft 365 apps.

> [!NOTE]
> Unless the **Client app** filter is specifically set to **Mobile and desktop**, the resulting access policy will only apply to browser sessions. The reason for this is to prevent inadvertently proxying user sessions, which may be a byproduct of using this filter. Whilst most major browsers support performing a client certificate check, some mobile and desktop apps use built-in browsers that may not support this check. Therefore, using this filter can affect authentication for these apps.

### Session controls

While session controls are built to work with any browser on any major platform on any operating system, we support [Microsoft Edge](https://www.microsoft.com/edge) (latest), [Google Chrome](https://www.google.com/chrome/) (latest), [Mozilla Firefox](https://www.mozilla.org/firefox/) (latest), or [Apple Safari](https://www.apple.com/safari/) (latest). Access to mobile and desktop apps can also be blocked or allowed.

> [!NOTE]
>
> - Defender for Cloud Apps uses Transport Layer Security (TLS) protocols 1.2+ to provide best-in-class encryption. Native client apps and browsers that do not support TLS 1.2+, will not be accessible when configured with session control. However, SaaS apps that use TLS 1.1 or lower will appear in the browser as using TLS 1.2+ when configured with Defender for Cloud Apps.
> - To apply session controls to portal.office.com, you must onboard Microsoft 365 admin center. For more information about onboarding apps, see [Onboard and deploy Conditional Access App Control for any app](proxy-deployment-any-app.md).

#### Pre-onboarded apps

Any web app configured using the [previously mentioned authentication protocols](#supported-apps-and-clients) can be onboarded to work with access and session controls. In addition, the following apps are already onboarded with both access and session controls for Azure Access Directory.

> [!NOTE]
> It's required to route your desired applications to access and session controls, and to perform a first login.

- AWS
- Box
- Concur
- CornerStone on Demand
- DocuSign
- Dropbox
- Egnyte
- GitHub
- Google Workspace
- HighQ
- JIRA/Confluence
- LinkedIn Learning
- Microsoft Azure DevOps (Visual Studio Team Services)
- Microsoft Azure portal
- Microsoft Dynamics 365 CRM
- Microsoft Exchange Online
- Microsoft OneDrive for Business
- Microsoft Power BI
- Microsoft SharePoint Online
- Microsoft Teams
- Microsoft Yammer
- Salesforce
- Slack
- Tableau
- Workday
- Workiva
- Workplace from Meta

If you're interested in a specific app being pre-onboarded, [send us details about the app](mailto:casfeedback@microsoft.com). Be sure to send the use case you're interested in for onboarding it.

## Known limitations
To learn more about security limitations, please contact our support team.

- **Browser plug-in limitation**  
Our current Conditional Access App Control session restrictions enforcement solution doesn't support native applications, since it requires some modification of the underlying application code. Browser extensions, similar to native apps, are pre-installed on the browser and so don't allow us to modify their code as needed and will break when their tokens are redirected through our proxy solution. As an administrator, you can define the default system behavior when a policy can't be enforced and choose between allowing access or totally blocking it.

- **Context loss**  
In the following applications, we've encountered scenarios where navigating to a link may result in loss of the full path of the link and typically the user lands on the home page of the app.
  - ArcGIS
  - GitHub
  - Microsoft Power Automate
  - Microsoft Power Apps
  - Workplace from Meta
  - ServiceNow

- **Session policies are valid for files up to 50 MB in size**  
Files with a size of up to 50MB are subject to session policies.
For example, an admin may define one of the following session policies:
  - Monitor file downloads for OneDrive app
  - Block file upload
  - Block download\upload of malware files

  A file of up to 50 MB will be handled based on the session policies in that case.
  For a larger file, tenant settings (Settings > Conditional Access App Control > Default behavior) determine if the file is allowed or blocked, regardless of the matching policies.

- **Inspections policies for information protection are valid for files up to 30 MB in size and 1 million characters**  
When a session policy to block file uploads or downloads based on information protection content inspection is applied, inspection is performed on files smaller than 30 MB and smaller than 1 million characters.
For example, an admin may define one of the following session policies:
  - Block file upload for files containing Social Security Number (SSN)
  - Protect file download for files containing PHI (Protected Health Information)
  - Block file download for with sensitivity label “very sensitive”

  In such cases, files larger than 30 MB or 1 million characters are not scanned and are treated according to the policy setting of **Always apply the selected action even if the data cannot be scanned.**
Here are some examples:
  - a TXT file, 1 MB size and 1 million characters: will be scanned
  - a TXT file, 2 MB size and 2 million characters: won't be scanned
  - a Word file composed of images and text, 4 MB size and 400 K characters: will be scanned
  - a Word file composed of images and text, 4 MB size and 2 million characters: won't be scanned
  - a Word file composed of images and text, 40 MB size and 400 K characters: won't be scanned

- **File upload limitation**

  If a session policy to block or monitor the upload of sensitive files is applied, then in these scenarios the user's attempts to upload files or folders using **drag & drop** will block the entire list of files and folders:
  - a folder that contains 100 or more files
  - a folder that contains at least one file and at least one subfolder
  - a folder that contains multiple subfolders
  - a selection of at least one file and at least one folder
  - a selection of multiple folders

    Here are a few examples:

  The security administrator defines the following policy: *Block upload of files containing PII to OneDrive*.
  - The user tries to upload a selection of 200 non-sensitive files using the file upload dialog. **Result:** the files are uploaded
  - The user tries to upload a selection of 200 non-sensitive files using drag & drop. **Result:** the files are blocked
  - The user tries to upload a selection of 200 files, some are sensitive, and some are not, using the file upload dialog. **Result:** the non-sensitive files are uploaded, the sensitive files are blocked
  - The user tries to upload a selection of 200 files, some are sensitive, and some are not, using drag & drop. **Result:** the whole set of files is blocked

## Next steps

For instructions on how to onboard your apps, see the appropriate document below:

- [Deploy Conditional Access App Control for catalog apps with Azure AD](proxy-deployment-aad.md)
- [Deploy Conditional Access App Control for catalog apps with non-Microsoft IdP](proxy-deployment-featured-idp.md)
- [Deploy Conditional Access App Control for custom apps using Azure Active Directory](proxy-deployment-any-app.md)
- [Deploy Conditional Access App Control for custom apps with non-Microsoft IdP](proxy-deployment-any-app-idp.md)

[!INCLUDE [Open support ticket](includes/support.md)]
