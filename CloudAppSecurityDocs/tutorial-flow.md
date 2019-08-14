---
title: Automate alerts to protect endpoints | Microsoft Docs
description: This tutorial describes the process to configure Microsoft Cloud App Security alerts to use Microsoft Flows to run Microsoft Defender actions.
author: ShlomoSagir-MS
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: tutorial
ms.date: 8/14/2019
---

# Tutorial: Automate alerts to protect endpoints

On its own, Cloud App Security provides predefined governance options such as suspend user or make file private when defining policies. By creating a playbook in Microsoft Flow using Cloud App Security connector, you can create workflows to enable customized endpoint actions for your policies using Microsoft Defender Advanced Threat Protection (ATP). After the playbook is created in Flow, simply associate it with a policy in Cloud App Security to send alerts to Flow. Microsoft Flow offers several connectors and conditions to create a customized workflow for your organization.

The [Cloud App Security connector](https://docs.microsoft.com/connectors/cloudappsecurity/) in Flow supports automated trigger and actions. Flow is triggered automatically when Cloud App Security generates an alert. Actions include changing the alert status in Cloud App Security.

In this tutorial, you learn how to automate alerts to:

> [!div class="checklist"]
> * Run an antivirus scan using Microsoft Defender ATP
> * Isolate a machine using Microsoft Defender ATP

For the purposes of this tutorial, the procedure describes how to automate alerts to run an antivirus scan using Microsoft Defender ATP. For automating alerts to isolate a machine, use the same steps swapping the antivirus flow with the isolate flow.

> [!NOTE]
> These flow are only relevant for policies that contains user activity. For example, you can't use these flows with Discovery or OAuth policies.

If you don’t have a Flow plan, [sign up for a free trial account](https://flow.microsoft.com/pricing).

## Prerequisites

* You must have a valid [Microsoft Flow plan](https://flow.microsoft.com/pricing)
* The Flow environment must be Azure AD synced, Defender ATP monitored, and domain joined

## Run an antivirus scan using Microsoft Defender ATP

This following steps guide you through creating a flow that runs an antivirus scan and adding it to a policy that detects suspicious behavior. When an alert for suspicious behavior is raised for a user, it triggers the flow that runs an antivirus scan on the machine used by the user suspected of being compromised.

### Step 1: Create a flow to run an antivirus scan

> [!NOTE]
> If you have previously created a flow using a Defender ATP connector, Flow automatically reuses the connector and you can skip the **Sign in** step.

1. Go to the [Microsoft Flow portal](https://flow.microsoft.com/) and select Templates.
    ![Screenshot of the main Flow page, showing the selection of templates.](media/tutorial-flow-templates.png)
1. Search for "Cloud App Security" and select **Run antivirus scan using Windows Defender upon a Cloud App Security alert**.
    ![Screenshot of the templates Flow page, showing the search results.](media/tutorial-flow-templates-search.png)
1. Click **Sign in** and enter the admin credentials you want to use with the Microsoft Defender ATP connector.
    ![Screenshot of the templates Flow page, showing the sign in process.](media/tutorial-flow-templates-signin.png)

> [!TIP]
> Keep this page open, you'll need it later.

### Step 2: Create a Cloud App Security connector

> [!NOTE]
> If you have previously created a flow using a Cloud App Security connector, Flow automatically reuses the token and you can skip this step.

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and select **Security extensions**.
1. In the **Security extensions** page, click the plus button to generate a new API token.
1. In the **Generate new token** pop-up window, enter the token name (for example, "Flow-Token"), and then click **Generate**. 
    ![Screenshot of the token window, showing the name entry and generate button.](media/tutorial-flow-token-generate.png)
1. Once the token is generated, click the copy icon to the right of the generated token, and then click **Close**. You'll need the token later.
    ![Screenshot of the token window, showing the token and the copy process.](media/tutorial-flow-token-copy.png)

### Step 3: Configure the flow

> [!NOTE]
> If you have previously created a flow using an Azure AD connector, Flow automatically reuses the token and you can skip this step.

1. Back in the Microsoft Flow portal, click **Create**.
    ![Screenshot of the templates Flow page, showing the create in process.](media/tutorial-flow-templates-create.png)
1. In the **Cloud App Security** pop-up window, enter the connection name (for example, "Cloud App Security Token"), paste the API token you copied, and then click **Create**.
    ![Screenshot of the Cloud App Security window, showing the name and key entry and create button.](media/tutorial-flow-token-generate.png)
1. Click **Continue** to connect to Azure Active Directory.
    ![Screenshot of the templates Flow window, showing the completed actions and continue button.](media/tutorial-flow-templates-continue.png)
1. In the **HTTP with Azure AD** pop-up window, for both the **Base Resource URL** and **Azure AD Resource URI** fields, enter `https://graph.microsoft.com`, and then click **Sign in** and enter the admin credentials you want to use with the HTTP with Azure AD connector.
    ![Screenshot of the HTTP with Azure AD window, showing the Resource fields and sign in button.](media/tutorial-flow-templates-continue.png)
1. Once all the connecters are successfully connected, on the flow's page under **Apply to each machine**, optionally modify the comment and scan type, and then click **Save**.
    ![Screenshot of the flow page, showing the scan setting section.](media/tutorial-flow-templates-continue.png)

### Step 4: Apply the flow to a policy

1. In Cloud App Security, edit the policy where you want to add the antivirus flow, and under **Alerts**, select **Send alerts to Flow**, and then select **Run antivirus scan using Windows Defender upon a Cloud App Security alert**.
    ![Screenshot of the policy page, showing the alerts settings section.](media/tutorial-flow-templates-continue.png)

## Next steps

> [!div class="nextstepaction"]
[Integrate with Flow for custom alert automation](flow-integration.md)
