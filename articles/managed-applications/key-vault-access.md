---
title: Use Azure Key Vault with Managed Applications | Microsoft Docs
description: Shows how to use access secrets in Azure Key Vault when deploying Managed Applications
services: managed-applications
author: tfitzmac
manager: timlt

ms.service: managed-applications
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.date: 07/09/2018
ms.author: tomfitz
---
# Access Key Vault secret when deploying Azure Managed Applications

When you need to pass a secure value (like a password) as a parameter during deployment, you can retrieve the value from an [Azure Key Vault](../key-vault/key-vault-whatis.md). To access the Key Vault when deploying Managed Applications, you must grant access to the **Appliance Resource Provider** service principal. This article describes how to configure the Key Vault to work with Managed Applications.

## Enable template deployment

1. In the portal, select your Key Vault.

1. Select **Access policies**.   

   ![Select access policies](./media/key-vault-access/select-access-policies.png)

1. Select **Click to show advanced access policies**.

   ![Show advanced access policies](./media/key-vault-access/advanced.png)

1. Select **Enable access to Azure Resource Manager for template deployment**. Then, select **Save**.

   ![Enable template deployment](./media/key-vault-access/enable-template.png)

## Add service as contributor

1. Select **Access control (IAM)**.

   ![Select access control](./media/key-vault-access/access-control.png)

1. Select **Add**.

   ![Select add](./media/key-vault-access/add-access-control.png)

1. Select **Contributor** for the role. Search for **Appliance Resource Provider** and select it from the available options.

   ![Search for provider](./media/key-vault-access/search-provider.png)

1. Select **Save**.

## Next steps

You've configured your Key Vault to be accessible during deployment of a Managed Application.

* For information about passing a value from a Key Vault as a template parameter, see [Use Azure Key Vault to pass secure parameter value during deployment](../azure-resource-manager/resource-manager-keyvault-parameter.md).
* For managed application examples, see [Sample projects for Azure managed applications](sample-projects.md).
* To learn how to create a UI definition file for a managed application, see [Get started with CreateUiDefinition](create-uidefinition-overview.md).