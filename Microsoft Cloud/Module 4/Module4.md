# Module 3:  Describe the core architectural components of Azure 

This is the Fourth Module of the Azure Fundementals Challenge

## Objectives

1. Describe Azure regions, region pairs, and sovereign regions.
2. Describe Availability Zones.
3. Describe Azure datacenters.
4. Describe Azure resources and Resource Groups.
5. Describe subscriptions.
6. Describe management groups.
7. Describe the hierarchy of resource groups, subscriptions, and management groups.

### Subscription

To use Azure services, you require an **Azure subscription**. Once you have an Azure account, you can also generate additional subscriptions. For instance, your company might have one Azure account for the business as a whole and separate subscriptions for its development, marketing, and sales departments. Once you have an Azure subscription, you can start creating Azure resources within each of these subscriptions.

### Learn Sandbox

In Learn exercises, Sandbox is used to make a temporary subscription within your Azure account. This temporary subscription lets you make Azure resources while you're working on a Learn module. After you finish the module, Learn takes care of cleaning up these temporary resources for you.

There are three ways you can interact with the sandbox:

1. **PowerShell CLI**: PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework.
<ul>
<li>
To get the date and time 
```cmd
Get-date
```
</li>
<li>
To check your Azure Version
```cmd
Get-date
```
</li>
</ul>

2. **Bash CLI**: Bash is a Unix shell and command language written by Brian Fox for the GNU Project as a free software replacement for the Bourne shell. First released in 1989, it has been used as the default login shell for most Linux distributions. Bash was one of the first programs Linus Torvalds ported to Linux, alongside GCC.

3.  **Azure CLI interactive mode**: The Azure Command-Line Interface (CLI) is a cross-platform command-line tool to connect to Azure and execute administrative commands on Azure resources. It allows the execution of commands through a terminal using interactive command-line prompts or a script.

### Azure Physical Infrastructure

The main architectural components can be divided into two types:
1. **The physical infrastructure**

Azure's physical infrastructure are facilities filled with equipment neatly organized, powered, cooled, and connected.
Azure operates data centers worldwide, but you can't access each one directly. Instead, they're organized into Azure Regions or Azure Availability Zones to enhance the reliability and resilience of your important tasks. It includes:

1. Regions
A region is like a part of the world with one or more nearby data centers. Azure carefully manages resources in each region to keep things running smoothly.

2. Availability zones 
Availability zones are separate data centers in a region. Each one has its own power, cooling, and network. They're like backup centers. If one has trouble, the others keep working. They're connected with super-fast, private networks.

3. Region Pairs
Azure regions are often paired with another region far away, like in a different part of the world. This helps make sure your stuff keeps running even if there's a problem, like a natural disaster or power outage. If one region has trouble, your services switch to the other one in the pair automatically.

4. Sovereign Regions

Apart from regular Azure regions, there are also special ones called sovereign regions. These sovereign regions are like separate, isolated parts of Azure used for specific reasons, like following certain laws.

2. **The management infrastructure**

The management infrastructure includes Azure resources and resource groups, subscriptions, and accounts.

1. Azure resources and resource groups

In Azure, a resource is like a fundamental building block, and it can be anything you create or use, like Virtual Machines, databases, or services.

Resource groups, on the other hand, are like containers for resources. You have to put each resource you create into a resource group. While a resource group can hold multiple resources, a single resource can only be in one group at a time. You can move some resources between groups, but doing so disconnects them from the old group. Also, you can't put one resource group inside another.

2. Azure subscriptions

You need an Azure subscription to use Azure services. It gives you access to Azure products, lets you create resources, and is linked to an Azure account, which is like your ID in Azure Active Directory.

One account can have several subscriptions, but you only need one. If you have multiple subscriptions, you can set different billing and access rules for each. This helps you manage costs and control access to Azure stuff.

3. Azure Management groups:
Management groups are like super-containers for subscriptions. You can put multiple subscriptions into a management group and set rules for them. These rules apply to all the subscriptions within that group.

So, management groups help you manage lots of subscriptions efficiently, keeping everything organized, secure, and compliant, no matter how complex your setup is.