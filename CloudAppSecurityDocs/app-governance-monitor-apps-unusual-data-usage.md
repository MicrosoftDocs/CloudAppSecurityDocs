---
title: Monitor and respond to apps with unusual data usage with app governance | Microsoft Defender for Cloud Apps
ms.date: 05/28/2023
ms.topic: conceptual
description: Monitor and respond to apps with unusual data usage using app governance in Microsoft 365 Defender with Microsoft Defender for Cloud Apps.
---

# Monitor and respond to apps with unusual data usage

App governance provides data usage information that can help you identify unwanted and potentially malicious app activity.

On the **App governance** page, use the following elements to understand data usage:

- **Data usage card**. Located on the **Overview page**. Provides total data usage over time, highlighting sudden spikes in total upload and download activity of all apps that access Microsoft 365 resources. 

    This card also provides usage information separately for various resources, such as files and email, so you can pinpoint the resources that apps might be misusing.

- **App details pane**. Located on the right of an apps tab when you select an app. In the app details pane, get app-specific data usage information by resource type as well as upload and download patterns over time.

- **Policy conditions**. Create policies that automatically flag and deactivate apps whose data usage matches the following conditions:

  - **Data usage**: The total amount of downloads and uploads exceeds your specified threshold
  - **Data usage trend**: The percentage increase in the total amount of downloads and uploads compared to the previous day reaches your specified threshold

## Next step

[Investigate anomaly detection alerts](app-governance-anomaly-detection-alerts.md)
