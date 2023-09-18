# Module 2: Start with a platform

This is the Second Module of the Entire Cloud Computing Foundations Course. It includes labs labelled 
1. GSP282- A Tour of Google Cloud Hands-on Labs
2. GSP002- Getting Started with Cloud Shell and gcloud

## Objectives

1. Explore the Google Cloud console.
2. Examine how projects are the basis for enabling and using Google Cloud services.
3. Identify how billing works in Google Cloud.
4. Install and configure the Cloud SDK.
5. Recognize the different use cases for using Cloud Shell and the Cloud Shell code editor.
6. Explore how APIs work.
7. Manage Google Cloud services from a mobile device.


### Interaction with Google Cloud

There are 4 ways to interact with Google Cloud

1. Google Cloud Console

The **Google Cloud console**, which is Google Cloud’s Graphical User Interface (GUI), helps you deploy, scale, and diagnose production issues in a simple web-based interface. With the console, you can easily find your resources, check their health, have full management control over them, and set budgets to control how much you spend on them. The console also provides a search facility to quickly find resources and connect to instances through SSH, which is the Secure Shell Protocol, in the browser.

2. Cloud SDK and Cloud Shell

The **Cloud SDK** (Cloud Software Development Kit) is a set of command-line tools that you can use to manage resources and applications hosted on Google Cloud. These include: the gcloud CLI, which provides the main command-line interface for Google Cloud products and services, **gsutil**. (g-s-util), which lets you access Cloud Storage from the command line, and **bq**, a command-line tool for BigQuery.

**Cloud Shell** provides command-line access to cloud resources directly from a browser. It’s a Debian-based virtual machine with a persistent 5-GB home directory, which makes it easy to manage Google Cloud projects and resources. With Cloud Shell, the Cloud SDK gcloud command and other utilities are always installed, available, up to date, and fully authenticated. This tool is convenient for working with code-first applications or container-based workloads, because you can easily edit files without needing to download and upload changes.

3. APIs

Application developers structure the software they write in a clean, well-defined interface that abstracts away needless detail, and then they document that interface. That’s an **Application Programming Interface**. The underlying implementation can change as long as the interface doesn’t, and other pieces of software that use the API don’t have to know or care. The Google Cloud console includes a tool called the **Google APIs Explorer** that shows what APIs are available, and in what versions.

Google provides **Cloud Client** and **Google API Client** Libraries in many popular languages to take much of the drudgery out of the task of calling Google Cloud from your code. Languages currently represented in these libraries are: Java, Python, PHP, C#, Go, Node.js, Ruby and C++

4. Cloud Mobile App

The Cloud Mobile App provides a way for you to manage services running on Google Cloud directly from your mobile device. It’s a convenient resource that comes at no extra cost. The Cloud Mobile App can be used to start, stop, and use ssh to connect to Compute Engine instances and to see logs from each instance.

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

