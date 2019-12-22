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

Microsoft’s Cloud App Security encrypts data at rest for all new tenants as of {Date place holder}.

Any data which resides in Cloud App Security for more than 48 hours will be encrypted.

## Bring Your Own Key (BYOK)

It is possible to encrypt the data with your own key which is managed in your Azure Key Vault.

Note: Currently, BYOK is not supported if your Azure Key Vault uses a firewall.

## Setting up a designated Key Vault in Azure Key Vault

1. Create new Key Vault in your Azure Key Vault

1. Create an access policy and set the following parameters:
    1. Set Key permissions: Keys/Wrap, Keys/Unwrap, Keys/List
        1. Key management operations:
            1. List
        1. Cryptographic operations:
            1. Wrap key
            1. Unwrap key
    1. Principal: ??? @Yahav Amsalem What should be put here?

1. Create a new Key
    1. Set permitted operations:
        1. Wrap key
        1. Unwrap key

1. Copy key URI

1. [Set up **soft-delete** behavior for your Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete#soft-delete-behavior)

1. [Set up **no purge** behavior for your Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete#purge-protection)

## Enabling BYOK in MCAS

Enabling BYOK will use the provided key to encrypt your data at rest. It is important to maintain the designated Key Vault and Key state to enable a successful encryption process.

You can choose to setup the BYOK with a specific key version or version-less key.

To enable the BYOK:

1. Go to Settings page

1. Click on the Data Encryption – BYOK tab

1. Enable the BYOK by moving the toggle and verify the requirements

1. Paste the URI from the Key Vault

1. Once validation completes, Save the settings.

## Disabling BYOK in MCAS

Disabling BYOK encryption, will remove your encryption from the data. The data will remain encrypted by Microsoft managed keys.

To disable BYOK:

1. Go to setting page

1. Click on the Data Encryption – BYOK tab

1. Disable the BYOK by moving the toggle and verify the implications

## Key roll handling

### Using versioned key

### Using un-versioned key

## BYOK - Encryption failure handling

In the following scenarios, Cloud App Security will fail to encrypt your data and will start a tenant shut-down process within an hour – access to the tenant will be blocked. Once failure reason is handled, the tenant will become available again.

### Missing Key Vault permissions

Make sure the selected Key Vault has the following key permissions in the access policy:

- Key management operations:
  - List
- Cryptographic operations:
  - Wrap key
  - Unwrap key

### Missing Key permissions

Make sure the selected Key has the following permitted operations:

- Wrap key
- Unwrap key

### Encryption Key has expired

Make sure the selected key expiration date has no passed.

### Encryption key has an activation set for a later time

While setting up the BYOK, make sure the selected key activation time is prior to the current time.

### Azure Key Vault firewall blocks access to the encryption key

TBD

### Encryption key not found or deleted

Verify the key is available in your Key Vault – if key was disabled or deleted, please recover it and re-enable so Cloud App Security can continue with the encryption process.
