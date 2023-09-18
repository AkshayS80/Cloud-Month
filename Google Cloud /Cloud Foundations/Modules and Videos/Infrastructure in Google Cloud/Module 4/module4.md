# Module 4: Where do I store this stuff?

This is the Fourth Module of the Entire Cloud Computing Foundations Course.It contains the following labs:-
1. GSP074 -- Cloud Storage: Qwik Start - CLI/SDK
2. GSP151 -- Cloud SQL for MySQL: Qwik Start

## Objectives

1. Explore the different storage options available in Google Cloud.
2. Learn to differentiate between structured and unstructured storage in the cloud.
3. Examine how you can use Cloud Storage for unstructured data storage.
4. Explore the use case for relational versus NoSQL storage options and identify the options available with Google Cloud.

### Storage Options in the cloud

Every application needs to store data, like media to be streamed or perhaps even sensor data from devices, and different applications and workloads require different storage database solutions. There are three types of ways that google cloud can store data:-

1. Relational 
2. Non relational Databases
3. World wide Object storage

Google Cloud provides managed storage and database services that are scalable, reliable, and easy to operate. These include:-
1. Cloud Storage 
2. Cloud SQL 
3. Cloud Spanner
4. Firestore
5. Cloud Bigtable

There are three common cloud storage use cases:-
1. The first is content storage and delivery.
2. The second use case is storage for data analytics and general compute.
3. The third use case is backup and archival storage.

### Structured and Unstructured data Storage 

1. Unstructured Data Storage

Unstructured data is information stored in a non-tabular form such as documents, images, and audio files. Unstructured data is usually best suited to Cloud Storage. It’s estimated that around 80 percent of all data is unstructured. It’s far more difficult to process or analyze unstructured data using traditional methods because the data has no internal identifier to enable search functions to identify it. Unstructured data often includes text and multimedia content, for example, email messages, documents, photos, videos, presentations, and web pages.

2. Structured Data Storage 

There is structured data, which represents information stored in tables, rows, and columns. Structured data is what most people are used to working with and typically fits within columns and rows in spreadsheets or relational databases. You can expect this type of data to be organized and clearly defined and usually easy to capture, access, and analyze. Examples of structured data include names, addresses, contact numbers, dates, and billing info.

It comes in two types-- Transactional and Analytical Workload
Transactional workloads stem from Online Transaction Processing systems, which are used when fast data inserts and updates are required to build row-based records whereas Analytical workloads, which stem from Online Analytical Processing systems, which are used when entire datasets need to be read.

Transactional requires relatively standardized queries that affect only a few records while Analytical often require complex queries, for example, aggregations.

### Cloud Storage and Object Storage

Cloud Storage is a fully managed scalable service that has a wide variety of uses. Cloud Storage’s primary use is whenever binary large-object storage (also known as a “BLOB”) is needed for online content such as videos and photos, for backup and archived data, and for storage of intermediate results in processing workflows.

Object storage is a computer data storage architecture that manages data as “objects” and not as a file and folder hierarchy (file storage), or as chunks of a disk (block storage). These objects are stored in a packaged format that contains the binary form of the actual data
itself, relevant associated metadata (such as date created, author, resource type, and permissions), and a globally unique identifier.

### Types of File Storage 

1. File Storage 
2. Block Storage 
3. Object Storage

### Cloud Storage Classes 

1. Standard Storage for Hot data (data that is stored for brief periods of time)
2. Nearline Storage for data that is read or modified once a month
3. Coldline Storage for data that is read or modified once every 90 days 
4. Archive Storage for data that is read or modified once every year

All of them have common features:
1. Unlimited Storage 
2. Worldwide accessibility and locations
3. Low Latency and High Durability
4. A uniform experience
5. Geo Redundancy

Cloud Storage files are organized into buckets. A bucket needs a globally unique name and a specific geographic location for where it should be stored, and an ideal location for a bucket is where latency is minimized.
The storage objects offered by Cloud Storage are “immutable,” which means that you do not edit them, but instead a new version is created with every change made. 

It also allows Object reversioning which allows us to revert a file to its older version of that file

Administrators can either allow each new version to completely overwrite the older one or keep track of each change made to a particular object by enabling “versioning” within a bucket.If you choose to use versioning, Cloud Storage will keep a detailed history of modifications (overwrites or deletes) of all objects contained in that bucket.

### SQL managed services

A database is a collection of information that is organized so that it can easily be accessed and managed. Computer applications run databases to get a fast answer to questions like: What’s this user’s name, given their sign-in information, so I can display it?

**Relational database management systems**, abbreviated RDBMS are used extensively and are the kind of database you encounter most of the time.
They’re organized based on the relational model of data.
They are very good when you have a well-structured data model and when you need transactions and the ability to join data across tables to retrieve complex combinations of your data. Because they make use of the Structured Query Language, they are sometimes called SQL databases.

Google Cloud offers two managed relational database services, **Cloud SQL** and **Cloud Spanner**.

1. Cloud SQL
Cloud SQL offers fully managed relational databases, including MySQL, PostgreSQL, and SQL Server as a service. It’s designed to hand off mundane, but necessary and often time-consuming, tasks to Google—like applying patches and updates, managing backups, and configuring replications—so your focus can be on building great applications.

Cloud SQL doesn't require any software installation or maintenance and supports automatic replication scenarios, such as from a Cloud SQL primary instance, an external primary instance, and external MySQL instances.

2. Cloud Spanner 

Cloud Spanner is a fully managed relational database service that scales horizontally, is strongly consistent, and speaks SQL.

Vertical scaling is where you make a single instance larger or smaller, while horizontal scaling is when you scale by adding and removing servers.

Cloud Spanner is especially suited for applications that require: 
1. An SQL relational database management system with joins and secondary indexes 
2. Built-in high availability 
3. Strong global consistency 
4. And high numbers of input/output operations per second, such as tens of thousands of reads/writes per second.

Data is automatically and instantly copied across regions, which is called synchronous replication. As a result, queries always return consistent and ordered answers regardless of the region. Google uses replication within and across regions to achieve availability, so if one region goes offline, a user’s data can still be served from another region.


### NoSQL managed services

Google offers two managed NoSQL database options, **Firestore** and **Cloud Bigtable**.

1. Firestore:

Firestore is a flexible, horizontally scalable, NoSQL cloud database for mobile, web, and server development. With Firestore, incoming data is stored in a document structure, and these documents are then organized into collections. Firestore’s NoSQL queries can then be used to retrieve individual, specific documents or to retrieve all the documents in a collection that match your query parameters. Firestore uses data synchronization to update data on any connected device.
However, it's also designed to make simple, one-time fetch queries efficiently. It caches data that an app is actively using, so the app can write, read, listen to, and query data even if the device is offline. Firestore leverages Google Cloud’s powerful infrastructure: automatic multi-region data replication, strong consistency guarantees, atomic batch operations, and real transaction support.

2. Cloud Bigtable

Bigtable is Google's NoSQL big data database service.It's the same database that powers many core Google services, including Search, Analytics, Maps, and Gmail. Bigtable is designed to handle massive workloads at consistent low latency and high throughput, so it's a great choice for both operational and analytical applications, including Internet of Things, user analytics, and financial data analysis. Bigtable can interact with other Google Cloud services and third-party clients.
