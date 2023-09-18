# Module 7: Describe Azure identity, access, and security

This is the Seventh Module of the Azure Fundementals Challenge

## Objectives

1. Describe directory services in Azure, including Azure Active Directory (AD) and Azure AD DS
2. Describe authentication methods in Azure, including single sign-on (SSO), multifactor authentication (MFA), and passwordless
3. Describe external identities and guest access in Azure
4. Describe Azure AD Conditional Access
5. Describe Azure Role Based Access Control (RBAC)
6. Describe the concept of Zero Trust
7. Describe the purpose of the defense in depth model
8. Describe the purpose of Microsoft Defender for Cloud

### Azure Active Directory

Azure Active Directory (Azure AD) is a directory service that enables you to sign in and access both Microsoft cloud applications and cloud applications that you develop. Azure AD can also help you maintain your on-premises Active Directory deployment. Azure AD is Microsoft's cloud-based identity service. 
Azure AD helps secure identities by detecting suspicious sign-ins.

##### Features

Azure AD provides services for:

- Authentication: Verify identity, self-service password reset, multifactor authentication, etc.
- Single sign-on (SSO): One username/password for multiple apps, easier access management.
- Application management: Manage cloud/on-premises apps, Application Proxy, SaaS apps, My Apps portal.
- Device management: Register devices for management with tools like Microsoft Intune, enforce device-based access policies.

### Azure Active Directory Domain Services

Azure Active Directory Domain Services (Azure AD DS) is like having domain services (e.g., LDAP, group policy, authentication) in the cloud without the hassle of managing domain controllers. It's especially useful for running legacy apps in the cloud or avoiding the need to rely on on-premises AD DS. Azure AD DS works seamlessly with your Azure AD setup, allowing users to sign in and use resources with existing credentials and groups, simplifying the migration of on-premises resources to Azure.

### Azure Authentication Methods

Authentication is like showing your ID to prove your identity, whether it's a person, a service, or a device. Azure offers various ways to prove who you are, like using passwords, single sign-on, multi-factor authentication, or even going passwordless. It's like different ways to confirm your identity when you travel. 

##### Single Sign-On

Single sign-on (SSO) is like having one key to open many doors. You log in once, and that key works for multiple apps from different providers. This saves you from remembering and changing lots of passwords, reducing the risk of security issues. With SSO, you need to remember only one ID and one password. Access across applications is granted to a single identity that's tied to the user, which simplifies the security model.

- Note: Single sign-on is only as secure as the initial authenticator because the subsequent connections are all based on the security of the initial authenticator.

##### Multi Factor Authentication

Multifactor authentication (MFA) is like using multiple locks to secure your home. Instead of just one key (password), you need at least two keys (factors) to unlock your accounts. These factors could be something you know (like a question), something you have (like a phone code), or something you are (like a fingerprint). MFA makes it harder for attackers because even if they know your password, they'd still need your other "keys" to get in. This makes your accounts much safer compared to using just a password.

For this, Microsoft provides Azure AD Multi-Factor Authentication which lets you choose another way to prove your identity when you sign in, like getting a phone call or a notification on your phone. This makes it much harder for anyone to break into your account, even if they know your password.

##### Passwordless Authentication

Passwordless authentication makes it easier and more secure to sign in because you don't need to remember a password. Instead, it relies on something you have (like your computer or phone), something you are (like your fingerprint), or something you know (like a PIN). 

Here are three options for passwordless authentication in Azure AD:
1. Windows Hello for Business

Windows Hello for Business is great for employees who use their own Windows PC. It links biometric (like fingerprints) and PIN credentials to their PC, keeping their data safe. It also works well with single sign-on (SSO) and connects easily to company resources both on-site and in the cloud.

2. Microsoft Authenticator app

The Authenticator App makes your iOS or Android phone a secure way to log in without passwords. You get a notification, match numbers on your phone and the screen, and use your fingerprint, face, or a PIN to confirm.

3. FIDO2 security keys

The FIDO Alliance promotes secure ways to log in without passwords. FIDO2 is the latest standard, and FIDO2 security keys are a type of passwordless authentication. They can look like USB devices, and when you use them, there's no password to guess or steal, making your account more secure.

### Azure external identities

Azure AD External Identities is a way to securely interact with people, devices, and services outside your organization. You can collaborate with partners or create apps for consumers. External users can use their own credentials, like Google or Facebook, to sign in, while you manage access to your apps with Azure AD.

Azure AD External Identities offers several features for collaborating with external users and organizations:
1. Business to Business (B2B) Collaboration: Collaborate with external users by allowing them to use their preferred identity to sign in to your Microsoft and other enterprise applications. These users are represented in your directory as guest users.

2. B2B Direct Connect: Establish a two-way trust with another Azure AD organization for seamless collaboration. B2B direct connect currently supports Teams shared channels, allowing external users to access your resources within Teams. These users are not represented in your directory but can be monitored in Teams admin center reports.

3. Azure AD Business to Customer (B2C): Publish modern SaaS apps or custom-developed apps to consumers and customers while using Azure AD B2C for identity and access management.

Depending on your collaboration needs and the types of resources you want to share, you can use a combination of these capabilities.

### Azure Conditional Access

Conditional Access is a tool that Azure Active Directory uses to allow (or deny) access to resources based on identity signals. These signals include who the user is, where the user is, and what device the user is requesting access from.

Conditional Access offers a more detailed approach to multifactor authentication. It considers various factors like a user's location and sign-in behavior. For instance, if a user is signing in from a known location, they may not need a second authentication factor. However, if their sign-in seems unusual or they're in an unexpected location, they may be asked for a second authentication factor.

Conditional Access provides a way to customize the security of user sign-ins based on specific conditions. These conditions can include factors like the user's location, their device, or the application they're trying to access.

Conditional Access works by gathering signals during sign-in, making decisions based on these signals, and then taking action to enforce those decisions. The signals can be things like the user's location, device, or the target application.

### Azure role-based access control

Azure offers predefined roles with common access rules for cloud resources, and you can even create your own roles. Each role comes with a set of specific access permissions.

When you assign individuals or groups to these roles, they automatically inherit all associated access permissions. For instance, if you add a new engineer to the Azure RBAC group for engineers, they will instantly have the same access as the other engineers in that group. If you add new resources and apply Azure RBAC to them, everyone in the RBAC group will also gain those permissions for the new resources, simplifying access management and ensuring security.

Role-based access control (RBAC) in Azure lets you manage who has access to your cloud resources and what they can do with them. It's applied to a specific scope, which could be a resource, a group of resources, a subscription, or even a management group (which is a collection of subscriptions).

RBAC in Azure follows a hierarchy:
- Permissions granted at a parent scope are inherited by child scopes. For example, if you assign an "Owner" role at the management group level, that user can manage everything within all subscriptions in that group.
- If you assign "Reader" at the subscription level, group members can view all resource groups and resources in that subscription.

RBAC is enforced whenever someone initiates an action on an Azure resource through Azure Resource Manager, which helps organize and secure your resources. Keep in mind that RBAC doesn't control access at the application or data level; it's for managing Azure resources specifically. RBAC follows an "allow" model. If you're assigned multiple roles with different permissions on the same resource or scope, you'll have the combined permissions of those roles.

### Zero Trust Model

Zero Trust is a modern security approach that starts with the assumption that any resource or user could be compromised, and it verifies every request to access resources as if it's coming from an untrusted network. This model is crucial in today's complex and mobile work environment.

Here are the key principles of Zero Trust:

1. Verify explicitly: Always confirm the identity and authorization of users and devices using all available information.
2. Use least privilege access: Limit user access to the minimum necessary, using Just-In-Time and Just-Enough-Access, adaptive policies based on risk, and data protection measures.
3. Assume breach: Plan for the worst-case scenario by minimizing the potential impact of breaches, segmenting access, encrypting data, and using analytics to detect and respond to threats effectively.

### Defense in-depth

Defense-in-depth is a strategy to protect sensitive information from unauthorized access. It involves using multiple layers of protection, each acting as a barrier against attacks. If one layer is breached, the next layer is there to stop further access. This approach doesn't rely on a single defense, making it harder for attackers.

##### Layers
Here are the layers:

- Physical security: Protects hardware in datacenters.
- Identity and access: Controls who can access infrastructure and make changes.
- Perimeter: Filters out large-scale attacks like DDoS before they disrupt services.
- Network: Controls communication between resources through segmentation and access rules.
- Compute: Secures access to virtual machines.
- Application: Ensures apps are free of vulnerabilities.
- Data: Controls access to sensitive business and customer data.

Each layer adds protection and alerts security teams for rapid response.

### Microsoft Defender for Cloud

Defender for Cloud is a security tool that keeps an eye on your various environments, whether they're in the cloud, on your premises, or a mix of both. Its job is to give you advice and alerts to improve your security.
It helps you secure your resources, keep an eye on your security status, defend against cyber threats, and make managing security easier.

It's already integrated with Azure, so many Azure services are automatically monitored and protected. However, if you have on-premises or other cloud environments, you might not see the full security picture. In such cases, Defender for Cloud can deploy a Log Analytics agent to collect security data. For Azure machines, it's straightforward. For non-Azure machines in hybrid or multi-cloud setups, Azure Arc helps extend protection without additional agents.

It provides:
1. Azure-native protections
2. Defend your hybrid resources
3. Defend resources running on other clouds

##### Access-Secure-Defend

Defender for Cloud serves three important purposes in managing resource and workload security:

1. Continuous Assessment: It helps you understand your security status, find vulnerabilities, and keep track of them over time. Defender for Cloud offers continuous assessment by providing vulnerability assessment solutions for your virtual machines, container registries, and SQL servers. It integrates with Microsoft Defender for Endpoint to give you access to vulnerability findings. With regular scans, it covers your compute, data, and infrastructure, allowing you to review and respond to the results within Defender for Cloud.

2. Secure: It strengthens your resources and services by following Azure Security Benchmark standards. Security in the cloud is crucial, covering everything from authentication to access control to the Zero Trust concept. To ensure the security of your cloud workloads, you must establish tailored security policies. Defender for Cloud offers powerful policy capabilities built on Azure Policy controls, providing flexibility to apply policies at different levels, from management groups to the entire tenant.

Defender for Cloud organizes these recommendations into security controls and assigns a secure score to each control, giving you a quick overview of your security posture. This score helps you understand and enhance your overall security, making it a valuable tool for maintaining a secure cloud environment.

3. Defend: It identifies and addresses threats to your resources, workloads, and services to enhance overall security. Defender for Cloud offers robust defense capabilities, including security alerts and advanced threat protection.

**Security alerts** are generated when Defender for Cloud detects a threat in your environment. These alerts provide details about the affected resources, offer remediation steps, and even allow you to trigger a logic app in response. Whether generated by Defender for Cloud or received from integrated security products, these alerts can be exported. Defender for Cloud's threat protection includes fusion kill-chain analysis, which links alerts based on cyber kill-chain analysis to give you a comprehensive view of an attack campaign.

**Advanced threat protection** extends to various resources like virtual machines, SQL databases, containers, web applications, and networks. This protection includes measures like securing VM management ports with just-in-time access and adaptive application controls, allowing you to define which apps should run on your machines. These features bolster your security posture and help defend against advanced threats.