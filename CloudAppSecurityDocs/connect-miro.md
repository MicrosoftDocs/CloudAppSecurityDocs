---
title: Connect Miro
description: This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Miro app using the App Connector APIs. 
ms.date: 07/17/2023
ms.topic: how-to
---

# Connect Miro to Microsoft Defender for Cloud Apps (Preview)

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Miro account using the App Connector APIs. This connection gives you visibility into and control over Miro usage. 

## Prerequisites

- A Miro account with an enterprise plan is a pre-requisite for this connection. You must sign-in as a company admin to Miro. 

## How to connect Miro to Defender for Cloud Apps

1. Sign into [Miro](https://miro.com/app/dashboard/) portal with a company admin account.
2. Create a developer team from the portal. To create a developer team, navigate to **Company Settings > User & Team management > Teams > Create new team**.
![Screenshot of creating a new Miro developer team.](media/connect-miro/miro-create-new-team.png)
3. Give a descriptive name to the team and set the permissions to ‘Default’. Select ‘Create as a Developer Team’ and create the team.
4. Create a new application in the newly created developer team. To create a new application, navigate to **Profile settings > Your apps** and click on **‘Create new app’**
![Screenshot of creating a new Miro app.](media/connect-miro/miro-create-new-app.png)
5. Give a name to the app, select the newly created developer team, and click on **Create app**.
6. Copy the Client ID and Client secret for future reference. 
7. Provide 'https://portal.cloudappsecurity.com/api/oauth/saga' as the 'Redirect URI for OAuth2.0'.
8. Provide ‘auditlogs:read’ and ‘organization:read; permissions and click on **Install app and get OAuth token**.
![Screenshot of enabling oAuth scopes on Miro app.](media/connect-miro/miro-provide-permissions.png)
9. In the [Defender for Cloud Apps](https://portal.cloudAppSecurity.com) portal, navigate to Investigate >Connected apps.
10. In the App connectors page, click on Connect an app and choose Miro. 
11. Enter a name for Miro connection in the connection wizard and click on Connect Miro.
12. Enter the Client ID, Client secret and click on Connect in Miro.
13. Select the Miro team that you want to connect with Defender for Cloud Apps and click on Add again. Note that this Miro team is different from the developer team in which you created the app.
![Screenshot of installing Miro app in the team.](media/connect-miro/miro-install-app.png)
14. Click on Test now to make sure the connection succeeded. Audit events will start flowing into Defender for Cloud apps from the time the connection is successfully established.

If you have any problems connecting the app, see [Troubleshooting App Connectors](/defender-cloud-apps/troubleshooting-api-connectors-using-error-messages).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)


[!INCLUDE [Open support ticket](includes/support.md)]


