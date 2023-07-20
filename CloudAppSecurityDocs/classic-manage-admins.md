---
title: Classic portal -  Manage admin access
description: Classic portal -  This article provides instructions for setting access to the Defender for Cloud Apps portal for your admins.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Manage admin access

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Defender for Cloud Apps supports role-based access control. This article provides instructions for setting access to the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/) for your admins. For more information about assigning administrator roles, see the articles for [Azure Active Directory (Azure AD)](/azure/active-directory/roles/permissions-reference) and [Microsoft 365](/microsoft-365/admin/add-users/assign-admin-roles).

<a name="office-365-and-azure-ad-roles-with-access-to-cloud-app-security"></a>

## Microsoft 365 and Azure AD roles with access to Defender for Cloud Apps

> [!NOTE]
>
> - Microsoft 365 and Azure AD roles aren't listed in the Defender for Cloud Apps **Manage admin access** page. To assign roles in Microsoft 365 or Azure Active Directory, go to the relevant RBAC settings for that service.
> - Defender for Cloud Apps uses Azure Active Directory to determine the user's [directory level inactivity timeout setting](/azure/azure-portal/set-preferences#change-the-directory-timeout-setting-admin). If a user is configured in Azure Active Directory to never sign out when inactive, the same setting will apply in Defender for Cloud Apps as well.

By default, the following Microsoft 365 and [Azure AD](/azure/active-directory/roles/permissions-reference) admin roles have access to Defender for Cloud Apps:

- **Global administrator and Security administrator**: Administrators with **Full access** have full permissions in Defender for Cloud Apps. They can add admins, add policies and settings, upload logs and perform governance actions, access and manage SIEM agents.

- **Cloud App Security administrator**: Allows full access and permissions in Defender for Cloud Apps. This role grants full permissions to Defender for Cloud Apps, like the Azure AD **Global administrator** role. However, this role is scoped to Defender for Cloud Apps and won't grant full permissions across other Microsoft security products.

- **Compliance administrator**: Has read-only permissions and can manage alerts. Can't access Security recommendations for cloud platforms. Can create and modify file policies, allow file governance actions, and view all the built-in reports under Data Management.

- **Compliance data administrator**: Has read-only permissions, can create and modify file policies, allow file governance actions, and view all discovery reports. Can't access Security recommendations for cloud platforms.

> [!NOTE]
> As of August 28 2022, users who were assigned an Azure AD **Security Reader** role won't be able to manage the Microsoft Defender for Cloud Apps alerts. This change will be gradually rolled out to all customers over the next several weeks. To continue to manage alerts, the user's role should be updated to an Azure AD **Security Operator**.

- **Security operator**: Has read-only permissions and can manage alerts. These admins are restricted from doing the following actions:

  - Create policies or edit and change existing ones
  - Performing any governance actions
  - Uploading discovery logs
  - Banning or approving third-party apps
  - Accessing and viewing the IP address range settings page
  - Accessing and viewing any system settings pages
  - Accessing and viewing the Discovery settings
  - Accessing and viewing the App connectors page
  - Accessing and viewing the Governance log
  - Accessing and viewing the Manage snapshot reports page
  - Accessing and viewing SIEM agents

- **Security reader**: Has read-only permissions. These admins are restricted from doing the following actions:

  - Create policies or edit and change existing ones
  - Performing any governance actions
  - Uploading discovery logs
  - Banning or approving third-party apps
  - Accessing and viewing the IP address range settings page
  - Accessing and viewing any system settings pages
  - Accessing and viewing the Discovery settings
  - Accessing and viewing the App connectors page
  - Accessing and viewing the Governance log
  - Accessing and viewing the Manage snapshot reports page
  - Accessing and viewing SIEM agents
  
- **Global reader**: Has full read-only access to all aspects of Defender for Cloud Apps. Can't change any settings or take any actions.

### Roles and permissions

| Permissions                                                  | Global  Admin | Security  Admin | Compliance  Admin | Compliance  Data Admin | Security  Operator | Security  Reader | Global  Reader | PBI Admin | Cloud App Security admin |
| ------------------------------------------------------------ | ------------- | --------------- | ----------------- | ---------------------- | ------------------ | ---------------- | -------------- | --------- | ------------------- |
| Read alerts                                                  | ✔             | ✔               | ✔                 | ✔                      | ✔                  | ✔                | ✔              | ✔         | ✔                      |
| Manage alerts                                                | ✔             | ✔               | ✔                 | ✔                      | ✔                  |                  |                | ✔         | ✔                      |
| Read OAuth applications                                      | ✔             | ✔               | ✔                 | ✔                      | ✔                  | ✔                | ✔              | ✔         | ✔                      |
| Perform OAuth application actions                            | ✔             | ✔               |                   |                        |                    |                  |                | ✔         | ✔                      |
| Access discovered apps, the cloud app catalog, and other cloud discovery data | ✔             | ✔               | ✔                 | ✔                      | ✔                  | ✔                | ✔              |           | ✔                      |
| Configure API connectors | ✔             | ✔               |                   |                        | ✔                  |                  |                |           | ✔                      |
| Perform cloud discovery actions                              | ✔             | ✔               |                   |                        |                    |                  |                |           | ✔                      |
| Access files data and file policies                          | ✔             | ✔               | ✔                 | ✔                      | ✔                  | ✔                | ✔              | ✔         | ✔                      |
| Perform file actions                                         | ✔             | ✔               |                   |                        |                    |                  |                | ✔         | ✔                      |
| Access governance log                                        | ✔             | ✔               | ✔                 | ✔                      | ✔                  | ✔                | ✔              | ✔         | ✔                      |
| Perform governance log actions                               | ✔             | ✔               |                   |                        |                    |                  |                | ✔         | ✔                      |
| Access scoped discovery governance log                       | ✔             | ✔               |                   |                        |                    |                  |                |           | ✔                      |
| Read policies                                                | ✔             | ✔               | ✔                 | ✔                      | ✔                  | ✔                | ✔              | ✔         | ✔                      |
| Perform all policy actions                                   | ✔             | ✔               |                   |                        |                    |                  |                | ✔         | ✔                      |
| Perform file policy actions                                  | ✔             | ✔               | ✔                 | ✔                      |                    |                  |                |           | ✔                      |
| Perform OAuth policy actions                                 | ✔             | ✔               |                   |                        |                    |                  |                | ✔         | ✔                      |
| View manage admin access                                     | ✔             | ✔               | ✔                 | ✔                      | ✔                  | ✔                | ✔              |           | ✔                      |
| Manage admins and activity privacy                           | ✔             | ✔               |                   |                        |                    |                  |                |           | ✔                      |

<a name="built-in-cloud-app-security-admin-roles"></a>

## Built-in admin roles in Defender for Cloud Apps

The following specific admin roles can be configured in the Defender for Cloud Apps portal:

- **Global administrator**: Has **Full access** similar to the Azure AD Global administrator role but only to Defender for Cloud Apps.

- **Compliance administrator**: Grants the same permissions as the Azure AD Compliance administrator role but only to Defender for Cloud Apps.

- **Security reader**: Grants the same permissions as the Azure AD Security reader role but only to Defender for Cloud Apps.

- **Security operator**: Grants the same permissions as the Azure AD Security operator role but only to Defender for Cloud Apps.

- **App/instance admin**: Has full or read-only permissions to all of the data in Defender for Cloud Apps that deals exclusively with the specific app or instance of an app selected. For example, you give a user admin permission to your Box European instance. The admin will see only data that relates to the Box European instance, whether it's files, activities, policies, or alerts:

  - Activities page - Only activities about the specific app
  - Alerts - Only alerts relating to the specific app
  - Policies - Can view all policies and if assigned full permissions can edit or create only policies that deal exclusively with the app/instance
  - Accounts page - Only accounts for the specific app/instance
  - App permissions - Only permissions for the specific app/instance
  - Files page - Only files from the specific app/instance
  - Conditional Access App Control - No permissions
  - Cloud Discovery activity - No permissions
  - Security extensions - Only permissions for API token with user permissions
  - Governance actions - Only for the specific app/instance
  - Security recommendations for cloud platforms - No permissions

- **User group admin**: Has full or read-only permissions to all of the data in Defender for Cloud Apps that deals exclusively with the specific groups assigned to them. For example, if you assign a user admin permissions to the group "Germany - all users", the admin can view and edit information in Defender for Cloud Apps only for that user group. The User group admin has the following access:

  - Activities page - Only activities about the users in the group
  - Alerts - Only alerts relating to the users in the group
  - Policies - Can view all policies and if assigned full permissions can edit or create only policies that deal exclusively with users in the group
  - Accounts page - Only accounts for the specific users in the group
  - App permissions – No permissions
  - Files page – No permissions
  - Conditional Access App Control - No permissions
  - Cloud Discovery activity - No permissions
  - Security extensions - Only permissions for API token with users in the group
  - Governance actions - Only for the specific users in the group
  - Security recommendations for cloud platforms - No permissions

    > [!NOTE]
    >
    > - To assign groups to user group admins, you must first [import user groups](user-groups.md) from connected apps.
    > - You can only assign user group admins permissions to imported Azure AD groups.

- **Cloud Discovery global admin**: Has permission to view and edit all Cloud Discovery settings and data. The Global Discovery admin has the following access:

  - Settings
    - System settings - View only
    - Cloud Discovery settings - View and edit all (anonymization permissions depend on whether it was allowed during role assignment)
  - Cloud Discovery activity - full permissions
  - Alerts - view and manage only alerts related to the relevant Cloud Discovery report
  - Policies - Can view all policies and can edit or create only Cloud Discovery policies
  - Activities page - No permissions
  - Accounts page - No permissions
  - App permissions – No permissions
  - Files page – No permissions
  - Conditional Access App Control - No permissions
  - Security extensions - Creating and deleting their own API tokens
  - Governance actions - Only Cloud Discovery related actions
  - Security recommendations for cloud platforms - No permissions
  - IP ranges - No permissions

- **Cloud Discovery report admin**:

  - Settings
    - System settings - View only
    - Cloud Discovery settings - View all (anonymization permissions depend on whether it was allowed during role assignment)
  - Cloud Discovery activity - read permissions only
  - Alerts – view only alerts related to the relevant Cloud Discovery report
  - Policies - Can view all policies and can create only Cloud Discovery policies, without the possibility to govern application (tagging, sanction and unsanctioned)
  - Activities page - No permissions
  - Accounts page - No permissions
  - App permissions – No permissions
  - Files page – No permissions
  - Conditional Access App Control - No permissions
  - Security extensions - Creating and deleting their own API tokens
  - Governance actions – view only actions related to the relevant Cloud Discovery report
  - Security recommendations for cloud platforms - No permissions
  - IP ranges - No permissions

> [!NOTE]
> The built-in Defender for Cloud Apps admin roles only provide access permissions to Defender for Cloud Apps.

## Override admin permissions

If you want to override an administrator's permission from Azure AD or Microsoft 365, you can do so by manually adding the user to Defender for Cloud Apps and assigning the user permissions. For example, if you want to assign Stephanie, who is a Security reader in Azure AD to have **Full access** in Defender for Cloud Apps, you can add her manually to Defender for Cloud Apps and assign her **Full access** to override her role and allow her the necessary permissions in Defender for Cloud Apps. Note that it is not possible to override Azure AD roles that grant Full access (Global administrator, Security administrator, and Cloud App Security administrator).

## Add additional admins

You can add additional admins to Defender for Cloud Apps without adding users to Azure AD administrative roles. To add additional admins, perform the following steps:

> [!IMPORTANT]
>
> - Access to the **Manage admin access** page is available to members of the Global Administrators, Security Administrators, Compliance Administrators, Compliance Data Administrators, Security Operators, Security Readers and Global Readers groups.
> - Only Azure AD Global Administrators or Security Administrators can edit the **Manage admin access** page and grant other users access to Defender for Cloud Apps.

1. Select the settings cog ![settings icon.](media/classic-settings-icon.png "settings icon") and then **Manage admin access**.

1. Select the plus icon to add the admins who should have access to Defender for Cloud Apps. Provide an email address of a user from inside your organization.

    > [!NOTE]
    > If you want to add external Managed Security Service Providers (MSSPs) as administrators of your Defender for Cloud Apps portal, make sure you first [invite them as a guest](#invite-external-admins) to your organization.

    ![add admins.](media/classic-add-admin.png)

1. Next, select the drop-down to set what type of role the admin has, **Global admin**, **Security reader**, **Compliance admin**, **App/Instance admin**, **User group admin**, **Cloud Discovery global admin**, or **Cloud Discovery report admin**. If you select **App/Instance admin**, select the app and instance for the admin to have permissions for.

    >[!NOTE]
    > Any admin, whose access is limited, that attempts to access a restricted page or perform a restricted action will receive an error that they don't have permission to access the page or perform the action.

1. Select **Add admin**.

## Invite external admins

Defender for Cloud Apps enables you to invite external admins (MSSPs) as administrators of your organization's (MSSP customer) Defender for Cloud Apps portal. To add MSSPs, make sure Defender for Cloud Apps is enabled on MSSPs tenant and then add them as [Azure AD B2B collaboration users](/azure/active-directory/external-identities/add-users-administrator) in the MSSPs customers Azure portal. Once added, MSSPs can be configured as administrators and assigned any of the roles available in Defender for Cloud Apps.

### To add MSSPs to the MSSP customer Defender for Cloud Apps portal

1. Add MSSPs as a guest in the MSSP customer directory using the steps under [Add guest users to the directory](/azure/active-directory/external-identities/add-users-administrator#add-guest-users-to-the-directory).
1. Add MSSPs and assign an administrator role in the MSSP customer Defender for Cloud Apps portal using the steps under [Add additional admins](#add-additional-admins). Provide the same external email address used when adding them as guests in the MSSP customer directory.

### Access for MSSPs to the MSSP customer Defender for Cloud Apps portal

By default, MSSPs access their Defender for Cloud Apps tenant through the following URL: `https://portal.cloudappsecurity.com`.

MSSPs however, will need to access the MSSP customer Defender for Cloud Apps portal using a tenant-specific URL in the following format: `https://portal.cloudappsecurity.com?tid=customer_tenant_id`.

MSSPs can use the following steps to obtain the MSSP customer portal tenant ID and then use the ID to access the tenant-specific URL:

1. As an MSSP, sign in to Azure AD with your credentials.

1. Switch directory to the MSSP customer's tenant.
1. Select **Azure Active Directory** > **Properties**. You'll find the MSSP customer tenant ID in the **Tenant ID** field.
1. Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://portal.cloudappsecurity.com?tid=customer_tenant_id`.

## Admin activity auditing

Defender for Cloud Apps lets you export a log of admin sign-in activities and an audit of views of a specific user or alerts carried out as part of an investigation.

To export a log, perform the following steps:

1. In the **Manage admins access** page, select **Export admin activities**.

1. Specify the required time range.

1. Select **Export**.

## Next steps

> [!div class="nextstepaction"]
> [Set up Cloud Discovery](set-up-cloud-discovery.md)
