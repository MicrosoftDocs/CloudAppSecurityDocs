---
title: Get Started with app governance
ms.date: 03/16/2022
ms.topic: how-to
description: Get started with app governance capabilities to govern your apps.
---

# Get started with app governance

[Microsoft 365 security & compliance licensing guidance for app governance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## Prerequisites

To get started using the app governance add-on to Defender for Cloud Apps, first check that you satisfy the following prerequisites:

1. Verify your account has the [appropriate level of licensing](#licensing-for-app-governance). App governance is an add-on feature for Defender for Cloud Apps, and so Defender for Cloud Apps must be present in your account as either a standalone product or as part of the various license packages.
1. You must have one of the [administrator roles](#administrator-roles) listed below to access the app governance pages in the portal.
1. To activate the free trial today, your organization's billing address can be in any region except Brazil, South Korea, Switzerland, Norway, South Africa, or United Arab Emirates.

If you satisfy the prerequisites, and are an existing Defender for Cloud Apps customer, you can navigate to the [sign up page for the free trial](https://aka.ms/appgovernancetrial) and complete the steps to add app governance to your tenant.

If you aren't already a Defender for Cloud Apps customer, you can sign up for a free trial by navigating to the [sign up page for the free trial for app governance](https://aka.ms/appgovernancetrial) and complete the steps to add a free trial of app governance to your tenant. Then navigate to the [sign up page for the free trial for Defender for Cloud Apps](https://www.microsoft.com/security/business/cloud-apps-defender) and complete the steps for sign-up.

[![Sign up for the free trial of app governance](media/app-governance/large-app-governance-banner.png)](https://aka.ms/appgovernancetrial)

To purchase a subscription for app governance, go to [Buy app governance](https://aka.ms/buyappgovernance) or reach out to your sales account team.

### Licensing for app governance

Before you get started with app governance, you should confirm your [Microsoft 365 admin center - subscriptions](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/subscriptions) and any add-ons.

You can purchase app governance as an add-on to any license that entitles you to use Defender for Cloud Apps. For a list of these licenses, see the [Defender for Cloud Apps licensing datasheet](https://aka.ms/mcaslicensing).

To use app governance in compliance with the terms of service, purchase an add-on license for each protected user after the trial ends. Each protected user must have both the Defender for Cloud Apps license and one of the app governance add-on licenses listed below:

- Microsoft Defender for Cloud Apps (standalone)
- Enterprise Mobility + Security E5/A5
- Microsoft 365 E5/A5
- Microsoft 365 E5/A5 Security
- Microsoft 365 E5/A5 Compliance
- Microsoft 365 E5/A5 Information Protection and Governance
- Microsoft 365 F5 Security add-on
- Microsoft 365 F5 Compliance add-on
- Microsoft 365 F5 Security + Compliance add-on

### Administrator roles

> [!NOTE]
> Only Global Admin, Company Admin, or Billing Admin role can activate the app governance free trial.

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

Here are the capabilities for each role.

| Role | Read the dashboard | Read all apps |Read policies | Create, update, or delete policies | Read alerts | Update alerts | Read settings | Update settings | Read Remediation | Update Remediation |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| Application Administrator | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) |
| Cloud Application Administrator | ![Check mark](media\checkmark.png) | | | | | | | | | |
| Company or Global Administrator | ![Check mark.](media\checkmark.png) | ![Check mark.](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) |
| Compliance Administrator | ![Check mark.](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) |  | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | |
| Compliance Data Administrator | ![Check mark.](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) |  | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | |
| Global Reader  | ![Check mark.](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) |  | ![Check mark](media\checkmark.png) |  | ![Check mark](media\checkmark.png) |  | | |
| Security Administrator | ![Check mark.](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) |  | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | |
| Security Operator | ![Check mark.](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) | |
| Security Reader  | ![Check mark.](media\checkmark.png) | ![Check mark](media\checkmark.png) | ![Check mark](media\checkmark.png) |  | ![Check mark](media\checkmark.png) |  | ![Check mark](media\checkmark.png) |  | ![Check mark](media\checkmark.png) | |
|||||||||| | |

For more information about each role, see [Administrator role permissions](/azure/active-directory/roles/permissions-reference).

## Enable Defender for Cloud Apps sync

To enable app governance sync with Defender for Cloud Apps, follow these steps:

1. Ensure Office 365 is connected in Defender for Cloud Apps.
1. Ensure Office 365 Azure AD apps are enabled.
1. Go to your Defender for Cloud Apps portal – [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)
1. Select the gear icon (top-right corner) and select **Settings**.
1. Under **Threat Protection**, select **App Governance**.
1. Select **Enable App Governance integration**, and then select **Save**.

To verify the integration with Defender for Cloud Apps is active, look for the app governance policies listed below to appear in Defender for Cloud Apps. The new policies might take few minutes to appear once integration is enabled.

- Microsoft 365 OAuth app Reputation
- Microsoft 365 OAuth Phishing Detection
- Microsoft 365 OAuth App Governance

> [!NOTE]
> App governance alerts will not flow to Microsoft 365 Defender until app governance is enabled in Defender for Cloud Apps and you have provisioned both Defender for Cloud Apps and Microsoft 365 Defender by accessing their respective portals at least once.
