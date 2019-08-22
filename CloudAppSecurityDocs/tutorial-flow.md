---
title: Extending Cloud App Security governance to coordinate remediation with endpoints | Microsoft Docs
description: This tutorial describes the process to configure Microsoft Cloud App Security alerts to trigger Microsoft Flow workflows to run Microsoft Defender Advanced Threat Protection remediation actions.
author: ShlomoSagir-MS
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: tutorial
ms.date: 8/22/2019
---

# Tutorial: Extending governance to coordinate remediation with endpoints

Cloud App Security provides predefined governance options for policies, such as suspend a user or make a file private. With Microsoft Flow, you can use a large ecosystem of software as a service (SaaS) connectors to build workflows to automate processes. Using predefined or custom workflows as policy governance actions, you can extend Cloud App Security remediation capabilities.

For example, when detecting a possible malware threat, you can use workflows to start Microsoft Defender Advanced Threat Protection (ATP) remediation actions such as running an antivirus scan or isolating an endpoint.

In this tutorial, you'll learn how to configure a policy governance action to use a workflow to run an antivirus scan on an endpoint where the user shows signs of suspicious behavior.

> [!NOTE]
> These workflows are only relevant for policies that contains user activity. For example, you can't use these workflows with Discovery or OAuth policies.

If you don’t have a Microsoft Flow plan, [sign up for a free trial account](https://flow.microsoft.com/pricing).

## Prerequisites

* You must have a valid [Microsoft Flow plan](https://flow.microsoft.com/pricing)
* The Microsoft Flow environment must be Azure AD synced, Defender ATP monitored, and domain joined

## To configure a policy to run an antivirus scan using Microsoft Defender ATP

### Step 1: Create a Cloud App Security connector

> [!NOTE]
> If you have previously created a workflow using a Cloud App Security connector, Microsoft Flow automatically reuses the token and you can skip this step.

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and select **Security extensions**.

1. In the **Security extensions** page, click the plus button to generate a new API token.
1. In the **Generate new token** pop-up window, enter the token name (for example, "Flow-Token"), and then click **Generate**.

    ![Screenshot of the token window, showing the name entry and generate button.](media/tutorial-flow-token-generate.png)
1. Once the token is generated, click the copy icon to the right of the generated token, and then click **Close**. You'll need the token later.

    ![Screenshot of the token window, showing the token and the copy process.](media/tutorial-flow-token-copy.png)

### Step 2: Create a flow to run an antivirus scan

> [!NOTE]
> If you have previously created a flow using a Defender ATP connector, Flow automatically reuses the connector and you can skip the **Sign in** step.

1. Go to the [Microsoft Flow portal](https://flow.microsoft.com/) and select Templates.
    ![Screenshot of the main Microsoft Flow page, showing the selection of templates.](media/tutorial-flow-templates.png)

1. Search for "Cloud App Security" and select **Run antivirus scan using Windows Defender upon a Cloud App Security alert**.

    ![Screenshot of the templates Microsoft Flow page, showing the search results.](media/tutorial-flow-templates-search.png)

1. Click **Sign in** and enter the admin credentials you want to use with the Microsoft Defender ATP connector.

    ![Screenshot of the templates Microsoft Flow page, showing the sign-in process.](media/tutorial-flow-templates-signin.png)

### Step 3: Configure the flow

> [!NOTE]
> If you have previously created a flow using an Azure AD connector, Microsoft Flow automatically reuses the token and you can skip this step.

1. Click **Create**.

    ![Screenshot of the templates Microsoft Flow page, showing the Cloud App Security create button.](media/tutorial-flow-templates-create.png)

1. In the **Cloud App Security** pop-up window, enter the connection name (for example, "Cloud App Security Token"), paste the API token you copied, and then click **Create**.

    ![Screenshot of the Cloud App Security window, showing the name and key entry and create button.](media/tutorial-flow-templates-create-window.png)

1. In the list of apps, on the row in which **HTTP with Azure AD** appears, choose the three dots at the end of the row, and then click **Add new connection**.

1. In the **HTTP with Azure AD** pop-up window, for both the **Base Resource URL** and **Azure AD Resource URI** fields, enter `https://graph.microsoft.com`, and then click **Sign in** and enter the admin credentials you want to use with the HTTP with Azure AD connector.

    ![Screenshot of the HTTP with Azure AD window, showing the Resource fields and sign-in button.](media/tutorial-flow-templates-azure.png)

1. Click **Continue**.

    ![Screenshot of the templates Microsoft Flow window, showing the completed actions and continue button.](media/tutorial-flow-templates-continue.png)

1. Once all the connecters are successfully connected, on the flow's page under **Apply to each machine**, optionally modify the comment and scan type, and then click **Save**.

    ![Screenshot of the flow page, showing the scan setting section.](media/tutorial-flow-templates-scan.png)

### Step 4: Apply the flow to a policy

1. In Cloud App Security, edit the policy where you want to add the antivirus flow, and under **Alerts**, select **Send alerts to Flow**, and then select **Run antivirus scan using Windows Defender upon a Cloud App Security alert**.

    ![Screenshot of the policy page, showing the alerts settings section.](media/tutorial-flow-templates-alerts.png)

The steps used in this tutorial can be used to create a wide range of workflow based actions to extend Cloud App Security remediation capabilities. To see alist of predefined workflows, in Microsoft Flow, search for "Cloud App Security".

## Next steps

> [!div class="nextstepaction"]
[Integrate with Microsoft Flow for custom alert automation](flow-integration.md)
