---
title: Classic portal -  Connect Google Workspace 
description: Classic portal -  This article provides information about how to connect your Google Workspace to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Connect Google Workspace to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Google Workspace account using the connector APIs. This connection gives you visibility into and control over Google Workspace use. For information about how Defender for Cloud Apps protects Google Workspace, see [Protect Google Workspace](protect-google-workspace.md).

>[!NOTE]
>File download activities for Google Workspace aren't displayed in Defender for Cloud Apps.

## Configure Google Workspace

1. As a Google Workspace Super Admin, sign in to <https://console.cloud.google.com>.

1. Select **Create project** to start a new project.

    ![Google create project.](media/connect-google-workspace/classic-google-workspace-create-new-project.png)

1. In the **New project** page, name your project as follows: **Defender for Cloud Apps** and select **Create**.

    ![Google new project pop-up.](media/connect-google-workspace/classic-google-workspace-create-new-project-popup.png)

1. After the project is created, in the tool bar, select **Google Cloud Platform**. Make sure that the correct project is selected in the drop-down at the top.  
Copy the **Project number**, you'll need it later.

    ![Select Google Cloud Platform in tool bar.](media/connect-google-workspace/classic-google-workspace-verify-project.png)

1. In the navigation menu, under **MORE PRODUCTS**, go to **APIs & Services** > **Library**.

    ![Google Workspace navigation menu.](media/connect-google-workspace/classic-google-workspace-navigation-menu.png)

    Enable the following APIs (use the search bar if the API isn't listed):

    - Admin SDK API
    - Google Drive API

    For each API, select **Enable** to activate it.

    ![enable Google API.](media/connect-google-workspace/classic-google-workspace-api.png)

    > [!NOTE]
    > Ignore the **Credentials** warning for now.

1. In the navigation menu, go to **APIs & Services** > **Dashboard**. Select **Admin SDK API** and **Google Drive API** and confirm they're enabled.

    ![Google Workspace confirm APIs are enabled.](media/connect-google-workspace/classic-google-workspace-api-enable-verification.png)

1. In the navigation menu, go to **APIs & Services** > **Credentials** and do the following steps:

    1. Select **CREATE CREDENTIALS** and then select **Service Account**.
    1. Under **Service account details**:
        1. Provide the following name: **Defender for Cloud Apps**
        1. Provide the following description: **API connector from Defender to Cloud App to a Google Workspace account**
            >[!NOTE]
            >The name and description can be different. These are examples for your convenience.
        1. Select **CREATE AND CONTINUE**.
           ![Google Workspace service account details.](media/connect-google-workspace/classic-google-workspace-service-account-details.png)
    1. Under **Grant this service account access to project**, for **Role** select **Project** > **Editor**, and then select **Done**.
        ![Google Workspace grant service account access.](media/connect-google-workspace/classic-google-workspace-service-account-access.png)

    1. In the navigation menu, return to **APIs & Services** > **Credentials**.
    1. Under **Service Accounts**, locate and edit the service account you created earlier by selecting the pencil icon.

        ![Google edit service account.](media/connect-google-workspace/classic-google-workspace-edit-service-account.png)

    1. Copy the email address. You'll need it later.
    1. Under **Keys**, from the **ADD KEY** menu, select **Create new key**, select **P12**, and then select **CREATE**. Save the file that's downloaded, you'll need it later.

1. In the navigation menu, go to **IAM & Admin** > **Service accounts**. Copy the **Client ID** assigned to the service account you have just created - you'll need it later.

    ![Google Workspace credentials service account.](media/connect-google-workspace/classic-google-workspace-copy-service-account-client-id.png)

1. Go to [admin.google.com](https://admin.google.com/) and in the navigation menu, go to **Security** > **Access and data control** > **API Controls**. Then do the following:

    1. Under **Domain wide delegation**, select **MANAGE DOMAIN WIDE DELEGATION**.
        ![Google Workspace domain wide delegation.](media/connect-google-workspace/classic-google-workspace-domain-wide-delegation.png)
    1. Select **Add new**.
        ![Google Workspace add new client ID.](media/connect-google-workspace/classic-google-workspace-add-new-client-id.png)
    1. In the **Client ID** box, enter the **Client ID** that you copied earlier.
    1. In the **OAuth Scopes** box, enter the following list of required scopes (copy the text and paste it in the box):

        ```txt
        https://www.googleapis.com/auth/admin.reports.audit.readonly,https://www.googleapis.com/auth/admin.reports.usage.readonly,https://www.googleapis.com/auth/drive,https://www.googleapis.com/auth/drive.appdata,https://www.googleapis.com/auth/drive.apps.readonly,https://www.googleapis.com/auth/drive.file,https://www.googleapis.com/auth/drive.metadata.readonly,https://www.googleapis.com/auth/drive.readonly,https://www.googleapis.com/auth/drive.scripts,https://www.googleapis.com/auth/admin.directory.user.readonly,https://www.googleapis.com/auth/admin.directory.user.security,https://www.googleapis.com/auth/admin.directory.user.alias,https://www.googleapis.com/auth/admin.directory.orgunit,https://www.googleapis.com/auth/admin.directory.notifications,https://www.googleapis.com/auth/admin.directory.group.member,https://www.googleapis.com/auth/admin.directory.group,https://www.googleapis.com/auth/admin.directory.device.mobile.action,https://www.googleapis.com/auth/admin.directory.device.mobile,https://www.googleapis.com/auth/admin.directory.user
        ```

    1. Select **AUTHORIZE**.

        ![Google Workspace authorize new client ID.](media/connect-google-workspace/classic-google-workspace-authorize-new-client-id.png)

## Configure Defender for Cloud Apps

1. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), select **Investigate** and then **Connected apps**.

1. To provide the Google Workspace connection details, under **App connectors**, do one of the following:

    **For a Google Workspace organization that already has a connected GCP instance**

    - In the list of connectors, at the end of row in which the GCP instance appears, select the three dots and then select **Add Google Workspace**.

    **For a Google Workspace organization that does not already have a connected GCP instance**

    - In the **Connected apps** page, select the plus sign (**+**) and select **Google Workspace**.

1. In the pop-up, fill in the following information:

    ![Google Workspace Configuration in Defender for Cloud Apps.](media/connect-google-workspace/classic-cas-config-google-workspace.png "Google Workspace Configuration in Defender for Cloud Apps")

    1. Enter the **Service account ID**, the **Email** that you copied earlier.

    1. Enter the **Project number (App ID)** that you copied earlier.

    1. Upload the P12 **Certificate** file that you saved earlier.

    1. Enter one **admin account email** of your Google Workspace admin.

    1. If you have a Google Workspace Business or Enterprise account, check this check box. For information about which features are available in Defender for Cloud Apps for Google Workspace Business or Enterprise, see [Enable instant visibility, protection, and governance actions for your apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

    1. Select **Save settings**.

    1. Make sure the connection succeeded by selecting **Test now**.  
    Testing may take a couple of minutes.  
    After receiving a success notice, select **Done** and close the Google Workspace page.

After connecting Google Workspace, you'll receive events for seven days prior to connection.

After connecting Google Workspace, Defender for Cloud Apps performs a full scan. Depending on how many files and users you have, completing the full scan can take a while. To enable near real-time scanning, files on which activity is detected are moved to the beginning of the scan queue. For example, a file that is edited, updated, or shared is scanned right away. This doesn't apply to files that aren't inherently modified. For example, files that are viewed, previewed, printed, or exported are scanned during the regular scan.

If you have any problems connecting the app, see [Troubleshooting App Connectors](troubleshooting-api-connectors-using-error-messages.md).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/classic-support.md)]
