# Module 3: Use Google Cloud to build your apps

This is the Third Module of the Entire Cloud Computing Foundations Course. It contains the following labs:-
1. GSP001 -- Creating a Virtual Machine
2. GSP067 -- App Engine: Qwik Start - Python
3. GSP080 -- Cloud Functions: Qwik Start - Command Line
4. GSP100 -- Kubernetes Engine: Qwik Start

## Objectives

1. Explore the role of compute options in the cloud.
2. Learn about building and managing virtual machines.
3. Examine building elastic applications using autoscaling.
4. Explore PaaS options by leveraging App Engine.
5. Examine building event-driven services using Cloud Functions.
6. Identify containerizing and orchestrating applications with Google Kubernetes Engine.
7. Identify developing and deploying scalable containerized applications with Cloud Run.

### Compute Options in the Cloud

There are a variety of Compute Services in the Google Cloud:-

1. Compute Engine (Iaas Type)

Good option for general workloads that require dedicated resources for your applications. With Compute Engine, users can create and run virtual machines in Google's innovative data centers and on its global fiber network.

It consists of thousands of VMs or Virtual Machines. Each virtual machine contains the power and functionality of a full-fledged operating system.

You can run any computing workload on Compute Engine, such as web-server hosting, application hosting, or application backends.

A special type of VM: **Preemptible VM** -- Compute Engine has permission to terminate a job if its resources are needed elsewhere.

Compute Engine has a feature called **autoscaling**, where VMs can be added to or subtracted from an application based on load metrics. The other part of making that work is balancing the incoming traffic among the VMs.

Google’s **Virtual Private Cloud (VPC)** supports several different kinds of load balancing, which we’ll explore shortly.
With Compute Engine, you can in fact configure very large VMs, which are great for workloads such
as in-memory databases and CPU-intensive analytics, but most Google Cloud customers start off with scaling out, not up.
The maximum number of CPUs per VM is tied to its “machine family” and is also constrained by the quota available to the user, which is zone-dependent.

2. Google Kubernetes Engine (Hybrid of IaaS and PaaS)

To run containers on a managed Kubernetes platform, you can leverage GKE. It offers the managed infrastructure of an IaaS, with the developer orientation of a PaaS offering.

The idea of a container is to give the independent scalability of workloads in PaaS and an abstraction layer of the OS and hardware in IaaS.

A configurable system lets you install your favorite runtime, web server, database, or middleware, configure the underlying system resources, such as disk space, disk I/O, or networking, and build as you like.

Kubernetes is a container orchestration tool you can use to simplify the management of containerized environments. It lets you install the system on local servers in the cloud, manage container networking and data storage, deploy rollouts and rollbacks, and monitor and manage container and host health.

When you run a GKE cluster, you also gain the benefit of advanced cluster management features that Google Cloud provides. These include:

1. Load balancing for Compute Engine instances
2. Node pools to designate subsets of nodes within a cluster for additional flexibility
3. Automatic scaling of your cluster's node instance count
4. Automatic upgrades for your cluster's node software
5. Node auto-repair to maintain node health and availability
6. Logging and Monitoring with Cloud Monitoring for visibility into your cluster

Kubernetes draws on the same design principles that run popular Google services and provides the same benefits: automatic management, monitoring and liveness probes for application containers, automatic scaling, rolling updates, and more. When you run your applications on a container cluster, you're using technology based on Google's 10+ years of experience with running production workloads in containers.

3. App Engine (PaaS Type)

App Engine lets you build highly scalable applications on a fully managed, serverless platform. App Engine is ideal if time-to-market is highly valuable to you and you want to focus on writing code without ever having to touch a server, cluster, or infrastructure. App Engine allows you to have high availability apps without a complex architecture.

With App Engine, you can choose from popular coding languages like Eclipse, IntelliJ, Maven, Git, Jenkins, and PyCharm, libraries, and frameworks to develop apps. That means that you can upload your code, and Google will manage your app's availability.

App Engine also provides built-in services and APIs, like NoSQL datastores, Memcache, load balancing, health checks, application logging, and a user authentication API that is common to most applications.

App Engine offers **software development kits, or SDKs**, to help you develop, deploy, and manage your apps on your local machine. The SDK manages your application locally, and the Google Cloud console manages your application in production.

Each SDK includes: 
1. All of the APIs and libraries available to App Engine
2. A simulated, secure sandbox environment that emulates all of the App Engine services on your local computer
3. Deployment tools to upload your application to the cloud and manage different versions.

There are two types of App Engine environments: **standard** and **flexible**.

Standard:- 
<ul>
<li>Instance startup in seconds</li>
<li>No SSH access</li>
<li>Doesn't write to local disk</li>
<li>Supports Third party Binaries for certain languages</li>
<li>Network access through App Engine service</li>
<li>Pay per instance class with automatic Shutdown</li>
</ul>

Flexible:-
<ul>
<li>Instance startup in Minutes</li>
<li>SSH access</li>
<li>Does write to local disk (ephemeral)</li>
<li>Supports Third party Binaries for all</li>
<li>Network access is present</li>
<li>Pay per resource allocation per hour with no automatic Shutdown</li>
</ul>

4. Cloud Functions (Serverless)

Cloud Functions offers a serverless option for triggering code to run based on some kind of event. Cloud Functions is serverless code that lets you run it based on certain events. With Cloud Functions, you could write a single-purpose function that completes the necessary image manipulations, and then arrange for it to automatically run whenever a new image is uploaded.

Cloud Functions is a lightweight, event-based, asynchronous compute solution that allows you to create small, single-purpose functions that respond to cloud events without needing to manage a server or a runtime environment.

5. Cloud Run (Serverless)

Cloud Run is a fully managed serverless platform that lets you develop and deploy highly scalable containerized applications.
It is a managed compute platform that lets you run stateless containers by using web requests or Pub/Sub events.

It’s built on Knative, an open API and runtime environment built on Kubernetes that gives you freedom to move your workloads across different environments and platforms.

Cloud Run is fast.
It can automatically scale up from zero and back down almost instantaneously, and it charges you only for the resources you use, calculated down to the nearest 100 milliseconds, so you‘ll never pay for your over-provisioned resources.

Cloud Run is unique; you only pay for the system resources you use while a container is handling web requests, with a granularity of 100ms, and when it is starting or shutting down.


### Resources are Hierarchical

Resource hierarchy is made up of four levels, and starting from the bottom up they are: **resources**, **projects**, **folders**, and an **organization node**.

1. Resource -- These represent virtual machines, Cloud Storage buckets, tables in BigQuery, or anything else in Google Cloud. Resources are organized into projects, which sit on the second level.

2. Projects -- These sit on the second level. Projects are the basis for enabling and using Google Cloud services, like managing APIs, enabling billing, adding and removing collaborators, and enabling other Google services. Projects can be organized into folders, or even subfolders.

Each project is a separate compartment, and each resource belongs to exactly one project. Projects can have different owners and users, because they’re billed and managed separately. Each Google Cloud project has three identifying attributes: a project ID, a project name, and a project number.

The project ID is a globally unique identifier assigned by Google that cannot be changed–it is immutable–after creation. Project IDs are used in different contexts to inform Google Cloud of the exact project to work with. The project names, however, are user-created. They don’t have to be unique and they can be changed at any time, so they are not immutable. Google Cloud also assigns each project a unique project number.

To **manage** projects, Google Cloud has the Resource Manager tool, designed to programmatically help you do just that. It’s an API that can gather a list of all the projects associated with an account, create new projects, update existing projects, and delete projects. It can even recover projects that were previously deleted and can be accessed through the RPC API and the REST API.

3. Folder -- These sit at the third level. You can use folders to group projects under an organization in a hierarchy. Folders let you group these resources on a per-department basis. Folders give teams the ability to delegate administrative rights so that they can work independently.

4. Organization Node -- The top level is an organization node, which encompasses all the projects, folders, and resources in your organization. To use folders, you must have an organization node, which is the topmost resource in the Google Cloud hierarchy. Everything else attached to that account goes under this node, which includes projects, folders, and other resources.

#### Billing

Billing is established at the project level. This means that when you define a Google Cloud project, you link a billing account to it. This billing account is where you will configure all your billing information, including your payment option. A billing account can be linked to zero or more projects, but projects that aren’t linked to a billing account can only use free Google Cloud services.

Billing accounts are charged automatically and invoiced every month or at every threshold limit.

