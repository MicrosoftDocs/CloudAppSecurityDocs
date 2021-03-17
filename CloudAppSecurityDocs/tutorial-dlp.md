---
title: Discover and protect sensitive information in your organization tutorial
description: This tutorial describes the process to discover and protect sensitive information in Microsoft Cloud App Security.
ms.date: 02/24/2021
ms.topic: tutorial
---
# Tutorial: Discover and protect sensitive information in your organization

[!INCLUDE [Banner for top of topics](includes/banner.md)]

In a perfect world, all your employees understand the importance of information protection and work within your policies. In the real world, it's likely that a busy partner who frequently works with accounting information will inadvertently upload a sensitive document to your Box repository with incorrect permissions. A week later you realize your enterprise's confidential information was leaked to your competition.

To help you prevent this from happening, Microsoft Cloud App Security provides you with an expansive suite of DLP capabilities that cover the various data leak points that exist in organizations.

In this tutorial, you'll learn how to use Cloud App Security to discover potentially exposed sensitive data and apply controls to prevent their exposure:

> [!div class="checklist"]
>
> - [Discover your data](#phase-1-discover-your-data)
> - [Classify sensitive information](#phase-2-classify-sensitive-information)
> - [Protect your data](#phase-3-protect-your-data)
> - [Monitor and report on your data](#phase-4-monitor-and-report-on-your-data)

## How to discover and protect sensitive information in your organization

Our approach to information protection can be split into the following phases that allow you to protect your data through its full lifecycle, across multiple locations and devices.

![shadow IT lifecycle](media/tutorial-dlp-solution.png)

### Phase 1: Discover your data

1. **Connect apps**: The first step in discovering which data is being used in your organization, is to connect cloud apps used in your organization to Cloud App Security. Once connected, Cloud App Security can scan data, add classifications, and enforce policies and controls. Depending on how apps are connected affects how, and when, scans and controls are applied. You can connect your apps in one of the following ways:

    - **Use an app connector**: Our app connectors use the APIs supplied by app providers. They provide greater visibility into and control over the apps used in your organization. Scans are performed periodically (every 12 hours) and in real time (triggered each time a change is detected). For more information and instructions on how to add apps, see [Connecting apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).
    - **Use Conditional Access App Control**: Our Conditional Access App Control solution uses a reverse proxy architecture that is uniquely integrated with Azure Active Directory (AD) Conditional Access. Once configured in Azure AD, users will be routed to Cloud App Security where access and session policies are enforced to protect the data apps attempt to use. This connection method allows you to apply controls to [any app](proxy-deployment-any-app.md). For more information, see [Protect apps with Cloud App Security Conditional Access App Control](proxy-intro-aad.md).

1. **Investigate**: After you connect an app to Cloud App Security using its API connector, Cloud App Security scans all the files it uses. You can then go to the file investigation page (**Investigate** > **Files**) to get an overview of the files shared by your cloud apps, their accessibility, and their status. For more information, see [Investigate files](file-filters.md).

### Phase 2: Classify sensitive information

1. **Define which information is sensitive**: Before looking for sensitive information in your files, you first need to define what counts as sensitive for your organization. As part of our [data classification service](dcs-inspection.md), we offer over 100 out-of-the-box sensitive information types, or you can [create your own](/microsoft-365/compliance/create-a-custom-sensitive-information-type) to suit to your company policy. **Cloud App Security is natively integrated with Microsoft Information Protection** and the same sensitive types and labels are available throughout both services. So when you want to define sensitive information, head over to the Microsoft Information Protection portal to create them, and once defined they will be available in Cloud App Security. You can also use advanced classifications types such as fingerprint or Exact Data Match (EDM).

    For those of you that have already done the hard work of identifying sensitive information and applying the appropriate sensitivity labels, you can use those labels in your policies without having to scan the contents again.
1. **Enable Azure Information Protection integration**
    1. In Cloud App Security, under the settings cog, select the **Settings** page under the **System** heading.
    1. Under **Azure Information Protection**, select **Automatically scan new files for Azure Information Protection classification labels**.

    For more information, see [Azure Information Protection integration](azip-integration.md).
1. **Create policies to identify sensitive information in files**: Once you know the kinds of information you want to protect, it's time to create policies to detect them. Start by creating the following policies:

    **File policy**  
    Use this type of policy to scan the content of files stored in your API connected cloud apps in near real-time and data at rest. Files are scanned using one of our supported inspection methods including **Azure Information Protection encrypted content** thanks to its **native integration** with Cloud App Security.

    1. Go to **Control** > **Policies**, click **Create Policy**, and then select **File policy**.
    1. Under **Inspection method**, choose and configure one of the following classification services:

        - **[Data Classification Services](dcs-inspection.md)**: Uses classification decisions you've made across Office 365, Azure Information Protection, and Cloud App Security to provide a unified labeling experience. This is the preferred content inspection method as it provides a consistent and unified experience across Microsoft products.
        - **[Built-in DLP](content-inspection-built-in.md)**: Inspects files for sensitive information using our built-in DLP content inspection engine.
        - **[External DLP integration](icap-stunnel.md)**: For enterprises wishing to use their own third-party DLP solutions, Cloud App Security file policies can securely direct files for inspection to your external DLP solution via an ICAP server.

    1. For highly sensitive files, select **Create an alert** and choose the alerts you require, so that you are informed when there are files with unprotected sensitive information in your organization.
    1. Click **Create**.

    **Session policy**  
    Use this type of policy to scan and protect files in real time on access to:

    - **Prevent data exfiltration**: Block the download, cut, copy, and print of sensitive documents on, for example, unmanaged devices.
    - **Protect files on download**: Require documents to be labeled and protected with Azure Information Protection. This action ensures the document is protected and user access is restricted in a potentially risky session.
    - **Prevent the upload of unlabeled files**: Require a file to have the right label and protection before a sensitive file is uploaded, distributed, and used by others. With this action, you can ensure that unlabeled files with sensitive content are blocked from being uploaded until the user classifies the content.

    1. Go to **Control** > **Policies**, click **Create Policy**, and then select **Session policy**.
    1. Under **Session control type**, choose one of the options with DLP.
    1. Under **Inspection method**, choose and configure one of the following classification services:

        - **[Data Classification Services](dcs-inspection.md)**: Uses classification decisions you've made across Office 365, Azure Information Protection, and Cloud App Security to provide a unified labeling experience. This is the preferred content inspection method as it provides a consistent and unified experience across Microsoft products.
        - **[Built-in DLP](content-inspection-built-in.md)**: Inspects files for sensitive information using our built-in DLP content inspection engine.

    1. For highly sensitive files, select **Create an alert** and choose the alerts you require, so that you are informed when there are files with unprotected sensitive information in your organization.
    1. Click **Create**.

You should create as many policies as required to detect sensitive data in compliance with your company policy.

### Phase 3: Protect your data

So now you can detect files with sensitive information, but what you really want to do is protect that information from potential threats. Once you are aware of an incident, you can manually remediate the situation or you can use one of the automatic governance actions provided by Cloud App Security for securing your files. Actions include, but are not limited to, Azure Information Protection native controls, API provided actions, and real-time monitoring. The kind of governance you can apply depends on the type of policy you are configuring, as follows:

1. **[File policy governance](governance-actions.md#file-governance-actions) actions**: Uses the cloud app provider's API and our native integrations to secure files, including:
    - Trigger alerts and send email notifications about the incident
    - Manage labels applied to a file to enforce native Azure Information Protection controls
    - Change sharing access to a file
    - Quarantine a file
    - Remove specific file or folder permissions in Office 365
    - Move a file to the trash folder

1. **Session policy controls**: Uses reverse proxy capabilities to protect files, including:
    - Trigger alerts and send email notifications about the incident
    - [Monitor all activities](session-policy-aad.md#monitor-session): Explicitly allows the download or upload of files and monitors all related activities.
    - [Block](session-policy-aad.md#block-download): Explicitly blocks the download or upload of files. Use this option to protect your organization's sensitive files from exfiltration or infiltration from any device, including unmanaged devices.
    - [Protect](session-policy-aad.md#protect-download): Automatically applies a classification label to files that match the policy's file filters. Use this option to protect the download of sensitive files.

### Phase 4: Monitor and report on your data

Your policies are all in place to inspect and protect your data. Now, you'll want to [check your dashboard](daily-activities-to-protect-your-cloud-environment.md#check-the-dashboard) daily to see what new alerts have been triggered. It's a good place to keep an eye on the health of your cloud environment. Your dashboard helps you get a sense of what's happening and, if necessary, launch an [investigation](investigate.md).

One of the most effective ways of monitoring sensitive file incidents, is to head over to the **Policies** page, and review the matches for policies you have configured. Additionally, if you configured alerts, you should also consider regularly monitoring file alerts by heading over to the **Alerts** page, specifying the category as **DLP**, and reviewing which file-related policies are being triggered. Reviewing these incidents can help you fine-tune your policies to focus on threats that are of interest to your organization.

In conclusion, managing sensitive information in this way ensures that data saved to the cloud has maximal protection from malicious exfiltration and infiltration. Also, if a file is shared or lost, it can only be accessed by authorized users.

## See also

> [!div class="nextstepaction"]
> [Understanding file data and filters](file-filters.md)

> [!div class="nextstepaction"]
> [File policies](data-protection-policies.md)

> [!div class="nextstepaction"]
> [Content inspection](content-inspection.md)

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[!INCLUDE [Open support ticket](includes/support.md)]  
