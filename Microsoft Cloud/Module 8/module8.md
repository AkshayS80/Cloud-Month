# Module 8: Describe cost management in Azure

This is the Eighth Module of the Azure Fundementals Challenge

## Objectives

1. Describe factors that can affect costs in Azure
2. Compare the Pricing calculator and Total Cost of Ownership (TCO) calculator
3. Describe the Microsoft Cost Management tool
4. Describe the purpose of tags

### Factors that can affect costs in Azure

Azure changes the way you pay for your resources. Instead of spending money upfront on infrastructure, you pay for what you use as an ongoing expense. Many factors affect how much you pay, including the type of resources, how much you use them, where they're located, your subscription type, and what you get from the Azure Marketplace.

##### Resource Type

Several factors determine how much you pay for Azure resources. The type of resource, its settings, and where it's located in Azure all affect the cost. Azure keeps track of your resource usage with meters and calculates your bill based on the usage records they generate.

##### Consumption

Azure offers two payment models: pay-as-you-go and reserved capacity. With pay-as-you-go, you pay for what you use each billing cycle. Reserved capacity lets you commit to using a certain amount of Azure resources for a fixed period, getting discounts of up to 72%. If your demand exceeds your reservation, you pay extra, providing cost savings for steady workloads while allowing flexibility for surges.

##### Maintainence

The cloud's flexibility allows quick resource adjustments based on demand. Organizing resources into groups, like resource groups, helps with organization. Cost control is crucial in managing your cloud environment. For instance, when you create a VM, it comes with additional resources like storage and networking. Removing a VM may not remove these additional resources right away. Monitoring your resources and removing unnecessary ones can help manage cloud costs effectively.

##### Geography and Costs
When you create Azure resources, you choose a region for deployment. Costs can vary by region due to factors like power and labor expenses. Moving data between regions can also affect costs.

##### Network Traffic Costs
Billing zones impact the cost of some Azure services. Bandwidth, which is data moving in and out of Azure datacenters, has pricing based on zones. Zones are groups of Azure regions for billing.

##### Subscription Type
Different Azure subscriptions come with usage allowances that influence costs. For instance, a free trial subscription provides access to some Azure products for free during the first year.

##### Azure Marketplace
Here, you can buy Azure-based solutions from third-party vendors. Costs may include Azure services and the vendor's services. All solutions in Azure Marketplace meet Azure's standards.

## Pricing and Total Cost of Ownership calculators

The pricing calculator and the total cost of ownership (TCO) calculator are two calculators that help you understand potential Azure expenses. Both calculators are accessible from the internet, and both calculators allow you to build out a configuration. 

##### Pricing calculator 

The pricing calculator helps you estimate the cost of using Azure resources. You can calculate costs for specific resources, plan out an entire solution, or use example scenarios. It covers resources like computing, storage, and network expenses. You can also factor in storage details like type, access, and redundancy.

##### Total Calculator

The TCO calculator helps you compare the costs of running your current on-premises infrastructure to using Azure Cloud. You input your existing setup, including servers, databases, storage, and network usage. Then, the calculator shows you the expected costs for both your current setup and for the same infrastructure in Azure. It considers factors like power and labor expenses to provide cost comparisons.

## Cost Management tool

Cost Management in Azure lets you easily monitor and manage your resource expenses. It enables you to check resource costs, set up alerts for spending limits, and create budgets to automate resource management.

Cost analysis is a part of Cost Management that offers a visual representation of your Azure expenses. With cost analysis, you can quickly see your total costs using various filters like billing cycle, region, or resource type. You can use it to investigate and understand your organizational spending patterns, see where costs are accumulating, and predict future expenses against your budget.

Cost alerts serve as a centralized place to monitor various types of alerts in the Cost Management service. There are three alert types:
- Budget alerts
- Credit alerts
- Department spending quota alerts

1. Budget alerts 

Budget alerts let you know when your spending, either based on usage or cost, reaches or surpasses a predefined amount set in your budget alert conditions. You can create these budgets in the Azure portal or using the Azure Consumption API. They support both cost and usage-based budgets. When the conditions are met, budget alerts are automatically generated and appear in the Azure portal. Alert emails are also sent to the designated recipients.

2. Credit alerts 

Credit alerts are triggered when your Azure credit for Enterprise Agreements (EAs) is utilized. These alerts are generated at two stages: when your credit balance hits 90% and when it reaches 100%. Credit alerts are shown in cost alerts and are communicated to the account owners through email.

3. Department spending quota alerts

Department spending quota alerts notify department owners when their spending reaches a predefined threshold of the quota. These quotas are configured within the EA portal. When the spending crosses the threshold, email alerts are sent to department owners, and the alerts also appear in cost alerts. For instance, alerts can be set at 50% or 75% of the quota.

## Budgets

A budget in Azure is like setting a spending limit. You can set budgets based on various factors like subscriptions, resource groups, or service types. When you create a budget, you also define a budget alert level. When your spending reaches this level, it triggers a budget alert that you can see in cost alerts. Additionally, if you choose, budget alerts can send you an email notification to inform you that your budget has reached the alert threshold.

## Tags
Tags provide extra information about resources. They help with:

- Resource Management: Locate and manage resources for specific workloads, units, or owners.
- Cost Management: Group resources for cost reporting, budget tracking, and forecasting.
- Operations Management: Categorize resources based on their criticality for forming service-level agreements (SLAs).
- Security: Classify data based on security levels.
- Governance and Compliance: Identify resources aligning with governance or regulatory requirements.
- Workload Optimization: Visualize resources in complex deployments and automate tasks.
