---
title: Turn on app governance in Microsoft Defender for Cloud Apps
ms.date: 05/21/2023
ms.topic: how-to
description: Get started with app governance capabilities to govern your apps in  Microsoft Defender for Cloud Apps.
---

# Turn on app governance for Microsoft Defender for Cloud Apps

> [!NOTE]
> Starting June 1, 2023, app governance is included with your Defender for Cloud Apps license.
>
> If you are currently an app governance trial customer, use the steps described in this article to turn on app governance with a Defender for Cloud Apps license.
>
> **Take this action before July 31, 2023 to continue using it without any interruption.**

## Prerequisites

Before you start, verify that you satisfy the following prerequisites:

- Microsoft Defender for Cloud Apps must be present in your account as either a standalone product or as part of the various [license](#licensing) packages.

    If you aren't already a Defender for Cloud Apps customer, you can [sign up for a free trial](https://www.microsoft.com/security/business/cloud-apps-defender).

- You must have [one of the appropriate roles](#roles) to turn on app governance and access it.

- Your organization's billing address must be in a region **other than** Brazil, South Korea, Switzerland, Norway, South Africa, or United Arab Emirates.

- Your organization must use the commercial cloud, and not a government cloud. App governance isn't yet available in government clouds.

## Turn on app governance

If your organization satisfies the [prerequisites](#prerequisites), go to [Microsoft 365 Defender > Settings > Cloud Apps > App governance](https://security.microsoft.com/cloudapps/settings) and select **Use app governance**. For example:

:::image type="content" source="media/app-governance-get-started/app-governance-service-status1.png" alt-text="Screenshot of the App governance toggle in Microsoft 365 Defender." lightbox="media/app-governance-get-started/app-governance-service-status1.png":::

After you've signed up for app governance, you'll need to wait up to 10 hours to see and use the product.

If you're unable to see the app governance option in the settings page, it might be due to one or more of the following reasons:

- App governance isn't yet supported in your region.

- Your organization is in a government cloud.

- We're unable to serve you at the moment due to capacity constraints.

You can join the waitlist and provide your consent, so that we can turn on app governance for your organization automatically when app governance becomes available for you. When we turn on app governance, we'll notify you by email.

For example:

:::image type="content" source="media/app-governance-get-started/app-governance-service-status.png" alt-text="Screenshot of the App governance waitlist option." lightbox="media/app-governance-get-started/app-governance-service-status.png":::

## Current trial customers

If you're currently running a free trial of app governance and want to use it without interruption, go to [Microsoft 365 Defender > Settings > Cloud Apps > App governance](https://security.microsoft.com/cloudapps/settings) and switch on the app governance toggle before **July 31, 2023**. 

If you want to opt out of app governance, no action is needed, and app governance will automatically turn off after **July 31, 2023**. Your data will be deleted permanently in accordance with our data retention policies. To keep a copy of your app and policy data, make sure to export them manually from the app governance pages before July 31, 2023.

## Licensing

App governance is available to organizations with a valid Defender for Cloud Apps license, including:

- Microsoft Defender for Cloud Apps (standalone)
- Enterprise Mobility & Security E5/A5
- Microsoft 365 Security E5/A5/F5
- Microsoft 365 E5/A5/F5
- Microsoft Purview E5/A5/F5
- Microsoft 365 F5 Security & Compliance

## Roles

You must have one of these roles to turn on app governance:

- Global Admin
- Company Admin
- Security Admin          
- Compliance Admin  
- Compliance Data Admin
- Cloud App Security admin

One of the following administrator roles is required to see app governance pages or manage policies and settings:

- Application Administrator
- Cloud Application Administrator
- Company or Global Administrator
- Compliance Administrator
- Compliance Data Administrator
- Global Reader
- Security Administrator
- Security Operator
- Security Reader (read-only)

The following table lists the app governance capabilities for each role.

| Role | Read the dashboard | Read all apps |Read policies | Create, update, or delete policies | Read alerts | Update alerts | Read settings | Update settings | Read Remediation | Update Remediation |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| **Application Administrator** | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) |
| **Cloud Application Administrator** | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) |
| **Company or Global Administrator** | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) |
| **Compliance Administrator** | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) |
| **Compliance Data Administrator** | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) |
| **Global Reader**  | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) |  | ![Check mark.](media\checkmark.png) |  | ![Check mark.](media\checkmark.png) |  | | |
| **Security Administrator** | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) |
| **Security Operator** | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | |
| **Security Reader**  | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) |  | ![Check mark.](media\checkmark.png) |  | ![Check mark.](media\checkmark.png) |  | ![Check mark.](media\checkmark.png) | |
|||||||||| | |

For more information about each role, see [Administrator role permissions](/azure/active-directory/roles/permissions-reference).

> [!NOTE]
> App governance alerts will not flow to Microsoft 365 Defender or show up in app governance until you have provisioned both Defender for Cloud Apps and Microsoft 365 Defender by accessing their respective portals at least once.

## Next steps

[Get started with app governance in Defender for Cloud Apps](app-governance-trial-user-guide.md)

