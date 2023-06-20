---
title: Connect DocuSign
description: This article describes how to connect Microsoft Defender for Cloud Apps to your existing DocuSign environment via the App Connector APIs. 
ms.date: 02/23/2023
ms.topic: how-to
---

# Connect DocuSign to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing DocuSign environment using the App Connector APIs. This connection gives you visibility into and control over your organization’s DocuSign use.

[!INCLUDE [security-posture-management-connector](includes/security-posture-management-connector.md)]


## Prerequisites

- DocuSign Enterprise Pro account plan with Monitor API enabled.
  - For more information about DocuSign Monitor API, see [How to get monitoring data | DocuSign](https://developers.docusign.com/docs/monitor-api/how-to/get-monitoring-data/) and [Enable DocuSign Monitor for your organization | DocuSign](https://developers.docusign.com/docs/monitor-api/how-to/enable-monitor/).

- DNS domains used in your organization should be claimed and validated in your DocuSign organization. For more information on claiming and validating domains, see [Domains | DocuSign](https://support.docusign.com/en/guides/org-admin-guide-claim-domain/)

- The DocuSign user used for logging into DocuSign must be mapped to the user role 'Docusign Administrator' and must be an organization admin of one organization only. For more information, see the prerequisite role in [How to get monitoring data | DocuSign](https://developers.docusign.com/docs/monitor-api/how-to/get-monitoring-data/) and [Organization Administrators - DocuSign Admin for Organization Management | DocuSign Support Center](https://support.docusign.com/en/guides/org-admin-guide-org-admins).
- Due to DocuSign’s API limitation, in order to have SaaS Security Posture management (SSPM) support there's a need to reconnect it with additional permissions: **account_read account_write** and **user_read organization_read** .
- The DocuSign account must be mapped to an organization. For more information, see:

  - Create new organization: [Organizations - DocuSign Admin for Organization Management | DocuSign Support Center](https://support.docusign.com/en/guides/org-admin-guide-create-org)

  - Link account to an existing organization: [Managing Accounts - DocuSign Admin for Organization Management | DocuSign Support Center](https://support.docusign.com/en/guides/org-admin-guide-accounts)

  - DocuSign Organization Admin guide: [DocuSign Admin for Organization Management (PDF) | DocuSign Support Center](https://support.docusign.com/guides/org-admin-guide).

## How to connect DocuSign to Defender for Cloud Apps

### Configure DocuSign

1. Sign into a DocuSign account that is mapped to your organization (you should be an account Admin for that account).  

1. Go to **Settings** and then **Apps and keys**.

1. Copy the User ID and Account Base URI. You'll need them later.

    ![DocuSign settings.](media/docusign-settings.png)

### Configure Defender for Cloud Apps

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**.

1. In the **App connectors** page, select **+Connect an app**, and then select **DocuSign**.

1. In the window that appears, give the connector a descriptive name, and then select **Next**.

    ![Connect DocuSign.](media/connect-docusign.png)

1. In the next screen, enter the following:

    - User ID: the User ID that you copied earlier.
    - Endpoint: the Account Base URI you copied earlier.

    ![Enter DocuSign details.](media/docusign-details.png)

1. Select **Next**.
1. In the next screen, select **Connect DocuSign**.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**. Make sure the status of the connected App Connector is **Connected**.

> [!NOTE]
> SaaS Security Posture Management (SSPM) data will be shown in the Microsoft 365 Defender portal on the **Secure Score** page. For more information, see [Security posture management for SaaS apps](/defender-cloud-apps/security-saas).

## Limitations

1. Only active DocuSign users will be shown in Defender for Cloud Apps.
   - If a user isn't active in all of the DocuSign accounts mapped to the connected DocuSign organization, the user will be shown as deleted in Defender for Cloud Apps.
1. For SaaS Security Posture Management (SSPM) support, the provided credentials must have these permissions - **account_read account_write** and **user_read organization_read**.
1. Defender for Cloud Apps won't show whether a user is an administrator or not.
1. The DocuSign activities that will be shown in Defender for Cloud Apps are the activities at the account level (of every account that is mapped to the connected DocuSign organization) and at the organization level.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps by using policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
