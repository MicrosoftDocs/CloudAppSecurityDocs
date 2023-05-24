---
title: Get started with app governance in Microsoft Defender for Cloud Apps
ms.date: 05/21/2023
ms.topic: quickstart
description: Step-by-step guide to help you quickly get started with app governance in Microsoft Defender for Cloud Apps.
---

# Get started with app governance in Defender for Cloud Apps

App governance solutions require a deep understanding of app behavior within an environment to identify and address activities that fall within a tolerance level that requires additional review to assess malicious intent.

When layered over Defender for Cloud Apps, app governance gives you in-depth governance against risky app behavior in your Microsoft 365 environment.

App governance provides additional security and policy management capabilities to monitor and govern app behaviors and quickly identify, alert, and protect from risky behaviors with data, users, and apps. App governance is also designed to secure OAuth-enabled apps registered on Azure AD.

Use app governance in Defender for Cloud Apps to:

- **Discover & manage the security posture of apps** – Get deep insights, visibility and reporting of all Microsoft 365 app behavior details

- **Provide secure access to apps, data & resources** – Manually/automatically disable access of Microsoft 365 apps showing risky characteristics/behavior

- **Defend against cyberthreats & anomalies** – Leverage machine learning-based detection of unusual app behavior (with other apps, high priority users and data) and remediate malicious app behavior

- **Protect the data in your cloud apps** – Detect apps that have uploaded/downloaded large amounts of Microsoft 365 data

Use the steps in this article to get started with app governance features in Microsoft Defender for Cloud Apps.

## Prerequisites

- If you haven’t already, [sign up for app governance](https://security.microsoft.com/cloudapps/settings?tabid=activateAppG) and complete the steps to add it to your tenant.  After you've signed up for app governance, you'll need to wait up to 10 hours to see and use the product.

    For more information, see [Turn on app governance for Microsoft Defender for Cloud Apps](app-governance-get-started.md). 

- Your sign-in account must have a supported [app governance administrator role](app-governance-get-started.md#roles) to view any app governance data.

- To use full functionality for app governance alerts you must have provisioned both Defender for Cloud Apps and Microsoft 365 Defender by accessing their respective portals at least once.

## Step 1: Get visibility and insights

Start by using the following steps to get visibility and insights about your apps:

1. **Sign in**: In your browser, go to the [app governance overview page](https://aka.ms/appgovernance).

1. **[Determine compliance posture](app-governance-visibility-insights-compliance-posture.md)**: App governance allows you to quickly assess the compliance posture of your apps and incidents in your tenant from the app governance **Overview** page in Microsoft 365 Defender. View details like how many overprivileged apps are in your tenant, the number of active incidents, the total Graph API data access, and more.

    > [!TIP]
> You can also view app governance-related recommendations in [Secure Score](https://security.microsoft.com/securescore?viewid=overview&tid=b5304409-74ae-42bf-a3e3-d62da4845129) to help you holistically manage your posture.

1. **[View your apps](app-governance-visibility-insights-view-apps.md)**: App governance allows you to quickly gain deep insights into the OAuth apps registered in Azure Active Directory that are accessing Microsoft 365 data in your tenant in the apps page. The apps page provides a list of these apps together with relevant app metadata and usage data.

    Sort by apps with high data usage or number of consents given, filter by high privileged apps, apps with unused permissions, or unverified publisher, and more.

1. **[Get detailed app information](app-governance-visibility-insights-view-apps.md#getting-detailed-information-on-an-app)**: Select an app in the list to get holistic app details all in one place. Investigate [priority account](/microsoft-365/admin/setup/priority-accounts) data usage for a specific app, trace exactly whose data is being accessed, and what permissions are being used and those that aren't used.

For more information, see [Get started with visibility and insights](app-governance-visibility-insights-get-started.md).

### Step 2: Implement app policies

App governance uses machine learning-based detection algorithms to detect anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve. Beyond this built-in detection capability (which we'll get into in more detail later), you can use a set of default policy templates or create your own app policies that generate other alerts.

These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.

App governance supports the following types of policies:

|Policy type  |Description  |
|---------|---------|
|**Predefined policies**     |  App governance is equipped with a set of predefined policies tailored to your environment. They allow you to start monitoring your apps even before you set up any policies. This ensures you're notified of any app anomalies early on.         |
|**User defined policies**     |     In addition to predefined policies, admins can also use the available conditions to create their custom policies or pick from the available recommended policies.    |


To see your list of current app policies, go to **Microsoft 365 Defender > App governance > Policies**. This will show you a list of all your policies in app governance. Built-in threat detection policies won't show up here, but you can read more about these [here](app-governance-anomaly-detection-alerts.md).

**To implement app policies**:

1. **[Work with predefined policies](app-governance-predefined-policies.md#working-with-predefined-policies)**:  App governance contains a set of out of the box policies to detect anomalous app behaviors. These policies are activated by default, but you can deactivate them if you choose to.

1. **[Create app policies:](app-governance-app-policies-create.md)** App governance offers over 20 policy conditions and templates for you to use. App policies in app governance are a way for you to:

    - Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.

    - Implement the app compliance policies for your organization.

1. **[Manage app policies](app-governance-app-policies-manage.md)**: To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:

    - Create new policies targeted at new apps

    - Change the status of an existing policy (active, inactive, audit mode)

    - Change the conditions of an existing policy

    - Change the actions of an existing policy for auto-remediation of alerts

For more information, see [Learn about app policies](app-governance-app-policies-overview.md).

### Step 3: Detect and remediate app threats

Use app governance to monitor the threat alerts that are being generated by built-in app governance detection methods for malicious app activities and policy-based alerts generated by active app policies that you create.

These alerts can indicate anomalies in app activity and when non-compliant, malicious, or risky apps are used. You can also use patterns in alerts to create new app policies or modify the settings of existing policies for more restrictive actions.

You can also remediate alerts, manually after investigation, or automatically through the action settings on active app policies.

**Do any of the following steps to detect and remediate threats**:

- **[Get started with app threat detection and remediation:](app-governance-detect-remediate-get-started.md)** App governance collects threat alerts that are generated by built-in, machine-learning-driven app governance detection methods based on malicious app activities and policy-based alerts generated by active app policies that you create.

- **[Monitor and respond to apps with unusual data usage:](app-governance-monitor-apps-unusual-data-usage.md)** App governance provides data usage information that can help you identify unwanted and potentially malicious app activity.

- **[Investigate anomaly detection alerts:](app-governance-anomaly-detection-alerts.md)** App governance provides security detections and alerts for malicious activities. The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.

- **[Remediate app threats:](app-governance-manage-alerts.md)** You remediate app threats to your Microsoft 365 tenant through the Alerts page of the Microsoft app governance section of the Microsoft 365 Defender.

For more information, see [Learn about app threat detection and remediation](app-governance-detect-remediate-overview.md).

## Next steps

For more information, see:

- [App governance in Microsoft 365](app-governance-manage-app-governance.md)

- [Defender for Cloud apps Ninja training](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-defender-for-cloud-apps-ninja-training-june-2022/ba-p/2751518)

- **Blogs**:

    - [Microsoft shifts to a comprehensive SaaS security solution - Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2023/02/15/microsoft-shifts-to-a-comprehensive-saas-security-solution/)

    - [Improve your app posture and hygiene using Microsoft Defender for Cloud Apps](https://techcommunity.microsoft.com/t5/microsoft-365-defender-blog/improve-your-app-posture-and-hygiene-using-microsoft-defender/ba-p/3742361)

- **Videos**:

    - [App governance video playlist](https://youtube.com/playlist?list=PLyhj1WZ29G66k4F_OZeMkQymRGyqHwZVp)

    - [Microsoft Mechanics Video on app governance](https://www.youtube.com/watch?v=KmE8LW_tJ1M).

    - [App Governance segment in the Security Summit video](https://mssecuritysummit.event.microsoft.com/Home/Security) starts at 11:50 mark. You need to register to view.

    - [App Governance is a Key Part of a Customers' Zero Trust Journey - YouTube](https://www.youtube.com/watch?v=XuGZu8ja134)
