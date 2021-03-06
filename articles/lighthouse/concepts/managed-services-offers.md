---
title: Managed services offers in Azure Marketplace
description: Managed services offers allow service providers to sell resource management offers to customers in Azure Marketplace.
ms.date: 03/17/2020
ms.topic: conceptual
---

# Managed services offers in Azure Marketplace

This article describes the new **Managed Services** offer type in [Azure Marketplace](https://azuremarketplace.microsoft.com). Managed services offers allow you to offer resource management services to customers with Azure delegated resource management. You can make these offers available to all potential customers or only to one or more specific customers. Since you bill customers directly for costs related to these managed services, there are no fees charged by Microsoft.

## Understand managed services offers

Managed services offers streamline the process of onboarding customers for Azure delegated resource management. When a customer purchases an offer in Azure Marketplace, they'll be able to specify which subscriptions and/or resource groups should be onboarded. Note that the subscription must first be authorized for onboarding by manually registering the **Microsoft.ManagedServices** resource provider.

After that, users in your organization will be able to perform administration tasks for those resources from within your organization's tenant, according to the access you defined when creating the offer in the [Cloud Partner Portal](https://cloudpartner.azure.com/). This is done through a manifest that specifies the Azure AD users, groups, and service principals that will have access to customer resources using Azure delegated resource management, along with roles that define their level of access. By assigning permissions to an Azure AD group rather than a series of individual user or application accounts, you can add or remove individual users when your access requirements change.

## Public and private offers

Each managed services offer includes one or more plans. Plans can be either private or public. 

If you want to limit your offer to specific customers, you can publish a private plan. When you do so, the plan can only be purchased for the specific] subscription IDs that you provide. For more info, see [Private offers](../../marketplace/private-offers.md).

Public plans let you promote your services to new customers. These are usually more appropriate when you only require limited access to the customer's tenant. Once you've established a relationship with a customer, if they decide to grant your organization additional access, you can do so either by publishing a new private plan for that customer only, or by [onboarding them for further access using Azure Resource Manager templates](../how-to/onboard-customer.md).

If appropriate, you can include both public and private plans in the same offer.

> [!IMPORTANT]
> Once a plan has been published as public, you can't change it to private. To control which customers can accept your offer and delegate resources, use a private plan. With a public plan, you can't restrict availability to certain customers or even to a certain number of customers (although you can stop selling the plan completely if you choose to do so). You can [remove access to a delegation](../how-to/onboard-customer.md#remove-access-to-a-delegation) after a customer accepts an offer only if you included an **Authorization** with the **Role Definition** set to [Managed Services Registration Assignment Delete Role](../../role-based-access-control/built-in-roles.md#managed-services-registration-assignment-delete-role) when you published the offer. You can also reach out to the  customer and ask them to [remove your access](../how-to/view-manage-service-providers.md#add-or-remove-service-provider-offers).

## Publish managed service offers

To learn how to publish a managed services offer, see [Publish a Managed Services offer to Azure Marketplace](../how-to/publish-managed-services-offers.md). For general info about publishing to Azure Marketplace using the Cloud Partner Portal, see [Azure Marketplace and AppSource Publishing Guide](../../marketplace/marketplace-publishers-guide.md) and [Manage Azure and AppSource Marketplace offers](../../marketplace/cloud-partner-portal/manage-offers/cpp-manage-offers.md).

## Next steps

- Learn about [Azure delegated resource management](azure-delegated-resource-management.md) and [cross-tenant management experiences](cross-tenant-management-experience.md).
- [Publish managed services offers](../how-to/publish-managed-services-offers.md) to Azure Marketplace.
