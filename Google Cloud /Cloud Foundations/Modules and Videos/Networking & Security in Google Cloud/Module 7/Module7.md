# Module 7: It helps to network

This is the Seventh Module of the Entire Cloud Computing Foundations Course. It contains the labs:-
1. GSP211 -- Multiple VPC Networks
2. GSP213 -- VPC Networks - Controlling Access
3. GSP215 -- HTTP Load Balancer with Cloud Armor

## Objectives

1. Explore Virtual Private Clouds (VPCs).
2. Examine Google’s network architecture.
3. Learn how to use multiple VPC networks.
4. Explore options to build hybrid clouds.
5. Examine load balancing options.

### Networking in the Cloud

Computers communicate through **networks**. They started small with the **LANs** and kept moving through the **WANs** and finally reached the pinnacle of connection called the **internet**.

In Google Cloud, a "network" is an isolated global resource holding network configuration. Instances are deployed in regional subnetworks, however the policy (firewall, routing, and so on), and access through VPN, are configured at the global network level.

### Virtual Private Clouds

A Virtual Private Cloud, or VPC, is a secure, individual, private cloud-computing model hosted within a public cloud. In a Virtual Private Cloud (VPC), clients can do everything they normally do in a regular private cloud, like running code, storing data, and hosting websites. The main difference is that this private cloud is located on servers managed by a public cloud provider. VPCs basically combine the scalability and user-friendliness of public cloud computing with the data security and isolation of private cloud computing.

Google VPC networks are global and can contain subnets, which are smaller segments within the network, located in any Google Cloud region worldwide. These subnets can extend across the various zones within a region, simplifying the process of creating network structures with a global reach.

Google Cloud offers two types of VPC networks, determined by their subnet creation mode: 
1. Auto subnet mode 
2. Custom subnet mode.

### The basics of public and internal IP addresses

A Virtual Private Cloud (VPC) consists of subnets, and each subnet needs to be set up with a private IP CIDR address, where CIDR stands for Classless Inter-domain Routing. The CIDR range defines the range of internal IP addresses that virtual machines in the subnet can use.
Examples include: 10.0.0.0 /16
Subnets follow rules:-
1. Subnets need to be configured with a private IP address
2. IP addresses are used Internal network communication
3. Each octet in an IP address is represented by 8 binary bits.
4. /## will determine the number of adddress bits that are static. The number at the end of the range determines how many bits will be static or frozen.

There are two types of IP addresses: Public and Internal(Private)

1. Public
<ul>
<li>can be ephemeral or reserved.</li>
<li>Billed when not attached to a Running VM</li>
<li>VM doesn't know external IP. It is mapped to internal IPcan be ephemeral or reserved.</li>
</ul>

2. Public
<ul>
<li>Allocated from subnet range to VMs by Dynamic Host Configuration Protocol (DHCP).</li>
<li>DHCP lease is renewed every 24 hours</li>
<li>The name of the virtual machine is the hostname, and the hostname will be associated with the internal IP address through a network-scoped DNS service.</li>
</ul>

### The Google Cloud Network

A region is a specific geographical location where you can run your resources. The PoPs are where the Google network is connected to the rest of the internet. Google Cloud operates a vast worldwide network of connection points to bring its traffic closer to its partners, cutting costs and delivering a superior user experience.

They have several Networking Services:-
1. Google Cloud VPC
Using Virtual Private Cloud (VPC), you can link your Google Cloud assets within a private network, separating them for security, compliance, and distinct development, testing, and production purposes.

2. Cloud Load Balancing
Cloud Load Balancing in Google Cloud ensures steady, high-performance load balancing that scales easily to deliver consistent user experiences.

3. Cloud CDN
Cloud CDN is a network that swiftly delivers content to users, ensuring it's readily available and performs well. It works by keeping files near users. Google's global network powers Cloud CDN, offering speedy and cost-effective content delivery.

4. Cloud Interconnect
Cloud Interconnect allows you to link your infrastructure to Google's network edge using top-quality connections. Google's partner network-service providers offer these connections, which often come with better service quality compared to regular internet connections.

5. Cloud DNS
Cloud DNS is a system that changes website names into their corresponding IP addresses. Google offers the necessary infrastructure for handling large-scale DNS services, which is ideal for real-world applications.

### Routes and firewall rules

1. Routing
Similar to physical networks, VPCs have routing tables. These tables are like data lists that contain information about router locations and their IP addresses. They help routers decide the best path to specific network destinations, often based on the number of "hops" required to reach them.

The great thing about VPC routing tables in Google Cloud is that they are built-in, so you don't need to set up or manage a router yourself. These tables are used to direct traffic within the same network, across subnetworks, or even between different Google Cloud zones, all without needing an external IP address.

2. Firewall
Another convenient feature in Google Cloud is the automatic global distributed firewall provided by VPCs. This firewall allows you to control access to instances by specifying rules for both incoming and outgoing traffic

### Multiple VPC networks

VPC peering lets two VPCs connect and share traffic. It creates a private connection between two VPC networks, even if they are from different projects or organizations.

Each VPC network has its own set of firewall rules that determine what traffic is allowed between them. VPC peering is a decentralized way of networking across multiple projects because each VPC network can be managed separately. They maintain their own global firewall rules and routing tables.

### Hybrid Clouds
Many Google Cloud customers want to connect their Google Virtual Private Clouds to other networks in their system, like on-premises networks or networks in other clouds. There are several ways to do this:

1. **Internet-Based VPN:** You can establish a virtual private network (VPN) connection over the internet using the IPsec VPN protocol. To make this connection dynamic and flexible, you can use Google Cloud's Cloud Router. It allows your Google VPC and other networks to exchange route information through the VPN using the Border Gateway Protocol (BGP). 

2. **Direct Peering:** Another option is to connect with Google through Direct Peering. This involves placing a router in the same public data center as a Google point of presence (PoP) and using it to exchange traffic between networks. Carrier Peering gives you direct access from your on-premises network to Google Workspace and Google Cloud products that rely on public IP addresses. However, it's worth noting that peering doesn't come with a Google service level agreement (SLA).

3. **Dedicated Interconnect:** For the highest uptime and reliability, you can use Dedicated Interconnect. This option allows for one or more direct, private connections to Google. If these connections meet Google's specifications, they can be backed up by a VPN for even greater reliability.

4. **Partner Interconnect:** Partner Interconnect provides connectivity between an on-premises network and a VPC network through a supported service provider. It can be useful if your data center is not in close proximity to a Dedicated Interconnect colocation facility or if your data transfer needs don't require a full 10 Gbps connection. Depending on your availability requirements, Partner Interconnect can be configured to support critical services or applications, but it may have some downtime.

### Load Balancing Options 

A load balancer's job is to evenly distribute user traffic across multiple instances of an application. This distribution helps prevent performance issues in applications.

Cloud Load Balancing is a managed service that efficiently handles all your traffic. Unlike traditional load balancers running on virtual machines (VMs) that require manual scaling and management, Cloud Load Balancing is fully distributed and software-defined, meaning you don't need to worry about scaling or managing it. All these services are designed for incoming internet traffic.

Google Cloud's suite of load-balancing options includes:

1. Global HTTP(S) Load Balancing: For web applications requiring cross-regional load balancing.
2. SSL Proxy Load Balancing: Designed for SSL traffic that isn't HTTP.
3. TCP Proxy Load Balancing: Suitable for non-SSL TCP traffic on specific port numbers.
4. Regional External Load Balancing: For load balancing UDP traffic or traffic on any port number within a Google Cloud region.