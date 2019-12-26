---
# required metadata
title: Manage encryption for Cloud App Security data
description: This article provides instructions for configuring encryption for data stored in Cloud App Security.
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
# Manage encryption for Cloud App Security data

*Applies to: Microsoft Cloud App Security*

**// OVERVIEW:** PMs to provide. Affects all content in this section and BYOK section

Microsoft’s Cloud App Security encrypts data at rest for all new tenants as of **{Date place holder}**.

Any data that resides in Cloud App Security for more than 48 hours will be encrypted.

Bring your own key (BYOK) allows you to encrypt data using your own key that you manage in your Azure Key Vault.

## Set up your Azure Key Vault key

1. [Create a new Key Vault](https://docs.microsoft.com/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key-vault).

1. Create an access policy, fill out the following information, and then click **Add**.
    1. Click **Key permissions** and choose the following permissions from the dropdown menu:

        | Section | Required permissions |
        | --- | --- |
        | Key Management Operations | - List |
        | Cryptographic Operations | - Wrap key<br />- Unwrap key |

        ![Screenshot showing the selection of key permissions](media/byok-kv-access-policy-key-perms.PNG)

    2. Principal: **// TBD**

        ![Screenshot showing add access policy page](media/byok-kv-add-access-policy.PNG)

1. [Create a new Key](https://docs.microsoft.com/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key), do the following, and then click **Add**.
    1. Under **Permitted operations**, select the following options:

        - Wrap key
        - Unwrap key

    2. Under **Key Identifier**, copy the URI. You'll need this later.

    ![Screenshot showing key settings page](media/byok-kv-key-perms.PNG)

1. [Set up the **soft-delete** behavior for your Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete#soft-delete-behavior).

1. [Set up the **no purge** behavior for your Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete#purge-protection).

1. Optionally, if using a firewall for a selected network, configure the following firewall settings to give Cloud App Security access the specified key, and then click **Save**:
    1. Make sure no virtual networks are selected.
    1. Add the following IP addresses: // Require list of MCAS IP addresses

    ![Screenshot showing firewall configuration](media/byok-kv-firewall.PNG)

## Enable data encryption in Cloud App Security

When you enable data encryption, Cloud App Security immediately uses your Azure Key Vault key to encrypt data at rest. Since your key is essential to the encryption process, it is important to ensure that your designated Key Vault and Key are accessible at all times.

You can choose to set up data encryption with an unversioned key or a specific key version.

### To enable the data encryption

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](media/settings-icon.png "settings icon") and select **Settings**.

1. Click the **Data encryption** tab.

1. Click **Enable data encryption**.

1. In the **Azure Key Vault key URI** box, paste the URI value you copied earlier.

1. Once the URI validation has completed, click **Enable**.

## Disable data encryption in Cloud App Security

When you disable data encryption, Cloud App Security removes your encryption from the data. However, your data remains encrypted by Cloud App Security's managed keys.

### To disable the data encryption

1. In Cloud App Security, in the menu bar, click the settings cog ![settings icon](media/settings-icon.png "settings icon") and select **Settings**.

1. Click the **Data encryption** tab.

1. Click **Disable data encryption**.

## Key roll handling

### Using versioned key

### Using unversioned key

## How to handle data encryption failures

In the event of there being a problem with accessing your Azure Key Vault key, Cloud App Security will fail to encrypt your data and your tenant's lockdown process will be initiated within the hour. Once your tenant is locked down, all access to it will be blocked until the cause has been resolved. Once your key is accessible again, full access to your tenant will be restored.

The following table lists the possible scenarios that can cause the data encryption to fail and the steps you can take to resolve them:

| Scenario | Steps |
| --- | --- |
| <a name="missing-kv-permissions"></a>**Missing Key Vault permissions** | In the selected Key Vault, under access policy, make sure that the following key permissions are selected:<br />Under **Key management operations**<br />- List<br />Under **Cryptographic operations**<br />- Wrap key<br />- Unwrap key |
| <a name="firewall-block"></a>**Azure Key Vault firewall blocking access to key** | In the selected Key Vault, make sure that the filewall is configured with the following IP addresses: // Require list of MCAS IP addresses |
| <a name="missing-key-permissions"></a>**Missing key permissions** | In the selected key, make sure that the following operations are permitted:<br />- Wrap key<br />- Unwrap key |
| <a name="key-not-enabled"></a>**Encryption key is not enabled** | In the selected key, make sure that enabled is turned on. ![Screenshot showing key enable option](media/byok-kv-key-enabled.PNG) |
| <a name="key-not-active"></a>**Encryption key is not active** | In the selected key, make sure that the activation date and time is prior to the current date and time. ![Screenshot showing key activation date](media/byok-kv-key-activation-date.PNG) |
| <a name="key-expired"></a>**Encryption key has expired** | In the selected key, make sure that the expiration date and time has not passed. ![Screenshot showing key expiration date](media/byok-kv-key-expiration-date.PNG) |
| <a name="key-not-found"></a>**Encryption key not found or deleted** | Verify that the selected key exists in your Key Vault. If key was deleted, recover and enable it again. If the key was moved to another Key Vault, move it back to this Key Vault. |
