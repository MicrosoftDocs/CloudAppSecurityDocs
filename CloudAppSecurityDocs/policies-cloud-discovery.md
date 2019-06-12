---
# required metadata

title: Cloud Discovery policies - Cloud App Security | Microsoft Docs
description: This topic outlines the steps to configure many Cloud Discovery policies in Cloud App Security.
author: rkarlin
ms.author: rkarlin
ms.date: 06/13/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.service: cloud-app-security
ms.assetid: 570da960-771d-484f-932d-b086f2ec2978


# optional metadata
ms.suite: ems
ms.custom: seodec18

---
# Cloud Discovery policies

*Applies to: Microsoft Cloud App Security*

This article provides an overview of how to get started using Cloud App Security to gain visibility across your organization into Shadow IT using Cloud Discovery.

Cloud App Security enables you to discover and analyze cloud apps that are in use in your organization’s environment. The Cloud Discovery dashboard shows all the cloud apps running in the environment and categorizes them by function and enterprise readiness. For each app, discover the associated users, IP addresses, machines, transactions, and conducts risk assessment without needing to install an agent on your endpoint devices.

## Detect new high-volume or wide app use <a name= "detect-volume"></a>

Detect new apps that are highly used, in terms of number of users or amount of traffic in your organization.

### Prerequisites

Configure automatic log upload for continuous Cloud Discovery reports, as described in [Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md).

### Steps

1.  On the **Policies** page, create a new **App discovery policy**

2.  In the **Policy template** field, select **New high volume app** or **New popular app** and apply the template.

3.  Customize policy filters to meet your organization’s requirements.

4.  Configure the actions to be take when an alert is triggered.

> [!NOTE]
>  An alert is generated once for each new app that was not discovered in the last 90 days.

## Detect new risky or non-compliant app use

Detect potential exposure of your organization in cloud apps that do not meet your security standards.

### Prerequisites

Configure automatic log upload for continuous Cloud Discovery reports, as described in [Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md).

### Steps

1.  On the **Policies** page, create a new **App discovery policy.**

2.  In the **Policy template** field, select the **New risky app** template and apply the template.

3.  Under **App matching all of the following** set the [Risk Score](risk-score.md) slider and and the Compliance risk factor to customize your the level of risk you want to trigger an alert, and set the other policy filters to meet your organization’s security requirements.

    1.  Optional: To get more meaningful detections, customize the amount of traffic that will trigger an alert.

        1.  Check the **Trigger a policy match if all the following occur on the same day** checkbox.

        2.  Select **Daily traffic** greater than 2000 GB (or other).

4.  Configure governance actions to be taken when an alert is triggered. Under **Governance**, select **Tag app as unsanctioned.**<br>Access to the app will be automatically blocked when the policy is matched.

5.  Optional: Leverage [Cloud App Security native integrations](set-up-cloud-discovery.md) with Secure Web Gateways to block app access.

## Detect use of unsanctioned business apps

You can detect when your employees continue to use unsanctioned apps as a replacement for approved business-ready apps.

### Prerequisites

-   Configure automatic log upload for continuous Cloud Discovery reports, as described in [Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md).

### Steps

1.  In the Cloud app catalog, search for your business-ready apps and mark them with a [custom app tag](discovered-app-queries.md#creating-and-managing-custom-app-tags).

2.  Follow the steps in [Detect new high volume or wide app usage](#detect-volume).

3.  Add an **App tag** filter and choose the app tags you created for your business-ready apps.

4.  Configure governance actions to be taken when an alert is triggered. Under Governance, select **Tag app as unsanctioned**.<br>Access to the app will be automatically blocked when the policy is matched.

5.  Optional: Leverage [Cloud App Security native integrations](set-up-cloud-discovery.md) with Secure Web Gateways to block app access.

## Detect unusual usage patterns on your network

Detect anomalous traffic use patterns (uploads/downloads) in your cloud apps, that originate from users or IP addresses inside your organization’s network.

### Prerequisites

Configure automatic log upload for continuous Cloud Discovery reports, as described in [Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md).

### Steps

1.  On the **Policies** page, create a new **Cloud Discovery anomaly detection policy**.

2.  In the **Policy template** field, select **Anomalous behavior in discovered users** or **Anomalous behavior in discovered IP addresses**.

3.  Customize the filters to meet your organization's requirements.

4. If you want to be alerted only when there are anomalies involving risky apps, use the **Risk score** filters and set the range in which apps are considered risky.

4.  Use the slider to **Select anomaly detection sensitivity**.

> [!NOTE]
>  After continuous log upload is established, the anomaly detection engine takes a few days until a baseline (learning period), is established for the expected behavior in your organization. After a baseline is established, you start receiving alerts based on discrepancies from the expected traffic behavior across cloud apps made by users or from IP addresses.

## Detect data exfiltration to unsanctioned storage apps

Detect potential data exfiltration by a user to an unsanctioned cloud storage app.

### Prerequisites

Configure automatic log upload for continuous Cloud Discovery reports, as described in [Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md).

### Steps

1.  On the **Policies** page, edit the built-in policy **Data exfiltration to unsanctioned apps**.

2.  Select the filter **App category** equals **Cloud storage**.

3.  Select the checkbox to **Create an alert for each matching event with the policy's severity**.

4.  Configure the actions to be take when an alert is triggered.

## Detect risky OAuth apps

Get visibility and control over [OAuth apps](investigate-risky-oauth.md) that are installed inside apps like Salesforce, Office 365, and G Suite. OAuth apps that request high permissions and have rare community use might be considered risky.

### Prerequisites

Configure automatic log upload for continuous Cloud Discovery reports, as described in [Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md).

### Steps

1.  On the **Policies** page, create a new **OAuth app policy**.

2.  Select the filter **App** and set the app the policy should cover, G Suite, Office 365, or Salesforce.

3.  Select **Permission level** filter equals **High** (available for G Suite and O365).

4.  Add the filter **Community use** equals **Rare**.

4.  Configure the actions to be take when an alert is triggered. For example, for Office 365, check **Revoke app** for OAuth apps detected by the policy.

> [!NOTE]
>  Supported for Office 365, Salesforce and G Suite app stores.

## Next steps 

[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
