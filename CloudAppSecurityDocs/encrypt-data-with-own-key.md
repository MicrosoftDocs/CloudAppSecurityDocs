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

> [!NOTE]
>
> - Cloud App Security encrypts data at rest for all new tenants as of **//TBD: Yahav to provide {Date place holder}**.
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

    2. Principal: **// TBD: Yahav to provide**

        ![Screenshot showing add access policy page](media/byok-kv-add-access-policy.PNG)

1. Create a [new key](https://docs.microsoft.com/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key), do the following, and then click **Add**.

    > [!NOTE]
    > You can set up data encryption with an unversioned key or a specific key version. For more information, see [About keys versioning](https://docs.microsoft.com/azure/key-vault/about-keys-secrets-and-certificates#objects-identifiers-and-versioning).

    1. Under **Permitted operations**, select the following options:

        - Wrap key
        - Unwrap key

    2. Copy the **Key Identifier** URI, you'll need this later.

    ![Screenshot showing key settings page](media/byok-kv-key-perms.PNG)

1. Set up the [**soft-delete** behavior](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete#soft-delete-behavior) for your Key Vault.

1. Set up the [no **purge protection** behavior](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete#purge-protection) for your Key Vault.

1. Optionally, if using a firewall for a selected network, configure the following firewall settings to give Cloud App Security access to the specified key, and then click **Save**:
    1. Make sure no virtual networks are selected.
    1. Add the following IP addresses: **// TBD: Yahav to provide. Require list of Cloud App Security IP addresses**

    ![Screenshot showing firewall configuration](media/byok-kv-firewall.PNG)

## Enable data encryption in Cloud App Security

When you enable data encryption, Cloud App Security immediately uses your Azure Key Vault key to encrypt data at rest. Since your key is essential to the encryption process, it is important to ensure that your designated Key Vault and key are accessible at all times.

### To enable data encryption

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](media/settings-icon.png "settings icon") and select **Settings**.

1. Select the **Data encryption** tab.

1. Click **Enable data encryption**.

1. In the **Azure Key Vault key URI** box, paste the key identifier URI value you copied earlier.

1. Once the URI validation has completed, click **Enable**.

> [!NOTE]
> When you disable data encryption, Cloud App Security removes the encryption with your own key from the data at rest. However, your data remains encrypted by Cloud App Security's managed keys.
>
> **To disable data encryption:** Go to the **Data encryption** tab and click **Disable data encryption**.

## Key roll handling

**// TBD: Speak to Yahav**

### Using versioned key

**// TBD: Speak to Yahav**

### Using unversioned key

**// TBD: Speak to Yahav**

## How to handle data encryption failures

If there is a problem accessing your Azure Key Vault key, Cloud App Security will fail to encrypt your data and your tenant will be lock down within an hour. When your tenant is locked down, all access to it will be blocked until the cause has been resolved. Once your key is accessible again, full access to your tenant will be restored. For information about handling data encryption failures, see [Troubleshooting data encryption with your own key](troubleshooting-data-encryption.md).
