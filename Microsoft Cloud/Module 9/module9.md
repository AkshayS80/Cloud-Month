# Module 9: Describe features and tools in Azure for governance and compliance

This is the Ninth Module of the Azure Fundementals Challenge

## Objectives

1. Describe the purpose of Microsoft Purview
2. Describe the purpose of Azure Policy
3. Describe the purpose of resource locks
4. Describe the purpose of the Service Trust portal

### Microsft Purview

Microsoft Purview is a set of tools for managing and understanding your data. It offers two main solutions: one for managing data risks and compliance, and another for creating a unified approach to managing data across different sources, whether they are on-premises, in the cloud, or from software-as-a-service providers. Key features include automated data discovery, classifying sensitive data, and tracking the lineage of data from source to destination.

##### Unified Data Governance

Microsoft Purview offers comprehensive data governance solutions for managing your data across various platforms, including on-premises, multicloud, and software-as-a-service. It helps you map your entire data landscape, classify data, and track its lineage from source to destination. You can also identify and secure sensitive data, provide a secure environment for data access, gain insights into data usage, and manage data access securely and efficiently at scale.

### Azure Policy

Azure Policy is a service in Azure that enables you to create, assign, and manage policies that control or audit your resources. These policies enforce different rules across your resource configurations so that those configurations stay compliant with corporate standards.

Azure Policy allows you to set rules for your resources and organize them into groups called initiatives. It checks if your resources follow these rules and can stop non-compliant resources from being created.

You can apply policies at different levels, and they are inherited down the hierarchy. Azure Policy offers predefined rules for various areas. It can even automatically fix issues, but you can exempt specific resources from these fixes. It also works with Azure DevOps for application deployment policies.

### Azure Policy Initiatives

Azure Policy initiatives group related policies together. They have a goal and include multiple policy definitions to help you track compliance for that goal. For example, the "Enable Monitoring in Azure Security Center" initiative aims to monitor security recommendations for all Azure resource types in Security Center. It contains various policy definitions, like checking for unencrypted SQL databases or missing endpoint protection.

### Resource Locks

Resource locks are like digital safety belts for your Azure resources. They prevent accidental deletion or changes, adding an extra layer of protection. You can use them on individual resources, groups of resources, or even your entire Azure subscription. Plus, they're inherited, so if you lock a group, everything inside stays protected too. There are two types:-

There are two types of resource locks in Azure. One stops users from deleting a resource, while the other stops them from changing or deleting it.

- **Delete Lock:** This lock allows users to read and modify a resource but prevents them from deleting it.

- **Read-Only Lock:** This lock allows users to only read a resource, just like the Reader role permissions, but they can't delete or update it.

You can manage resource locks from the Azure portal, PowerShell, the Azure CLI, or from an Azure Resource Manager template.
To view, add, or delete locks in the Azure portal, go to the Settings section of any resource's Settings pane in the Azure portal.

Resource locks provide protection against accidental changes, but if you need to make changes to a locked resource, you can follow a two-step process:

1. Remove the lock: To modify a locked resource, you must first remove the lock.

2. Apply your changes: After the lock is removed, you can make the desired changes as long as you have the necessary permissions. Resource locks work independently of RBAC permissions, so even if you have owner rights, you still need to remove the lock before making changes.

### Microsoft Service Trust Portal

The Microsoft Service Trust Portal (STP) is a one-stop shop for security, regulatory compliance, and privacy information related to the Microsoft cloud. The Service Trust Portal holds information about how Microsoft safeguards its cloud services and customer data. To access certain resources on this portal, you need to sign in using your Microsoft cloud services account, also known as an Azure Active Directory organization account. The Service Trust Portal features and content are accessible from the main menu. 


