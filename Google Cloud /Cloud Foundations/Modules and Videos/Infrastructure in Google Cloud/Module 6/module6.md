# Module 6: You can’t secure the cloud, right?

This is the Sixth Module of the Entire Cloud Computing Foundations Course. It contains the following labs:-
1. GSP064 -- Cloud IAM: Qwik Start
2. GSP499 -- User Authentication: Identity-Aware Proxy

## Objectives

1. Outline how security is administered in Google Cloud, including the shared security model.
2. Explore the different encryption options with Google Cloud.
3. Identify best practices when you configure authentication and authorization with Identity and Access Management (IAM).

### Infrastructure Security Design

Design for security is prevalent, throughout the infrastructure, that Google Cloud and Google services run-on.
There are 5 levels:

1. Operational security

It contains these features:- 
<ul>
<li>Intrusion detection: Rules and machine intelligence give Google’s operational security teams warnings of possible incidents.</li>
<li>Reducing insider risk: Google aggressively limits and actively monitors the activities of employees who have been granted administrative access to the infrastructure.</li>
<li>Employee U2F(Universal Second Factor) use: To guard against phishing attacks against Google employees, employee accounts require use of U2F-compatible security keys.</li>
<li>Software development practices: Google employs central source control and requires two-party review of new code.</li>
</ul>

2. Internet communication

It contains these features:- 
<ul>
<li>Google Front End (GFE): Google services that want to make themselves available on the internet register themselves with an infrastructure service called the Google Front End, which ensures that all TLS connections are ended using a public-private key pair and an X.509  certificate from a Certified Authority (CA), and follows best practices such as supporting perfect forward secrecy.</li>
<li>Denial of Service (DoS) protection: The sheer scale of its infrastructure enables Google to simply absorb many DoS attacks.</li>
</ul>

3. Storage Services

Encryption at rest: Most applications at Google access physical storage (in other words, “file storage”) indirectly by using storage services, and encryption (using centrally managed keys) is applied at the layer of these storage services.  


4. Service Deployment

It contains these features:- 
<ul>
<li>Encryption of inter-service communication: Google’s infrastructure provides cryptographic privacy and integrity for remote procedure call (“RPC”) data on the network.</li>
<li>User identity: Google’s central identity service, which usually manifests to end users as the Google login page, goes beyond asking for a simple username and password.</li>
<li>Premises security: Google designs and builds its own data centers, which incorporate multiple layers of physical security protections. </li>
</ul>


5. Hardware Infrastructure

It contains these features:-
<ul>
<li>Hardware design and provenance: Google custom designs both the server boards and networking equipment within its data centers. Additionally, Google is responsible for crafting specialized chips, including a hardware security chip that is presently being implemented in both server components and peripheral devices.</li>
<li>Secure boot stack: Google server machines use various technologies to ensure that they are booting the correct software stack, such as cryptographic signatures over the BIOS, bootloader, kernel, and base operating system image.</li>
<li>Premises security: Google designs and builds its own data centers, which incorporate multiple layers of physical security protections. </li>
</ul>
Access to these data centers is limited to only a small fraction of Google employees.
Google also hosts some servers in third-party data centers, where we ensure that there are Google-controlled physical security measures on top of the security layers provided by the data center operator.

### The Shared Security Model

Security responsibilities are divided between the **customer** and **Google Cloud**. When a customer installs an application on their own on-premises infrastructure, they bear the responsibility for safeguarding the entire system. This encompasses everything from the physical security of the hardware and the facility housing it to the encryption of data stored on disks, ensuring network integrity, and securing the content within those applications. However, when they migrate an application to Google Cloud, Google assumes the responsibility for many of the foundational security aspects, including physical security, disk encryption, and network integrity.

### Encryption Options

Several encryption options are available on Google Cloud.

These range from simple but with limited control, to greater control flexibility but with more complexity.

The simplest option is **Google Cloud default encryption**, followed by **customer-managed encryption keys** (CMEK), and the option that provides the most control: **customer-supplied encryption keys** (CSEK). **Client-side Encryption** enables you to encrypt your data locally before you store it in the cloud.
<ul>
<li>Customer Managed Encryption Keys: With customer-managed encryption keys, you manage your encryption keys that protect data on Google Cloud. Cloud Key Management Service, or Cloud KMS, automates and simplifies the generation and management of encryption keys.The keys are managed by the customer and never leave the cloud. Cloud KMS supports encryption, decryption, signing, and verification of data.</li>
<li>Customer-supplied encryption keys: It gives user more control over their keys, but with greater management complexity. With CSEK, users use their own AES 256-bit encryption keys. They are responsible for generating these keys.

Persistent disks, such as those that back virtual machines, can be encrypted with customer-supplied encryption keys. When a persistent disk is deleted, the keys are discarded, and the data is rendered irrecoverable by traditional means. To have more control over persistent disk encryption, users can create their own persistent disks and redundantly encrypt them.</li>
<li>Client-Side Encryption: With client-side encryption, users encrypt data before they send it to Google Cloud. Neither the unencrypted data nor the decryption keys leave their local device</li>
</ul>

### Authentication and authorization with IAM

Using IAM (Identity and Access Management), administrators have the capability to establish rules that specify who is authorized to perform specific actions on particular resources. The "who" aspect in an IAM policy can encompass a Google Account, a Google group, a service account, or a Cloud Identity domain. Meanwhile, the "can do what" aspect of an IAM policy is determined by a role. In essence, an IAM role serves as a bundle of permissions.

These permissions are grouped together into a role for the purpose of simplifying comprehension and management. When a user, group, or service account is assigned a role for a specific level within the resource hierarchy, the resulting policy is applicable to the designated level and all subordinate levels beneath it in the hierarchy.

**Cloud Identity**

Using a tool known as Cloud Identity, organisations have the capability to establish rules and oversee their users and groups through the Google Admin console. Administrators can access and oversee Google Cloud assets using the same login credentials they currently employ in their pre-existing Active Directory or LDAP systems. Cloud Identity also empowers administrators to deactivate a user's account and remove them from groups within the organization when they depart, all through the Google Admin console.

There are three kinds of roles in IAM: basic, predefined, and custom.

1. Basic 
Basic roles are broad in scope. Basic roles include owner, editor, viewer, and billing administrator. Project viewers can examine resources, but can’t modify them. Project editors can examine and modify a resource and project owners can also examine and modify a resource. In addition, project owners can manage the associate roles and permissions, and set up billing.

2. Predefined 
Specific Google Cloud services offer sets of predefined roles, and they even define where those roles can be applied.For example, In Compute Engine, you can apply specific predefined roles—such as “instanceAdmin”—to Compute Engine resources in a given project, a given folder, or an entire organization. This then allows whoever has these roles to perform a specific set of predefined actions.

3. Custom

First, you must manage the permissions that comprise the custom role you’ve created. Because of this, some companies decide to stick with the predefined roles and second, custom roles can only be applied to either project or organization level. They can’t be applied to the folder level. 

A **service account** is a special kind of account typically used by an application or compute workload, such as a Compute Engine instance, rather than a person. A service account is identified by its email address, which is unique to the account.

### IAM authorization best practices 

1. Use temporary credentials
2. Require multi-factor authentication (MFA)
3. Rotate access keys regularly for use cases that require long-term credentials
4. Safeguard your root user credentials and don't use them for everyday tasks
5. Grant least privilege
6. Use IAM Access Analyzer
7. Set permissions guardrails across multiple accounts
8. Delegate permissions management within an account by using permissions boundaries
9. Grant roles to groups instead of individuals