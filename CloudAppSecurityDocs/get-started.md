---
title: Get started
description: This quickstart outlines the process for getting Defender for Cloud Apps up and running so you have cloud app use, insight, and control.
ms.date: 01/29/2023
ms.topic: quickstart
---

# Get started with Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This quickstart provides you with steps for getting up and running with Defender for Cloud Apps. Microsoft Defender for Cloud Apps can help you take advantage of the benefits of cloud applications while maintaining control of your corporate resources. It works by improving visibility of cloud activity and helping to increase the protection of corporate data. In this article, we walk you through the steps you take to set up and work with Microsoft Defender for Cloud Apps.

## Prerequisites

- In order for your organization to be in compliance for licensing Microsoft Defender for Cloud Apps, you must obtain a license for every user protected by Microsoft Defender for Cloud Apps. For pricing details, see the [Microsoft 365 licensing datasheet](https://aka.ms/M365EnterprisePlans).

    For activation support, see [Get support for Microsoft 365 for business](/microsoft-365/admin/get-help-support)

    >[!NOTE]
    >Microsoft Defender for Cloud Apps is a security tool and therefore doesn't require Microsoft 365 productivity suite licenses. For Microsoft 365 Cloud App Security (Microsoft Defender for Cloud Apps only for Microsoft 365), see [What are the differences between Microsoft Defender for Cloud Apps and Microsoft 365 Cloud App Security?](editions-cloud-app-security-o365.md).

- After you have a license for Defender for Cloud Apps, you'll receive an email with activation information and a link to the Defender for Cloud Apps portal.

- To set up Defender for Cloud Apps, you must be a Global Administrator or a Security Administrator in Azure Active Directory or Microsoft 365. It's important to understand that a user who is assigned an admin role will have the same permissions across all of the cloud apps that your organization has subscribed to. This is regardless of whether you assign the role in the Microsoft 365 admin center, or in the Azure classic portal, or by using the Azure AD module for [Windows PowerShell](/microsoft-365/enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true). For more information, see [Assign admin roles](/microsoft-365/admin/add-users/assign-admin-roles) and [Assigning administrator roles in Azure Active Directory](/azure/active-directory/roles/permissions-reference).

- To run the Defender for Cloud Apps portal, use Internet Explorer 11, Microsoft Edge (latest), Google Chrome (latest), Mozilla Firefox (latest), or Apple Safari (latest).

## Access the portal

 You can access Defender for Cloud Apps through the **[Microsoft 365 Defender portal](https://security.microsoft.com)**, as follows:

1. In the [Microsoft 365 Defender Portal](https://security.microsoft.com/),  under **Cloud Apps**, you'll find the various components of Defender for Cloud Apps:

    :::image type="content" source="media/defender-for-cloud-apps-menu.png" alt-text="Defender for Cloud Apps menu." lightbox="media/defender-for-cloud-apps-menu.png":::

## Step 1. Set instant visibility, protection, and governance actions for your apps

How to page: [Set instant visibility, protection, and governance actions for your apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)

Required task: Connect apps

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **Connected Apps**, select **App Connectors**.
1. Select the **+Connect an app** to add an app and then select an app.
1. Follow the configuration steps to connect the app.

**Why connect an app?**
After you connect an app, you can gain deeper visibility so you can investigate activities, files, and accounts for the apps in your cloud environment.

## Step 2. Protect sensitive information with DLP policies

How to page: [Protect sensitive information with DLP policies](policies-information-protection.md)

Recommended task: Enable file monitoring and create file policies

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **Information Protection**, select **Files**.
1. Select **Enable file monitoring** and then select **Save**.
1. If you use sensitivity labels from Microsoft Purview Information Protection, under **Information Protection**, select **Microsoft Information Protection**.
1. Select the required settings and then select **Save**.
1. In [Step 3](#step-3-control-cloud-apps-with-policies), create [File policies](data-protection-policies.md) to meet your organizational requirements.

> [!TIP]
> You can view files from your connected apps by browsing to **Cloud Apps** > **Files** in the Microsoft 365 Defender portal.

**Migration recommendation**  
We recommend using Defender for Cloud Apps sensitive information protection in parallel with your current Cloud Access Security Broker (CASB) solution. Start by [connecting the apps you want to protect](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) to Microsoft Defender for Cloud Apps. Since API connectors use out-of-band connectivity, no conflict will occur. Then progressively migrate your [policies](control-cloud-apps-with-policies.md) from your current CASB solution to Defender for Cloud Apps.

> [!NOTE]
> For third-party apps, verify that the current load does not exceed the app's maximum number of allowed API calls.

## Step 3. Control cloud apps with policies

How to page: [Control cloud apps with policies](control-cloud-apps-with-policies.md)

Required task: Create policies

### To create policies

1. In the Microsoft 365 Defender portal, under **Cloud Apps**, choose **Policies** -> **Policy templates**.
1. Choose a policy template from the list, and then select the **+** icon to create the policy.
1. Customize the policy (select filters, actions, and other settings), and then choose **Create**.
1. Under **Cloud Apps**, choose **Policies** -> **Policy management**, to choose the policy and see the relevant matches (activities, files, alerts).

> [!TIP]
> To cover all your cloud environment security scenarios, create a policy for each **risk category**.

### How can policies help your organization?

You can use policies to help you monitor trends, see security threats, and generate customized reports and alerts. With policies, you can create governance actions, and set data loss prevention and file-sharing controls.

## Step 4. Set up Cloud Discovery

How to page: [Set up Cloud Discovery](set-up-cloud-discovery.md)

Required task: Enable Defender for Cloud Apps to view your cloud app use

1. [Integrate with Microsoft Defender for Endpoint](mde-integration.md) to automatically enable Defender for Cloud Apps to monitor your Windows 10 and Windows 11 devices inside and outside your corporation.
1. If you use [Zscaler, integrate](zscaler-integration.md) it with Defender for Cloud Apps.
1. To achieve full coverage, create a continuous Cloud Discovery report

    1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
    1. Under **Cloud Discovery**, choose **Automatic log upload**.
    1. On the **Data sources** tab, add your sources.
    1. On the **Log collectors** tab, configure the log collector.

**Migration recommendation**  
We recommend using Defender for Cloud Apps discovery in parallel with your current CASB solution. Start by configuring automatic firewall log upload to Defender for Cloud Apps [log collectors](discovery-docker.md). If you use Defender for Endpoint, in Microsoft 365 Defender, make sure you [turn on the option](mde-integration.md#how-to-integrate-microsoft-defender-for-endpoint-with-defender-for-cloud-apps) to forward signals to Defender for Cloud Apps. Configuring Cloud Discovery won't conflict with the log collection of your current CASB solution.

### To create a snapshot Cloud Discovery report

1. In the Microsoft 365 Defender portal, under **Cloud Apps**, choose **Cloud discovery**.
1. In the top right-hand corner, select **Actions** -> **Create Cloud Discovery snapshot report**.

### Why should you configure Cloud Discovery reports?

Having visibility into shadow IT in your organization is critical.
After your logs are analyzed, you can easily find which cloud apps are being used, by which people, and on which devices.

## Step 5. Deploy Conditional Access App Control for catalog apps

How to page: [Deploy Conditional Access App Control for catalog apps with Azure AD](proxy-deployment-aad.md)

Recommended task: Deploy Conditional Access App Control for catalog apps

1. Configure your IdP to work with Defender for Cloud Apps. If you have Azure AD, you can leverage inline controls such as *Monitor only* and *Block downloads* which will work for any catalog app out of the box.
1. Onboard apps onto access and session controls.
    1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
    1. Under **Connected apps**, select *Conditional Access App Control apps**.
    1. Sign in to each app using a user scoped to the policy
    1. Refresh the **Conditional Access App Control apps** page and to view the app.
1. Verify the apps are configured to use access and session controls

To configure session controls for custom line-of-business apps, non-featured SaaS apps, and on-premises apps, see [Deploy Conditional Access App Control for custom apps using Azure Active Directory](proxy-deployment-any-app.md).

**Migration recommendation**  
Using Conditional Access App Control in parallel with another CASB solution can potentially lead to an app being proxied twice, causing latency or other errors. Therefore, we recommended progressively migrating apps and policies to Conditional Access App Control, creating the relevant session or access policies in  Defender for Cloud Apps as you go.

## Step 6. Personalize your experience

How to page: [Personalize your experience](mail-settings.md)

Recommended task: Add your organization details

### To enter email settings

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **System**, select **Mail settings**.
1. Under **Email sender identity**, enter your email addresses and display name.
1. Under **Email design**, upload your organization's email template.

### To set admin notifications

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Microsoft 365 Defender**.
1. Select **Email notifications**.
1. Configure the methods you want to set for system notifications.

### To customize the score metrics

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **Cloud Discovery**, choose **Score metrics**.
1. Configure the importance of various risk values.
1. Choose **Save**.

Now the risk scores given to discovered apps are configured precisely according to your organization needs and priorities.

### Why personalize your environment?

Some features work best when they're customized to your needs.
Provide a better experience for your users with your own email templates. Decide what notifications you receive and customize your risk score metric to fit your organization's preferences.

## Step 7. Organize the data according to your needs

How to page: [Working with IP ranges and tags](ip-tags.md)

Recommended task: Configure important settings

### To create IP address tags

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **System**, select **IP address ranges**.
1. Select **+ Add IP address range**  to add an IP address range.
1. Enter the IP range **Name**, **IP address ranges**, **Category**, and **Tags**.
1. Choose **Create**.

    Now you can use IP tags when you create policies, and when you filter and create continuous reports.

### To create continuous reports

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **Cloud Discovery**, choose **Continuous reports**.
1. Choose **Create report**.
1. Follow the configuration steps.
1. Choose **Create**.

Now you can view discovered data based on your own preferences, such as business units or IP ranges.

### To add domains

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.
1. Under **System**, choose **Organization details**.
1. Add your organization's internal domains.
1. Choose **Save**.

### Why should you configure these settings?

These settings help give you better control of features in the console. With IP tags, it's easier to create policies that fit your needs, to accurately filter data, and more. Use Data views to group your data into logical categories.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md).

[!INCLUDE [Open support ticket](includes/support.md)].
