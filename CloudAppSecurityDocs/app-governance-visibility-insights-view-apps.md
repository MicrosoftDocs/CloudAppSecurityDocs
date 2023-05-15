---
title: View your apps
ms.date: 04/30/2023
ms.topic: how-to
description: View your apps.
---

# View your apps

App governance allows you to quickly gain deep insights into the Microsoft 365 OAuth apps in your tenant. For example, you can see:

- A list of OAuth-enabled apps in the tenant, together with relevant app metadata and usage data.
- App details with deeper insights and information by selecting an app in the list.

## Getting a list of all the apps in your tenant

For a summary of apps in your tenant, go to **Microsoft 365 Defender > App governance > Apps**.

![The app governance app summary page in Microsoft 365 Defender.](media/app-governance-visibility-insights-view-apps/appg-cc-apps.png)

>[!NOTE]
> Your sign-in account must have one of [these roles](app-governance-get-started.md#roles) to view any app governance data.
>

You will see a list of apps and this information:

- **App name**: The display name of the app as registered on Azure AD
- **App status**: Shows whether the app is enabled or disabled, and if disabled by whom
- **Graph API access**: Shows whether the app has at least one Graph API permission
- **Permission type**: Shows whether the app has application (app only), delegated, or mixed permissions
- **Consent type**: Shows whether the app consent has been given at the user or the admin level, and the number of users whose data is accessible to the app
- **Publisher**: Publisher of the app and their verification status
- **Last modified**: Date and time when registration information was last updated on Azure AD
- **Last used**: The last time the app signed in

  - Due to data history or app scope constraints, some apps will show *Over 30 days ago*. These apps haven't signed in in the last 30 days, but we don’t currently have an exact last sign-in date.
  - Apps which don't have a last sign in date available will have *Not available* in this column
- **Credential unused since**: The last time the app signed in using the credential it hasn’t used the longest

  - Due to data history or app scope constraints, some apps will show *Over 30 days ago*. These apps haven't signed in in the last 30 days, but we don’t currently have an exact last sign-in date.
  - Apps which don’t have a last sign-in date available will have *Not available* in this column
  - Apps with *No credentials* don’t have any credentials assigned to the app.
- **Credential expiration**: Earliest upcoming expiration date for all app credentials

  - Apps with *No credentials* don’t have any credentials assigned to the app.
- **Added on**: Shows the date and time when the app was registered to Azure AD and assigned a service principal
- **Permission usage**: Shows whether the app has any unused Graph API permissions in the last 90 days
- **Data usage**: Total data downloaded or uploaded by the app in the last 30 days
- **Privilege level**
- **Certification**: Indicates if an app meets stringent security and compliance standards set by Microsoft 365 or if its publisher has publicly attested to its safety
- **App ID**
- **Sensitivity label accessed**: Sensitivity labels on content accessed by the app
- **Service accessed**: Microsoft 365 services accessed by the app
- **Community use**: Shows you how popular the app is across all your users (*common*, *uncommon*, *rare*)
- **Consent grants**: Shows you all app consent grants in the last 30 days
- **App activities**: Shows you all app activities in the last 30 days


App governance sorts the app list alphabetically by **App name** by default. To sort the list by another app attribute, select the attribute name.

You can also select **Search** to search for an app by name.

## Getting detailed information on an app

For detailed information on a specific app in your tenant, go to **Microsoft 365 Defender > App governance > Apps > *app name***

> [!div class="mx-imgBorder"]
>![See additional data on the app such as the date first consented and the App ID.](media/app-governance-visibility-insights-view-apps/image2.png)

> [!div class="mx-imgBorder"]
>![See the data usage by the app in the tenant and plot the data usage for Exchange, SharePoint, OneDrive, and Teams resources.](media/app-governance-visibility-insights-view-apps/data-usage.png)

> [!div class="mx-imgBorder"]
>![See a list of users who are using the app, whether they're a priority account, and the amount of data downloaded and uploaded.](media/app-governance-visibility-insights-view-apps/users.png)

> [!div class="mx-imgBorder"]
>![See a summary and list of the Graph API and legacy permissions granted to the app, consent type, and whether they are in use.](media/app-governance-visibility-insights-view-apps/permissions.png)

> [!div class="mx-imgBorder"]
>![See how frequent items with certain sensitivity labels were accessed by the app on Microsoft 365.](media/app-governance-visibility-insights-view-apps/sensitive-labels-details.png)

The app details pane provides additional information on these tabs:

| Tab name | Description |
|:-------|:-----|
|**Summary**| See additional data on the app such as the date first consented and the App ID. To see the properties of the app as registered in Azure AD, select **View app in Azure AD**. |
|**Data usage** |See the data usage by the app in the tenant and plot the data usage for Exchange, SharePoint, OneDrive, and Teams resources. You can filter usage insights by priority accounts only. |
|**Users** |See a list of users who are using the app, whether they're a priority account, and the amount of data downloaded and uploaded. If an app is admin consented, the Total consented users will be all users in the tenant. |
|**Permissions** | See a summary and list of the Graph API and legacy permissions granted to the app, consent type, and whether they are in use. For more information, see the [Microsoft Graph permissions reference](/graph/permissions-reference). |
|**Sensitive labels** | See how frequent items with certain sensitivity labels were accessed by the app on Microsoft 365. |
|**Last used** | Indicates the last time the app signed in and provides a link to related recommendations on Azure Active Directory. |
| **Credentials** | Indicates whether the app has unused or expiring credentials and provides a link to credential management on Azure Active Directory. |

For an enabled app, there's also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app. These actions require these administrator roles:

- *Compliance Administrator*
- *Global* or *Company Administrator*
- *Security Administrator*
- *Security Operator*

## Managing OAuth apps

The **OAuth** page displays information about app permissions in apps connected to Microsoft 365, Google Workspace, and Salesforce. Use this page to view permissions granted to each app and to revoke permissions or ban apps.

**To access the OAuth page**, in [Microsoft 365 Defender](https://security.microsoft.com), select **Cloud apps** > **OAuth apps**. For example:

![Screenshot of the Manage OAuth apps page](media/app-permissions.png)


Do any of the following on the **Manage OAuth apps** page to manage your apps:

|Option  |Description |
|---------|---------|
|**Queries**     |     Use the filtering options at the top of the page to define or load a saved query. <br><br>By default, the **OAuth** page has a set of saved, basic queries, with one applied as a default filter. Do any of the following actions to change the filter applied as needed: <br><br>- Select **Save as** to save your updated filter.  <br><br>- Select **Select a query** to select a different saved query, such as **Apps authorized by admins** or **Apps authorized by external users** <br><br>- Select the **Advanced filters** toggle on the right to add more filtering options. Select a filter, an operator, and the value you want to filter by.   |
|**Bulk selection**     |  Select to either select all listed apps, or clear the selection on all selected apps.       |
|**New policy from search**     |  Select to create a new OAuth app policy based on the current query results,  For more information, see [Create app policies in app governance](app-governance-app-policies-create.md).       |
|**Export**     |  Select to export the currently listed apps to a CSV file.|

### View OAuth app details

The **Manage OAuth apps** page provides the following information about each OAuth app that was granted permissions:

|Colum name  |Description  |Available for...   |
|---------|---------|---------|
|**Name**     | The app's name. Select to show or hide more details about the app.       |    Microsoft 365, Google Workspace, Salesforce     |
|**Authorized by**     | The number of users who authorized this app to access their app's account, and granted the app permissions. <br><br>Select to view more information, including a list of user emails and whether an admin has consented the app previously. <br><br>On the **Users who added...** pane, select **Export** to export the listed users to a CSV file. |Microsoft 365, Google Workspace, Salesforce   |
|**Permission level**     |  *High*, *Medium*, or *Low*.   <br><br>The level indicates how much access this app has to app's data. For example, *Low* might indicate that the app only accesses user profile and name. <br><br>Select the level to view more information, including permissions granted to the app, community use, or related activity in the [Governance log](/defender-cloud-apps/governance-actions).     |  Microsoft 365, Google Workspace, Salesforce          |
|**Last authorized**     | The most recent date on which a user granted permissions to this app.        |Microsoft 365, Salesforce         |
|**Actions**  |   Select an option to mark an app as approved or banned.       |    Microsoft 365, Google Workspace, Salesforce        |


Select **Show details** at the top right to view more information about all of the apps displayed, including:

|Colum name  |Description  |Available for...   |
|---------|---------|---------|
|**Publisher**     |  The name of the vendor that provides the app. <br><br>Publisher verifications help admins and end users understand theauthenticity of application developers integrating with the Microsoft identity platform. For more information, see [Publisher verification](/azure/active-directory/develop/publisher-verification-overview).| Microsoft 365    |
|**Permissions**     |  A list of all permissions currently granted to the app       |   Microsoft 365, Google Workspace      |
|**App website**     |  A link to the app's website.       |   Microsoft 365      |
|**Community use**     | Common, Uncommon, Rare. Indicates how popular the app is across all your users.      | Microsoft 365, Google Workspace,Salesforce        |
|**App ID**     |  The app's ID      |   Microsoft 365, Google Workspace, Salesforce      |
|**App activities**     |  A link to the app's activity log, which you can use to understand the app's recent usage.      |  Microsoft 365, Google Workspace, Salesforce       |
|**Redirect URLs**     | A list of any redirect URLs for the app.        |  Microsoft 365       |
| **Terms of service** | A link to the app's terms of service | Microsoft 365  |
| **Support** |A link to the app's support statement | Microsoft 365  |
| **Privacy Statement** | A link to the app's privacy statement | Microsoft 365  |
| **Consent activities** | A link to the app's activity log, with a filter applied for consent activities only. | Microsoft 365  |
| **Last used** | The most recent date on which this app was used by anyone in your organization.|Salesforce |



## Next steps

[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).
