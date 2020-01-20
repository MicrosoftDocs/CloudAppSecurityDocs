---
# required metadata
title: Encrypt Cloud App Security data at rest with your own key
description: This article provides instructions for using your own key to encrypt data at rest stored in Cloud App Security.
author: shsagir
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: conceptual
ms.date: 01/15/2020

# optional metadata
#ROBOTS: NOINDEX # Used to prevent showing on search pages
#services: na
#ms.subservice: na
ms.collection: M365-security-compliance
---
# Encrypt Cloud App Security data at rest with your own key (BYOK)

*Applies to: Microsoft Cloud App Security*

This article describes how to configure Cloud App Security to use your own key to encrypt the data it collects, whilst it's at rest. If you are looking for documentation about applying encryption to data stored in cloud apps, see [Azure Information Protection integration](azip-integration.md).

Cloud App Security takes your security and privacy seriously. Therefore, once Cloud App Security starts collecting data, it uses its own managed keys to protect your data in accordance with our [data security and privacy](cas-compliance-trust.md) policy. Additionally, Cloud App Security allows you to further protect your data at rest by encrypting it with your own Azure Key Vault key.

> [!IMPORTANT]
> If there is a problem accessing your Azure Key Vault key, Cloud App Security will fail to encrypt your data and your tenant will be lock down within an hour. When your tenant is locked down, all access to it will be blocked until the cause has been resolved. Once your key is accessible again, full access to your tenant will be restored.

## Prerequisites

You must register the **Microsoft Cloud App Security - BYOK** app in your tenant's Azure Active Directory (Azure AD).

**//TBD: Need updated First party app name**

### To register the app

1. Install [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

1. Open a PowerShell terminal and run the following commands:

    ``` Powershell
    Connect-AzureAD
    New-AzureADServicePrincipal -AppId 61fc00cf-6d25-4d73-ba42-77a7ecec2b31
    Set-AzureADServicePrincipal -ObjectId <object_id> -AccountEnabled true
    ```

    Where *<object_id>* is the object ID returned by the previous command (`New-AzureADServicePrincipal`).

**//TBD: Need updated AppId**

> [!NOTE]
>
> - Cloud App Security encrypts data at rest for all new tenants.
> - Any data that resides in Cloud App Security for more than 48 hours will be encrypted.

## Deploy your Azure Key Vault key

1. Create a [new Key Vault](https://docs.microsoft.com/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key-vault).

1. Create an access policy, fill out the following information, and then click **Add**.
    1. Click **Key permissions** and choose the following permissions from the dropdown menu:

        | Section | Required permissions |
        | --- | --- |
        | Key Management Operations | - List |
        | Cryptographic Operations | - Wrap key<br />- Unwrap key |

        ![Screenshot showing the selection of key permissions](media/byok-kv-access-policy-key-perms.PNG)

    2. Under **Select principal**, choose **Microsoft Cloud App Security - BYOK**.

        ![Screenshot showing add access policy page](media/byok-kv-add-access-policy.PNG)

1. Create a [new RSA key](https://docs.microsoft.com/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key), do the following, and then click **Add**.

    > [!NOTE]
    > Only RSA keys are supported.

    1. Under **Permitted operations**, select the following options:

        - Wrap key
        - Unwrap key

    2. Copy the **Key Identifier** URI, you'll need this later.

    ![Screenshot showing key settings page](media/byok-kv-key-perms.PNG)

1. Set up the [soft-delete behavior](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete#soft-delete-behavior) for your Key Vault.

1. Set up the [no purge protection behavior](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete#purge-protection) for your Key Vault.

1. Optionally, if using a firewall for a selected network, configure the following firewall settings to give Cloud App Security access to the specified key, and then click **Save**:
    1. Make sure no virtual networks are selected.
    1. Add the following IP addresses:
        - 13.66.200.132
        - 23.100.71.251
        - 40.78.82.214
        - 51.105.4.145
        - 52.166.166.111
    1. Select **Allow trusted Microsoft services to bypass this firewall**.

    ![Screenshot showing firewall configuration](media/byok-kv-firewall.PNG)

## Enable data encryption in Cloud App Security

When you enable data encryption, Cloud App Security immediately uses your Azure Key Vault key to encrypt data at rest. Since your key is essential to the encryption process, it is important to ensure that your designated Key Vault and key are accessible at all times.

### To enable data encryption

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](media/settings-icon.png) and select **Settings**.

1. Select the **Data encryption** tab.

1. Click **Enable data encryption**.

1. In the **Azure Key Vault key URI** box, paste the key identifier URI value you copied earlier.

    > [!NOTE]
    > Cloud App Security always uses the latest key version, regardless of the key version specified by the URI.

1. Once the URI validation has completed, click **Enable**.

> [!NOTE]
> When you disable data encryption, Cloud App Security removes the encryption with your own key from the data at rest. However, your data remains encrypted by Cloud App Security's managed keys.
>
> **To disable data encryption:** Go to the **Data encryption** tab and click **Disable data encryption**.

## Key roll handling

Whenever you create new version of the key configured for data encryption, Cloud App Security automatically rolls to the latest version of the key.

## How to handle data encryption failures

If there is a problem accessing your Azure Key Vault key, Cloud App Security will fail to encrypt your data and your tenant will be lock down within an hour. When your tenant is locked down, all access to it will be blocked until the cause has been resolved. Once your key is accessible again, full access to your tenant will be restored. For information about handling data encryption failures, see [Troubleshooting data encryption with your own key](troubleshooting-data-encryption.md).
