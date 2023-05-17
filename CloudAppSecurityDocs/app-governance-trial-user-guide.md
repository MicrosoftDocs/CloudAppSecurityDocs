---
title: App governance trial user guide
ms.date: 03/16/2023
ms.topic: conceptual
description: Step-by-step guide to help you quickly get started with the app governance add-on trial
---

# Quick guide: App governance capability in Defender for Cloud Apps

Welcome to the step-by-step guide to help you quickly get started with app governance in Microsoft Defender for Cloud Apps.

Before getting into the details of setting up app governance, and recommended key features to try, let's review the relationship between the app governance capability and Microsoft Defender for Cloud Apps.

## Managing risks from apps

You can deploy three broad solution types to control and protect from risks posed by non-Microsoft and Line of Business (LOB) cloud apps:

- **App Access:** solutions like Azure Active Directory that register your apps, manage access rights and permissions for your apps, and define which users can access which app.

- **App Use:** solutions like [Microsoft Defender for Cloud Apps](https://aka.ms/defender-for-cloud-apps) (formerly known as Microsoft Cloud App Security) that discover and assess cloud apps, protects sensitive information in apps, identify risky user behavior in apps, enforce policies to control activity, and detect and remediate threats.

- **App Behavior:** solutions like the Microsoft app governance capability that requires a deep understanding of app behavior within an environment to identify and address activities that fall within a tolerance level that requires additional review to assess malicious intent.

These three solutions together provide a three-pronged approach to holistically protect against app threats across the app lifecycle.

:::image type="content" source="media/app-governance/three-solutions.png" alt-text="Three solutions to manage risk from apps.":::

## Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps is a SaaS security solution that provides visibility and control into an organization's SaaS applications. There are various ways to deploy Defender for Cloud Apps, including log collection, API connectors, and reverse proxy. It allows you to govern risky apps, protect sensitive data, and gain sophisticated analytics to identify and combat cyberthreats across all your Microsoft and non-Microsoft cloud services. Specifically for cloud apps across the organization, you can:

- Discover and gain visibility into risky SaaS apps

- Protect against cyberthreats and alert on suspicious behavior using user behavioral analytics

- Protect sensitive information using API connecters and real-time controls for both Microsoft and non-Microsoft apps

- Surface misconfigurations in your cloud apps and provide remediation actions to elevate the overall security posture in your organization

:::image type="content" source="media/app-governance/defender-cloud-apps-protections.png" alt-text="Ways that Defender for Cloud Apps protects.":::

For information about licensing, see the [Microsoft Defender for Cloud Apps product page](https://www.microsoft.com/security/business/siem-and-xdr/microsoft-defender-cloud-apps?rtc=1).

## What is the app governance capability in Defender for Cloud Apps?

App governance gives you in-depth governance against risky app behavior in your Microsoft 365 environment. It provides additional security and policy management capabilities to monitor and govern app behaviors and quickly identify, alert, and protect from risky behaviors with data, users, and apps. It's designed to secure OAuth-enabled apps registered on Azure AD.
:::image type="content" source="media/app-governance/app-governance-add-on.png" alt-text="App governance add on.":::

App governance offers an in-depth Microsoft 365 platform-level view & control of app behavior.

- **Discover & manage the security posture of apps** – Get deep insights, visibility and reporting of all Microsoft 365 app behavior details

- **Provide secure access to apps, data & resources** – Manually/automatically disable access of Microsoft 365 apps showing risky characteristics/behavior

- **Defend against cyberthreats & anomalies** – Leverage machine learning-based detection of unusual app behavior (with other apps, high priority users and data) and remediate malicious app behavior

- **Protect the data in your cloud apps** – Detect apps that have uploaded/downloaded large amounts of Microsoft 365 data

> [!NOTE]
> This guide is focused only on the app governance capability in Defender for Cloud Apps and will provide you with recommendations to help you get started.

## Get started with app governance

If you haven’t already, [sign up for app governance](https://security.microsoft.com/cloudapps/settings?tabid=activateAppG) and complete the steps to add it to your tenant.  After you've signed up for app governance, you'll need to wait up to 24 hours to see and use the product.

>[!NOTE]
>To use full functionality for app governance alerts you must have provisioned both Defender for Cloud Apps and Microsoft 365 Defender by accessing their respective portals at least once.

Once app governance is enabled for you, try these recommended actions:

### Step 1: [Get visibility and insights](app-governance-visibility-insights-get-started.md)

The first place to get started is the app governance overview page at <https://aka.ms/appgovernance>. Your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#roles) to view any app governance data.

1. [Determine compliance posture](app-governance-visibility-insights-compliance-posture.md): App governance allows you to quickly assess the compliance posture of your apps and incidents in your tenant from the app governance Overview page in Microsoft 365 Defender. You can see details like how many overprivileged apps are in your tenant, number of active incidents, total Graph API data access, and more.

   You'll also be able to see app governance-related recommendations in [Secure Score](https://security.microsoft.com/securescore?viewid=overview&tid=b5304409-74ae-42bf-a3e3-d62da4845129) to help you holistically manage your posture.

1. [View your apps](app-governance-visibility-insights-view-apps.md): App governance allows you to quickly gain deep insights into the OAuth apps registered in Azure Active Directory that are accessing Microsoft 365 data in your tenant in the apps page. The apps page provides a list of these apps together with relevant app metadata and usage data.

    You can sort by apps with high data usage or number of consents given, filter by high privileged apps, apps with unused permissions, or unverified publisher, and more.

1. [Get detailed app information](app-governance-visibility-insights-view-apps.md#getting-detailed-information-on-an-app): By selecting an app in the list, you can get holistic app details all in one place. Investigate [priority account](/microsoft-365/admin/setup/priority-accounts) data usage for a specific app, trace exactly whose data is being accessed, and what permissions are being used (plus those that aren't used).

### Step 2: [Implement app policies](app-governance-app-policies-overview.md)

App governance uses machine learning-based detection algorithms to detect anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve. Beyond this built-in detection capability (which we'll get into in more detail later), you can use a set of default policy templates or create your own app policies that generate other alerts.

These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.

There are two types of policies in app governance:

- **Predefined policies** - App governance is equipped with a set of predefined policies tailored to your environment. They allow you to start monitoring your apps even before you set up any policies. This ensures you're notified of any app anomalies early on.  

- **User defined policies** - In addition to predefined policies, admins can also use the available conditions to create their custom policies or pick from the available recommended policies.

To see your list of current app policies, go to **Microsoft 365 Defender > App governance > Policies**. This will show you a list of all your policies in app governance. Built-in threat detection policies won't show up here, but you can read more about these [here](app-governance-anomaly-detection-alerts.md).

1. [Working with predefined policies](app-governance-predefined-policies.md#working-with-predefined-policies):  App governance contains a set of out of the box policies to detect anomalous app behaviors. These policies are activated by default, but you can deactivate them if you choose to.

1. [Create app policies:](app-governance-app-policies-create.md) App governance offers over 20 policy conditions and templates for you to use. App policies in app governance are a way for you to:

    - Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.

    - Implement the app compliance policies for your organization.

1. [Manage app policies](app-governance-app-policies-manage.md): To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:

    - Create new policies targeted at new apps

    - Change the status of an existing policy (active, inactive, audit mode)

    - Change the conditions of an existing policy

    - Change the actions of an existing policy for auto-remediation of alerts

### Step 3: [Detect and remediate app threats](app-governance-detect-remediate-overview.md)

With app governance, you can:

- Easily monitor the threat alerts that are being generated by built-in app governance detection methods for malicious app activities and policy-based alerts generated by active app policies that you create. These alerts can indicate anomalies in app activity and when non-compliant, malicious, or risky apps are used. You can also use patterns in alerts to create new app policies or modify the settings of existing policies for more restrictive actions.

- Easily remediate alerts either manually after investigation or automatically through the action settings on active app policies.

Try these actions:

- [Get started with app threat detection and remediation:](app-governance-detect-remediate-get-started.md) App governance collects threat alerts that are generated by built-in, machine-learning-driven app governance detection methods based on malicious app activities and policy-based alerts generated by active app policies that you create.

- [Monitor and respond to apps with unusual data usage:](app-governance-monitor-apps-unusual-data-usage.md) App governance provides data usage information that can help you identify unwanted and potentially malicious app activity.

- [Investigate anomaly detection alerts:](app-governance-anomaly-detection-alerts.md) App governance provides security detections and alerts for malicious activities. The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.

- [Remediate app threats:](/defender-cloud-apps/app-governance-manage-alerts) You remediate app threats to your Microsoft 365 tenant through the Alerts page of the Microsoft app governance section of the Microsoft 365 Defender.

## Resources for the Microsoft Defender for Cloud Apps app governance capability

- Documentation and overview video: [App governance in Microsoft 365](app-governance-manage-app-governance.md)

- Microsoft Mechanics Video on app governance: see [this video](https://www.youtube.com/watch?v=KmE8LW_tJ1M).

- Training: [Defender for Cloud apps Ninja training](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-defender-for-cloud-apps-ninja-training-june-2022/ba-p/2751518)

- Videos: [YouTube play list for AppG](https://youtube.com/playlist?list=PLyhj1WZ29G66k4F_OZeMkQymRGyqHwZVp)

- Security Summit video: [App Governance segment](https://mssecuritysummit.event.microsoft.com/Home/Security) starts at 11:50 mark. You need to register to view.

- Microsoft shifts to a comprehensive SaaS security solution - [Microsoft shifts to a comprehensive SaaS security solution - Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2023/02/15/microsoft-shifts-to-a-comprehensive-saas-security-solution/)

- App posture and hygiene - [Improve your app posture and hygiene using Microsoft Defender for Cloud Apps](https://techcommunity.microsoft.com/t5/microsoft-365-defender-blog/improve-your-app-posture-and-hygiene-using-microsoft-defender/ba-p/3742361)

- App governance is a key part of customers’ zero trust journey - [App Governance is a Key Part of a Customers' Zero Trust Journey - YouTube](https://www.youtube.com/watch?v=XuGZu8ja134)


