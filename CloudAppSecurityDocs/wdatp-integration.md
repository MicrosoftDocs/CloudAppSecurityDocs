---
# required metadata

title: Integrate Windows Defender Advanced Threat Protection with Cloud App Security | Microsoft Docs
description: This article provides information about how to integrate Windows Defender ATP with Cloud App Security seamless integration and enhanced visibility into Shadow IT and risk management.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/25/2018
ms.topic: conceptual
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: b35ca44c-da8e-49ec-89d1-c076d123c14f



# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


*Applies to: Microsoft Cloud App Security*


# Windows Defender Advanced Threat Protection integration with Microsoft Cloud App Security

Microsoft Cloud App Security integrates with Windows Defender Advanced Threat Protection (ATP) natively, to simplify roll out of Cloud Discovery, and extends Cloud Discovery capabilities beyond your corporate network. Microsoft Cloud App Security leverages the traffic information collected by Windows Defender ATP about the cloud apps and services being accessed from IT-managed Windows 10 machines. This enables you to run Cloud Discovery on managed machines, even when they aren't within your corporate network. It also enables machine-based investigation: after you identify a risky user, you can then check all the machines the user accessed to detect potential risks; if you identify a risky machine, you can check all the users who used it to detect potential risks. 


## Windows Defender Advanced Threat Protection
[Windows Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) is a security platform for intelligent protection, detection, investigation, and response. Windows Defender ATP protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.

Want to experience Windows Defender ATP? [Sign up for a free trial](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).

## Better together: Cloud App Security and Windows Defender ATP

Microsoft Cloud App Security leverages Windows Defender ATP to tap into data about cloud app and service traffic from managed Windows devices. This seamless integration does not require any additional deployment.

###	Shadow IT discovery on and off your corporate network 
Because the Windows Defender ATP agent is installed directly on machines, it monitors traffic regardless of your user's location, or whether or not they are connected via a VPN.

###	Native integration
The integration between Cloud App Security and Windows Defender ATP works out of the box. It is not necessary to route or mirror traffic from your endpoints or to perform complex integration steps.

###	Machine-centric investigation
Logs from your endpoints routed to Cloud App Security provide user information for traffic activities. Windows Defender ATP network activity provides device context, which can be paired with the username to provide a full picture of which user performed which activity from which machine, across your network.

## Prerequisites

- Microsoft Cloud App Security license (EM+S E5)
- Windows Defender ATP license
- Windows 10 machines running Windows Defender ATP RS5


## How it works

On its own, Cloud App Security collects logs from your endpoints using either [logs you upload](create-snapshot-cloud-discovery-reports.md) or by [configuring automatic log upload](discovery-docker.md). This native integration enables you to take advantage of the logs Windows Defender ATP's agent creates when it runs on Windows and monitors network transactions and utilize them for Shadow IT discovery across the Windows machines on your network. 

To achieve the most comprehensive coverage and discover what's going on in your network, it's best to use both the Cloud App Security [log collector](discovery-docker.md)  to monitor all traffic on your endpoints, as well as the integration with Windows Defender ATP to monitor your Windows 10 machines. Because the Windows Defender ATP agent is installed directly on machines, it monitors traffic regardless of your user's location and whether or not they are connected via a VPN.


## How to integrate Windows Defender ATP with Cloud App Security

To enable integration with Cloud App Security from Windows Defender ATP:

1. In the Windows Defender ATP portal, from the navigation pane, select **Preferences setup**.
2. In the **Settings** menu, under **General**, select **Advanced features**.
3. Toggle the **Microsoft Cloud App Security** to **On**.
4. Click **Save preferences**.

>[!NOTE]
> It takes up to two hours after you enable the integration for the data to show up in Cloud App Security.
>

   ![WD ATP settings](./media/wdatp-settings.png)

## Investigate machines in Cloud App Security

After you integrate Windows Defender ATP with Cloud App Security, you will be able to investigate discovered machine data in the Cloud Discovery dashboard.

1. In the Cloud App Security portal, click **Cloud Discovery** and then **Cloud Discovery dashboard**.
2. In the top navigation bar, under **Continuous reports**, select **Win10 endpoint users**.
  ![WD ATP report](./media/win10-dashboard-report.png)
4. You can see that across the top, the number of discovered machines was added after the integration.
5. Click the **Machines** tab.
6. You can drill down into each machine listed, and use the tabs to view the investigation data, and find correlations between the machines and the users, IP addresses, and apps that were involved in incidents:
   - **Overview**
      - Transactions: provides you with information about the number of transactions that took place on the machine over the selected period of time.
      - Total traffic: provides you with information about the total amount of traffic (in MB) over the selected period of time.
     - Uploads: provides you with information about the total amount of traffic (in MB) uploaded by the machine over the selected period of time.
     - Downloads: provides you with information about the total amount of traffic (in MB) downloaded by the machine over the selected period of time.
   - **Discovered apps**<br>
  Lists all the discovered apps that were accessed by the machine.
   - **User history**<br>
    Lists all the users who signed in to the machine.
   - **IP address history**<br>
    Lists all the IP addresses that were assigned to the machine.
 ![Machines overview](./media/machines-overview.png)
 

As with any other Cloud Discovery source, you can export the data from the Win10 endpoint users report for further investigation. 


## Related Videos  
[Cloud App Security + Azure Information Protection Integrations](https://channel9.msdn.com/Shows/Microsoft-Security/MCAS--AIP-Integrations)  

## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
