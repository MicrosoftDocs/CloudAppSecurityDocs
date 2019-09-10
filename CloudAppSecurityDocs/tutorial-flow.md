---
title: Extend governance to endpoint remediation | Microsoft Docs
description: This tutorial describes the process to configure Microsoft Cloud App Security policy alerts to trigger Microsoft Flow workflows to run Microsoft Defender Advanced Threat Protection remediation actions.
author: ShlomoSagir-MS
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: tutorial
ms.date: 9/8/2019
---

# Tutorial: Extend governance to endpoint remediation

Cloud App Security provides predefined governance options for policies, such as suspend a user or make a file private. Using the native integration with Microsoft Flow, you can use a large ecosystem of software as a service (SaaS) connectors to build workflows to automate processes including remediation.

For example, when detecting a possible malware threat, you can use workflows to start Microsoft Defender Advanced Threat Protection (ATP) remediation actions such as running an antivirus scan or isolating an endpoint.

In this tutorial, you'll learn how to configure a policy governance action to use a workflow to run an antivirus scan on an endpoint where a user shows signs of suspicious behavior.

> [!div class="checklist"]
> * 1: [Generate a Cloud App Security API token](#generate-token)
> * 2: [Create a flow to run an antivirus scan](#create-flow)
> * 3: [Configure the flow](#configure-flow)
> * 4: [Configure a policy to run the flow](#configure-policy)

> [!NOTE]
> These workflows are only relevant for policies that contains user activity. For example, you can't use these workflows with Discovery or OAuth policies.

If you don’t have a Microsoft Flow plan, [sign up for a free trial account](https://flow.microsoft.com/pricing).

## Prerequisites

* You must have a valid [Microsoft Flow plan](https://flow.microsoft.com/pricing)
* You must have a valid Microsoft Defender ATP plan
* The Microsoft Flow environment must be Azure AD synced, Defender ATP monitored, and domain joined

## Phase 1: Generate a Cloud App Security API token<a name="generate-token"></a>

> [!NOTE]
> If you have previously created a workflow using a Cloud App Security connector, Microsoft Flow automatically reuses the token and you can skip this step.

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and select **Security extensions**.

1. On the **Security extensions** page, click the plus button to generate a new API token.
1. In the **Generate new token** pop-up window, enter the token name (for example, "Flow-Token"), and then click **Generate**.

    ![Screenshot of the token window, showing the name entry and generate button.](media/tutorial-flow-token-generate.png)
1. Once the token is generated, click the copy icon to the right of the generated token, and then click **Close**. You'll need the token later.

    ![Screenshot of the token window, showing the token and the copy process.](media/tutorial-flow-token-copy.png)

## Phase 2: Create a flow to run an antivirus scan<a name="create-flow"></a>

> [!NOTE]
> If you have previously created a flow using a Defender ATP connector, Flow automatically reuses the connector and you can skip the **Sign in** step.

1. Go to the [Microsoft Flow portal](https://flow.microsoft.com/) and select Templates.
    ![Screenshot of the main Microsoft Flow page, showing the selection of templates.](media/tutorial-flow-templates.png)

1. Search for "Cloud App Security" and select **Run antivirus scan using Windows Defender upon a Cloud App Security alert**.

    ![Screenshot of the templates Microsoft Flow page, showing the search results.](media/tutorial-flow-templates-search.png)

1. Click **Sign in** and enter the admin credentials you want to use with the Microsoft Defender ATP connector.

    ![Screenshot of the templates Microsoft Flow page, showing the sign-in process.](media/tutorial-flow-templates-signin.png)

## Phase 3: Configure the flow<a name="configure-flow"></a>

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

## Phase 4: Configure a policy to run the flow<a name="configure-policy"></a>

1. In Cloud App Security, click **Control**, and then click **Policies**.

1. In the list of policies, on the row where the relevant policy appears, choose the three dots at the end of the row, and then choose **Edit policy**.

1. Under **Alerts**, select **Send alerts to Flow**, and then select **Run antivirus scan using Windows Defender upon a Cloud App Security alert**.

    ![Screenshot of the policy page, showing the alerts settings section.](media/tutorial-flow-templates-alerts.png)

Now every alert raised for this policy will initiate the flow to run the antivirus scan.

You can use the steps in this tutorial to create a wide range of workflow-based actions to extend Cloud App Security remediation capabilities, including other Defender ATP actions. To see a list of predefined Cloud App Security workflows, in Microsoft Flow, [search for "Cloud App Security"](https://go.microsoft.com/fwlink/?linkid=2102574).

## See Also

> [!div class="nextstepaction"]
[Integrate with Microsoft Flow for custom alert automation](flow-integration.md)
