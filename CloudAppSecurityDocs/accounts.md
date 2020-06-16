---
# required metadata

title: Visibility into cloud app accounts - Cloud App Security | Microsoft Docs
description: This article provides information about reviewing accounts from your connected apps.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 05/20/2020
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Accounts

*Applies to: Microsoft Cloud App Security*

Microsoft Cloud App Security gives you visibility into the accounts from your connected apps. After you connect Cloud App Security to an app using the App connector, Cloud App Security reads account information associated with connected apps. The Accounts page enables you to investigate those accounts, permissions, the groups they're members of, their aliases and the apps they're using. Additionally, when Cloud App Security detects a new account that wasn't previously seen in one of the connected apps - for example in activities or in file sharing - the account is added to the accounts list of that app. This enables you to have visibility into the activity of external users interacting with your cloud apps.

Admins can search for a specific user’s metadata or user’s activity. The **Users and accounts** page provides you with comprehensive details about the entities that are pulled from connected cloud applications. It also provides the user’s activity history and security alerts related to the user.

[!INCLUDE [Handle personal data](../includes/gdpr-intro-sentence.md)]

The **Users and accounts** page can be [filtered](#users-and-accounts-filters) to enable you to find specific accounts and to deep dive into different types of accounts, for example, you can filter for all External accounts that haven't been accessed since last year.

The **Users and accounts** page enables you to easily investigate your accounts, including the following issues:

* Check if any accounts have been inactive in a particular service for a long time (Maybe you should revoke the license for that user to that service)

* You can filter for the list of users with admin permissions
* You can search for users who are no longer part of your organization but may still have active accounts
* You can take [governance actions](#governance-actions) on the accounts such as suspend an app or go to the account settings page.
* You can see which accounts are included in each user group  
* You can see which apps are accessed by each account and which apps are deleted for specific accounts

    ![accounts screen](./media/accounts-page.png)

## Users and accounts filters

Following is a list of the account filters that can be applied. Most filters support multiple values as well as NOT, in order to provide you with a powerful tool for policy creation.  
  
<!--- **Account name**: The account name is the primary alias of the user, but other identifiers from other Microsoft accounts (Office 365 and Azure Active Directory) such as proxy addresses, aliases, SID are supported and consolidated beneath the primary alias. -->

* **Affiliation**: The affiliation is either **Internal** or **External**. To set which users and accounts are internal, under **Settings** make sure to set the **IP address range** of your internal organization. In the event that the account has admin permissions the icon in the Accounts table appears with the addition of the red tie. ![accounts admin icon](./media/accounts-admin-icon.png)

* **App**: You can filter for any API connected app being used by accounts in your organization.
* **Domain**: Enables you to filter for users in specific domains.
* **Groups**: Enables you to filter for members of user groups in Cloud App Security - both built-in user groups and imported user groups.
* **Instance**: Enables you to filter for members of a specific app instance.
* **Last seen**: The **last seen** filter enables you to find accounts that are dormant and whose users haven't performed any activities in a while.
* **Organization**: Enables you to filter for members of specific organizational groups defined in your connected apps.
* **Show Admins only**: Filters for accounts and users that are admins.
* **Status**: Filter based on user account status of N/A, staged, active, suspended, or deleted. A status of not available (N/A) is normal and may appear, for example, for anonymous accounts.
* **Type**: Enables you to filter to either the user or the account type.
* **User name**: Enables you to filter to specific users.

## Governance actions

From the **Users and account** page, you can take governance actions such as suspend an app or go to the account settings page. For a full list of governance actions, see the [governance log](governance-actions.md).

For example, if you identify a user that is compromised, you can apply the **Confirm user compromised** action to set the user risk level to high, causing the relevant policy actions defined in Azure Active Directory to be enforced. The action can be applied manually or using relevant [policies that support governance actions](governance-actions.md).

### To manually apply a user or account governance action

You can manually apply the **Confirm user compromised** action using one of the following methods:

* From the **Users and account** page, on the row where the relevant user or account appears, choose the three dots at the end of the row, and then choose **Confirm user compromised**.

* From the **User page**, select **User actions**, and then choose **Confirm user compromised**.

* **User name**: Enables you to filter to specific users.

## Next steps

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[!INCLUDE [Open support ticket](includes/support.md)]
