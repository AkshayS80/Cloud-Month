# Module 1: So What's the Cloud Anyways?

This is the First Module of the Entire Cloud Computing Foundations Course

## Objectives

1. Explore cloud computing.
2. Compare and contrast physical, virtual, and cloud architectures.
3. Differentiate infrastructure as a service (IaaS), platform as a service (PaaS), and software as a service (SaaS).
4. Be introduced to Google Cloud compute, storage, big data, and ML services.
5. Examine the Google network and how it powers cloud computing.

### Cloud Computing

By defintion,Cloud computing is the on-demand availability of computing resources (such as storage and infrastructure), as services over the internet. It eliminates the need for individuals and businesses to self-manage physical resources themselves, and only pay for what they use.

It is the type of usage of IT that are defined by the traits:
1. Customers get on demand self-service computing resources
2. Customers get access to resources from wherever
3. Providers have these resources ready to send(in pools) and allocates them to users out of those pools
4. Resources increase and decrease as needed
5. Customers only pay for what they use or reserve.

#### History

1. Colocation
The trend towards cloud computing commenced with an initial phase referred to as colocation. Colocation provided users with the cost-effective option of leasing physical infrastructure space, as opposed to making substantial investments in data center properties.

2. Virtualized Data Centers

Virtualized data centers of today, which is the second wave, share similarities with the private data centers and colocation facilities of decades past.The components of virtualized data centers match the physical building blocks of hosted computing—servers, CPUs, disks, load balancers, and so on—but now they’re virtual devices.With virtualization, enterprises still maintained the infrastructure; it’s still a user-controlled and user-configured environment.

3. Container Based Architecture

It is a fully automated, elastic third-wave cloud that consists of a combination of automated services and scalable data. Services automatically provision and configure the infrastructure used to run applications.

#### IaaS, PaaS, SaaS and Serverless

1. Infrastructure as a Service(IaaS)

IaaS offerings provide raw compute, storage, and network capabilities, organized virtually into resources that are similar to physical data centers. Customers pay for the resources they allocate ahead of time

2. Platform as a Service(PaaS)

PaaS offerings bind code to libraries that provide access to the infrastructure applications need. Customers pay for the resources they actually use

3. Software as a Service(SaaS)

SaaS applications are not installed on your local computer; they run in the cloud as a service and are consumed directly over the internet by end users. Google's popular applications like Gmail, Docs, and Drive, collectively known as Google Workspace, are all classified as SaaS.

4. Serverless

Serverless computing allows developers to concentrate on their code, rather than on server configuration, by eliminating the need for any infrastructure management. Serverless technologies offered by Google include Cloud Functions, which manages event-driven code as a pay-as-you-go service

#### Google Cloud Infrastructure

There are three layers in the Infrastructure:-

1. At the base layer is **networking and security**, which lays the foundation to support all of Google’s infrastructure and applications.

2. On the next layer sit **compute** and **storage**, decoupled so they can scale independently based on need.

3. On the top layer sit the **big data** and **machine learning** products, which enable you to perform tasks to ingest, store, process, and deliver business insights, data pipelines, and machine learning models.

#### Google Cloud Computing Services

##### Computing Services
1. Compute Engine
2. Google Kubernetes Engine
3. App Engine
4. Cloud Functions
5. Cloud Run

##### Storage Services
1. Cloud Storage
2. Cloud SQL -- Relational Database
3. Cloud Spanner -- Relational Database
4. Cloud Bigtable -- NoSQL Database
5. Firestore -- NoSQL Database

##### Regions and Zones

Google Cloud’s infrastructure is based in five major geographic locations: North America, South America, Europe, Asia, and Australia.
Having multiple service locations is important because choosing where to locate applications affects qualities like availability, durability, and latency, which measures the time a packet of information takes to travel from its source to its destination.
Each of these locations is divided into several different regions and zones.

**Regions** represent independent geographic areas, and are composed of zones.

A **zone** is an area where Google Cloud resources are deployed. Zonal resources operate within a single zone, which means that if a zone becomes unavailable, the resources won’t be available either.