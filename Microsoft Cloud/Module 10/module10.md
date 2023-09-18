# Module 10: Describe features and tools for managing and deploying Azure resources

This is the Tenth Module of the Azure Fundementals Challenge

## Objectives

1. Describe Azure portal
2. Describe Azure Cloud Shell, including Azure CLI and Azure PowerShell
3. Describe the purpose of Azure Arc
4. Describe Azure Resource Manager (ARM) and Azure ARM templates

### Azure Portal

The Azure portal is like a user-friendly control center on the internet for managing your Azure subscription. It's a place where you can do a bunch of things, like handling simple web apps or dealing with more complicated cloud stuff. You can even make custom dashboards to keep things organized and set it up to work well for you.

The neat thing about it is that it's built to be super reliable. It's always available and doesn't need to go offline for maintenance. Plus, it's spread out across all of Azure's datacenters, so it stays speedy and won't slow down.

### Azure Cloud Shell

Azure Cloud Shell is like a special tool in your web browser that helps you control and work with Azure stuff. You can create, set up, and manage Azure resources right there in your browser. It's got two different ways to talk to Azure, either using Azure PowerShell or the Azure Command Line (which is like a type of code).

What's cool about it is you don't need to install anything on your computer; it's all set up in your web browser. And when you log in, it knows who you are and what you can do in Azure, so you don't have to keep typing in your info. You can use whichever way of talking to Azure you like best, whether that's with the PowerShell or the Command Line.

### Azure PowerShell

Azure PowerShell is like a special tool for developers and IT folks. It lets them give commands (called "cmdlets") that talk to Azure and get things done. These commands can be small tasks or big, complicated jobs. People use Azure PowerShell to do things like setting up and taking down stuff in Azure, or even creating whole systems with lots of parts. When they put these commands in a script, it means they can do the same tasks again and again without typing everything out each time and you can use Azure PowerShell on different types of computers, like Windows, Linux, and Mac. So, it's pretty handy for lots of different jobs.

### Azure CLI

The Azure CLI is similar to Azure PowerShell, but it uses different words to give commands. Azure PowerShell talks in PowerShell, while the Azure CLI uses Bash. Just like Azure PowerShell, the Azure CLI helps with simple tasks and big projects, and you can use it on Windows, Linux, Mac, or even in Azure Cloud Shell. The choice between Azure PowerShell and the Azure CLI is mostly about which language you know better. 

### Azure Arc

Azure Arc helps you keep an eye on your hybrid and multi-cloud setup using Azure Resource Manager (ARM). It makes managing and controlling everything easier by giving you a consistent way to oversee your resources.

With Azure Arc, you can:
- Bring all your resources, even non-Azure ones, into ARM for easier management.
- Manage virtual machines, Kubernetes clusters, and databases from different clouds like they're part of Azure.
- Use familiar Azure tools and features no matter where your stuff is.
- Blend traditional ITOps and modern DevOps approaches.
- Create custom locations for your Azure Arc-enabled Kubernetes clusters and extensions.

In simpler terms, Azure Arc makes managing your mix of cloud and on-premises tech more streamlined and consistent.

It can also manage the following types of resources hosted outside of Azure:
<ul>
<li>Servers</li>
<li>Kubernetes clusters</li>
<li>Azure data services</li>
<li>SQL Server</li>
<li>Virtual machines (preview)</li>
</ul>

### Azure Resource Manager and ARM templates

Azure Resource Manager (ARM) helps you create, change, and remove things in your Azure account. When you use any Azure tools or apps, ARM takes your requests, checks if it's really you, and then talks to Azure to make things happen. No matter which tool you use, it all works the same way because they all use ARM behind the scenes.

With Azure Resource Manager, you can:
1. Manage your stuff using templates instead of scripts. 
2. Handle all your resources together, not one by one.
3. Easily redo your setup as you develop and make sure everything stays the same.
4. Make sure things are set up in the right order.
5. Control who can do what because it's built into the system.
6. Label your stuff to keep it organized.
7. Check how much things cost by grouping them together with labels.

With ARM templates, you describe what you want to create in a special code format (JSON). The code is checked first to make sure it's right. Then, it makes all the stuff you want at the same time. For example, if you need 50 of something, it makes all 50 together. The best part is you only have to say what you want, and the template does the work. It can even run other code before or after making it.

Benefits of using ARM templates:
1. **Declarative Syntax**: ARM templates let you make a whole Azure setup without writing detailed commands. You just say what you want, and it does the rest.
2. **Repeatable**: You can use the same plan to make things many times during development. You know they will be exactly the same every time.
3. **Orchestration**: Azure Resource Manager takes care of making things in the right order, so you don't have to figure it out. It can also make many things at the same time to save time.
4. **Modular**: You can make smaller parts of your plan that you can use again and again. You can connect them when you need to use them. 
5. **Extensible**: You can attach PowerShell or Bash scripts to your templates, known as deployment scripts. These scripts help you set up your resources while deploying. You can include the script in your template or keep it in an external place and point to it from the template. 

### Infrastructure as a Code

Infrastructure as code means managing your digital resources using code. When you start, it's like using tools to control your resources in the cloud. As you become more skilled, you can use code to manage whole setups, making it easy to repeat and keep consistent. For example, you can use ARM templates or Bicep to control your Azure environment using this concept.

### Bicep 

Bicep is like a language that helps you set up Azure resources. Instead of using long and complex code like ARM templates in JSON, Bicep uses a shorter and simpler style to describe your Azure environment. It's a more straightforward language to tell Azure how to create your resources.

Bicep offers several advantages, including:

1. **Immediate Support for New Services:** Bicep works with all Azure services and their latest versions as soon as they are released. You don't need to wait for updates to use new Azure services.

2. **Simplified Syntax:** Bicep code is shorter and easier to understand than equivalent JSON templates. You don't need to be a programmer to use it. Bicep uses clear language to describe the resources you want to create.

3. **Consistent Deployments:** Bicep files ensure that your Azure resources are deployed consistently every time. You can deploy the same file multiple times without worrying about changes.

4. **Efficient Orchestration:** Bicep automates the deployment of resources, handling their interdependencies and deploying them in parallel whenever possible. You can deploy resources using a single command.

5. **Modularity:** You can break your Bicep code into reusable modules, simplifying your development process and promoting code reuse. These modules can be easily added to other Bicep files when needed.