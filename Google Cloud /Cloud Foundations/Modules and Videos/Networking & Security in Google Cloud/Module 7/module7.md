# Module 7: It helps to network

This is the Seventh Module of the Entire Cloud Computing Foundations Course. 

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

A Virtual Private Cloud, or VPC, is a secure, individual, private cloud-computing model hosted within a public cloud (like Google Cloud!). Within a Virtual Private Cloud (VPC), clients have the capability to execute code, store data, host websites, and perform all the tasks they would typically carry out in a traditional private cloud. However, the key distinction is that this private cloud is situated on remote servers managed by a public cloud provider. Essentially, VPCs merge the scalability and ease of use found in public cloud computing with the data protection and segregation associated with private cloud computing.

