# Module 5: Describe Azure compute and networking services

This is the Fifth Module of the Azure Fundementals Challenge

## Objectives

1. Compare compute types, including container instances, virtual machines, and functions.
2. Describe virtual machine options, including virtual machines (VMs), virtual machine scale sets, virtual machine availability sets, and Azure Virtual Desktop.
3. Describe resources required for virtual machines.
4. Describe application hosting options, including Azure Web Apps, containers, and virtual machines.
5. Describe virtual networking, including the purpose of Azure Virtual Networks, Azure virtual subnets, peering, Azure DNS, VPN Gateway, and ExpressRoute.
6. Define public and private endpoints.


### Azure Virtual Machines

Azure Virtual Machines (VMs) are like cloud-based computers that offer a lot of flexibility. You can customize everything on them, from the operating system to your own software. They're great when you want:

1. Full control over the operating system.
2. To run your own special software.
3. Customized hosting setups.

Azure VMs save you from dealing with physical hardware but still require you to set up and maintain the software. You can quickly create VMs using preconfigured templates called images, which may come with an operating system and other software already installed. This makes VM provisioning fast and easy.

##### Scale

In Azure, you can use virtual machines (VMs) for various purposes, whether it's testing, development, or important tasks. You can use a single VM or group them together for better performance and reliability. Azure provides two useful features for managing VM groups:

1. **Virtual Machine Scale Sets**: These allow you to create and manage a bunch of identical VMs that are load-balanced. Instead of setting up multiple VMs individually, Azure takes care of it for you. You can easily configure and update many VMs at once, and they can automatically scale up or down based on demand or a schedule. This is great for large-scale services like computing, big data, or containers.

2. **Virtual Machine Availability Sets**: These help you create a more resilient and highly available environment. They group VMs to ensure they don't all go offline together due to updates or failures. Azure does this by separating VMs into two ways: update domains (for updates) and fault domains (for hardware/network protection). You don't have to pay extra for using availability sets; you only pay for the VMs themselves.

These features make managing groups of VMs easier, more reliable, and cost-effective.

### Azure virtual desktop

Azure Virtual Desktop is a cloud-based service that lets you use a Windows desktop from anywhere, using different devices and web browsers. It's secure and managed centrally through Azure Active Directory. You can add extra security layers like multi-factor authentication and control who can access what using role-based access controls. Your desktop and apps don't depend on your local device. They run in the cloud, so there's less risk of data exposure on personal devices. Plus, user sessions are kept separate, whether it's one user or multiple users sharing the same environment.

### Azure Containers 

Containers are like lightweight virtual machines that run applications. They share the same operating system as the host machine, making them efficient and quick to start. Unlike traditional virtual machines, you don't need to manage the underlying operating system for containers. They're great for quickly responding to changes, recovering from crashes, and scaling applications up or down as needed. Docker is a popular tool for managing containers, and Azure supports it.

##### Azure Containers Instances
The quickest and simplest way to run a container in Azure without dealing with virtual machines. Just upload your container, and Azure handles the rest.

##### Azure Containers Apps
Similar to Container Instances but with added benefits like load balancing and scaling, providing more flexibility in your design. It's also a platform as a service (PaaS) offering.

##### Azure Kubernetes Service
A container orchestration service that simplifies the management of container fleets, making it easier and more efficient to deploy and manage multiple containers.

### Azure functions

Azure Functions is a serverless computing option that automatically activates when an event occurs, eliminating the need for continuously running virtual machines or containers. This means you only pay for the computing power you use when your function is triggered by an event.

Azure Functions are great for focusing solely on your code without worrying about the underlying infrastructure. They're ideal for responding to events, timers, or messages, especially when the tasks are quick. Functions scale automatically based on demand, making them cost-effective for variable workloads. They run your code when needed and stop when done, so you only pay for the time your function runs.

Functions can be stateless or stateful (Durable Functions), and they're a core part of serverless computing. If your app's requirements change, you can deploy it in a different environment without serverless constraints, giving you flexibility in managing scalability and networking.

### Application hosting options

When hosting your application on Azure, you have two main options: virtual machines (VMs) and containers. VMs offer maximum control over the hosting environment, allowing precise configuration. Containers, on the other hand, provide isolation and individual management for various parts of your hosting solution, making them a powerful choice. There are other hosting options in Azure, like App Service.

##### App Service

Azure App Service is a powerful hosting solution for web apps, APIs, and more. It allows you to build and host applications without worrying about managing infrastructure. App Service supports various programming languages, automatic scaling, and high availability. You can deploy your code from Git repositories, ensuring continuous deployment. It's a hassle-free way to focus on your app while Azure takes care of the underlying environment.

Azure App Service is a versatile platform that can host various types of web-based applications, making it an excellent choice for developers. Here are some key features and application styles you can host with App Service:

1. **Web Apps**: You can host web applications written in languages like ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP, or Python. App Service supports both Windows and Linux.

2. **API Apps**: Just like hosting websites, you can create REST-based web APIs using your preferred language and framework. App Service provides full Swagger support, making it easy to publish your API on Azure Marketplace for consumption by HTTP- or HTTPS-based clients.

3. **WebJobs**: WebJobs allow you to run programs or scripts (in various languages) within the same context as your web app, API app, or mobile app. You can schedule them or trigger them as needed, often used for background tasks.

4. **Mobile Apps**: App Service's Mobile Apps feature helps you build back ends for iOS and Android applications rapidly. You can store app data in a cloud-based SQL database, handle customer authentication with social providers, send push notifications, and execute custom back-end logic in languages like C# or Node.js. SDK support is available for native iOS and Android, Xamarin, and React Native apps.

App Service simplifies deployment, management, security, scalability, and availability, making it a flexible and efficient choice for hosting web-oriented applications.

### Azure virtual networking

Azure virtual networks and subnets create a network environment for Azure resources like VMs, web apps, and databases. These resources can interact with each other, the internet, and your on-premises computers. Essentially, Azure networks extend your on-premises network into the Azure cloud.

Key capabilities of Azure virtual networks include:

1. **Isolation and Segmentation**:Azure lets you create isolated virtual networks. Each virtual network has its private IP address space that doesn't connect directly to the internet. You can divide this space into subnets for organization. Azure provides name resolution services and lets you configure DNS settings.

2. **Internet Communication**: You can make Azure resources accessible from the internet by assigning public IP addresses or using a public load balancer.

3. **Azure Resource Communication**: Azure resources can securely communicate within the network. This includes VMs, App Service Environments, Azure Kubernetes Service, and more. Service endpoints can connect various Azure resource types, improving security and routing.

4. **On-Premises Communication**: Azure virtual networks allow you to connect your on-premises resources with Azure resources. This can be done through point-to-site VPNs, site-to-site VPNs, or Azure ExpressRoute for dedicated private connections.

5. **Traffic Routing**: Azure routes traffic between subnets, on-premises networks, and the internet by default. You can customize routing with route tables, and Border Gateway Protocol (BGP) for on-premises connections.

6. **Traffic Filtering**: You can filter traffic between subnets using Network Security Groups (NSGs) that define rules for allowing or blocking traffic. Network Virtual Appliances (NVAs) offer specialized network functions like firewalls.

7. **Connecting Virtual Networks**: Azure supports virtual network peering, allowing two virtual networks to connect directly. This connection is private and secure, using Microsoft's backbone network. User-Defined Routes (UDR) provide control over traffic flow between subnets within or between virtual networks.

Azure networking supports two types of endpoints:

- **Public Endpoints**: These have public IP addresses and are accessible from anywhere globally.

- **Private Endpoints**: These exist within a virtual network and have private IP addresses within that network's address space.

In simple terms, Azure virtual networks and subnets provide the framework for Azure resources to communicate, whether it's within Azure, with the outside world, or with your on-premises systems.

### Virtual Private Networks(VPNs)

A virtual private network (VPN) creates a secure, encrypted connection within a network, often used to link trusted private networks over an untrusted network, like the internet. It ensures data is protected from eavesdropping and attacks, allowing secure sharing of sensitive information.

##### Gateways

A VPN gateway in Azure is like a special network gateway that helps different things connect securely:

1. **Site-to-Site**: It connects your company's datacenter to your Azure virtual network, allowing them to talk to each other safely.

2. **Point-to-Site**: It connects individual devices (like laptops) to your Azure virtual network, giving them secure access.

3. **Network-to-Network**: It connects different Azure virtual networks together, so they can communicate securely.

In Azure, VPNs are managed through VPN gateways, which serve these purposes:

1. **Connectivity**: VPN gateways in Azure connect different networks, including on-premises datacenters, individual devices, and virtual networks. All data sent through a VPN gateway is encrypted for security. Each virtual network can have one VPN gateway, which can link to multiple locations.

2. **Types of VPNs**: There are two main types of VPNs in Azure - policy-based and route-based. Policy-based VPNs specify specific IP addresses that should be encrypted through each tunnel. In contrast, route-based VPNs use IP routing to decide which tunnel to use for each packet. Route-based VPNs are more flexible and resilient to changes like adding new subnets.

3. **Authentication**: Regardless of VPN type, Azure VPN gateways use a pre-shared key for authentication.

4. **Use Cases**: Route-based VPN gateways are preferred for various scenarios, including connecting virtual networks, point-to-site connections, multisite connections, and coexisting with an Azure ExpressRoute gateway.

##### High Availability Options

Azure VPN gateways offer various high-availability options:

1. **Active/standby**: By default, there are two instances, and if one has issues, the other takes over quickly.

2. **Active/active**: You can have two instances with unique IP addresses, great for load distribution.

3. **ExpressRoute failover**: In case of problems with ExpressRoute connections, a VPN gateway can act as a backup using the internet.

4. **Zone-redundant gateways**: For regions with availability zones, gateways can be deployed across zones for resilience and better availability.

### Azure ExpressRoute

Azure ExpressRoute is a way to connect your on-premises network to Microsoft's cloud services, like Azure and Microsoft 365, using a private connection provided by a connectivity provider. This connection is called an ExpressRoute Circuit. It's like a dedicated highway between your location (office, datacenter, etc.) and Microsoft's cloud. Each location has its own ExpressRoute circuit.

You can establish this connection in different ways, like through an IP VPN network, a direct Ethernet link, or a virtual connection at a colocation facility. Importantly, ExpressRoute doesn't use the public Internet, which makes it more reliable, faster, and more secure compared to regular Internet connections.

##### Advantages

Using ExpressRoute offers multiple advantages when connecting Azure and on-premises networks:

1. **Connectivity Across Regions**: You can access Microsoft cloud services from any location within a specific geopolitical region.

2. **Global Connectivity**: With ExpressRoute Global Reach, you get worldwide access to Microsoft services across all regions.

3. **Dynamic Routing**: ExpressRoute uses Border Gateway Protocol (BGP) for intelligent and efficient routing between your network and Microsoft's cloud.

4. **Redundancy**: There's built-in redundancy at every peering location, ensuring a highly reliable connection.

##### Connectivity Models

ExpressRoute provides four connectivity models to link your on-premises network with the Microsoft cloud:

1. **Co-location at a Cloud Exchange**: Your datacenter or facility is physically located at a cloud exchange, allowing you to request a virtual cross-connect to Microsoft's cloud.

2. **Point-to-Point Ethernet Connection**: You establish a dedicated point-to-point connection from your facility to the Microsoft cloud.

3. **Any-to-Any Networks**: This option lets you integrate your Wide Area Network (WAN) with Azure, connecting your offices and datacenters to Azure as if they were branch offices.

4. **Directly from ExpressRoute Sites**: You can directly connect to Microsoft's global network at peering locations worldwide. ExpressRoute Direct offers high-speed, scalable connectivity options, such as dual 100 Gbps or 10 Gbps connections, supporting Active/Active connectivity at a large scale.

##### Security Considerations

ExpressRoute provides a private connection between your on-premises infrastructure and Azure, so your data doesn't travel over the public internet, reducing potential security risks. However, certain tasks like DNS queries, certificate checks, and Azure Content Delivery Network requests still use the public internet.

### Azure DNS

Azure DNS is a service that helps manage domain names and their corresponding IP addresses in the Microsoft Azure cloud. It offers several advantages:
1. **Reliability and performance:** Azure DNS uses a global network of servers to provide fast and reliable domain name resolution. It's designed for high availability and responds quickly to DNS queries.
2. **Security:** It includes security features like role-based access control, activity logs, and resource locking to protect your DNS configuration.
3. **Ease of use:** Azure DNS integrates seamlessly with other Azure services, using the same credentials and billing. You can manage your domains and records through the Azure portal, PowerShell, or the Azure CLI.
4. **Customizable virtual networks:** You can use your own domain names within private virtual networks, rather than relying on Azure-generated names.
5. **Alias records:** Azure DNS supports alias records that can point to Azure resources like public IP addresses, Traffic Manager profiles, or Content Delivery Network endpoints. These aliases automatically update if the resource's IP address changes.