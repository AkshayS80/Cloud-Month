# Module 6: Describe Azure storage services

This is the sixth Module of the Azure Fundementals Challenge

## Objectives

1. Compare Azure storage services
2. Describe storage tiers
3. Describe redundancy options
4. Describe storage account options and storage types
5. Identify options for moving files, including AzCopy, Azure Storage Explorer, and Azure File Sync
6. Describe migration options, including Azure Migrate and Azure Data Box

### Azure Storage Accounts

A storage account is like a special container for your data in Azure Storage. It's like having your own space on the internet where you can store and access your files from anywhere. This data is kept secure, always available, extremely reliable, and can handle a massive amount of data.

When you create a storage account, you choose what type of account it is. This choice affects the storage features and options you can use. There are different ways to store your data. Some of the options include making sure your data is stored in multiple places, in different regions, or with extra read access.

Here's a list of those options:
1. Locally redundant storage (LRS)
2. Geo-redundant storage (GRS)
3. Read-access geo-redundant storage (RA-GRS)
4. Zone-redundant storage (ZRS)
5. Geo-zone-redundant storage (GZRS)
6. Read-access geo-zone-redundant storage (RA-GZRS)

These options help you decide how your data is stored and protected in Azure Storage.

### Storage Accounts Endpoints

When you create an Azure Storage Account, it gives you a special and unique name for your data in Azure. This name is important because it forms the web address (or endpoint) where you can access your data. To make sure everyone has a different name, there are some rules:

1. Your storage account name can be between 3 and 24 characters long.
2. It can only contain numbers and lowercase letters.
3. No two storage accounts can have the same name in all of Azure. This makes sure that every storage account has its own special place in Azure where you can put your data.

### Azure Storage Redundancies

Azure Storage is built to make sure your data is safe and always available. It does this by keeping multiple copies of your data. This way, even if something goes wrong like a computer breaking or the internet going down, your data is still safe. 

##### Redundancies in Primary Region 

Data in an Azure Storage account is always replicated three times in the primary region. 

Azure Storage offers two options for how your data is replicated in the primary region, 
1. Locally redundant storage (LRS)

Locally redundant storage (LRS) makes three copies of your data in one data center in the same area. It's the cheapest option but not as safe as others. LRS protects against small problems like a broken computer or hard drive. But if something big, like a fire or flood, happens in that data center, all the copies of your data could be lost.

2. Zone-redundant storage (ZRS).

Zone-redundant storage (ZRS) copies your Azure Storage data across three availability zones in the primary region. It keeps your data available for reading and writing even if one zone has a problem. You don't need to do anything special to keep using your data. Microsoft suggests using ZRS when you need high availability or when you have rules about where your data can be kept within a country or region.

##### Redundancies in Secondary Region 

To ensure high durability, you can make copies of your storage account data in a distant secondary region. This secures your data even in catastrophic failures. When you create a storage account, you choose the primary region, and the secondary region is automatically selected based on Azure Region Pairs. By default, data in the secondary region isn't available for read or write access unless there's a failover to the secondary region. If the primary region becomes unavailable, you can choose to fail over to the secondary region. After the failover has completed, the secondary region becomes the primary region, and you can again read and write data.

Azure Storage offers two options for copying your data to a secondary region: 

1. Geo-redundant storage (GRS):

GRS replicates your data three times in the primary region for immediate protection using LRS. Afterward, it asynchronously copies your data to a separate location in the secondary region (which is its paired region) using LRS as well. This approach ensures extremely high durability for your Azure Storage data objects, with a minimum of 16 nines of durability.

2. Geo-zone-redundant storage (GZRS)

GZRS combines the benefits of high availability within a region, like what ZRS offers, with protection from regional disasters through geo-replication. In a GZRS storage account, your data is copied across three Azure availability zones in the primary region (similar to ZRS), and it's also replicated to a secondary geographic region using LRS. This setup ensures maximum consistency, durability, and availability for your applications, along with excellent performance and disaster recovery resilience. Microsoft recommends using GZRS for such critical scenarios.

### Azure storage services

The Azure Storage platform provides these data services:
1. Azure Blobs: 

Azure Blob storage is like a giant digital storage space in the cloud. It can hold enormous amounts of data, whether it's text, images, videos, or any other type of information. What's great about Blob storage is that it's very versatile – you can store all sorts of data, not just standard files. Blob storage can handle lots of people uploading data at the same time, making it perfect for things like serving images to websites, sharing files, streaming videos, or keeping backups and archives. It's also useful for storing data that needs further analysis by software, whether it's running in the cloud or on your own servers.

2. Azure Files:

Azure File storage is like having a cloud-based filing cabinet. It gives you a place to store your files, and you can access them using standard ways that computers understand. It works with both Windows and non-Windows systems, like Linux and macOS. You can use these files from anywhere, whether you're in the cloud or on your own computers. You can even make copies of your files in different places to access them faster. It's like having your important documents available no matter where you are or what kind of computer you're using.

3. Azure Queues:

Azure Queue storage is like a digital to-do list. It helps you manage tasks or messages that need to be processed, and you can access them from anywhere using the internet. Each task or message can be up to a certain size, and you can store a lot of them. It's great for handling jobs or messages in the background, like when someone submits a form on a website, and you want to do something with that information later. Azure Queue storage helps you keep things organized and process them efficiently.

4. Azure Disks: 

Azure Disk storage is like a virtual hard drive for your virtual machines in the cloud. It's managed by Azure, so you don't have to worry about the hardware details. You just tell Azure how much storage you need, and it handles the rest, making sure your data is safe and available. It's like having a reliable, cloud-based hard drive for your virtual machines.

5. Azure Tables: 

Azure Table storage is like a big, organized table where you can store lots of data. It's good for structured information, like lists or tables of data, and you can access it from inside or outside the Azure cloud. So, whether you're working within Azure or in a hybrid or multi-cloud setup, Azure Table storage helps you keep your data organized and accessible. It's especially handy for structured data that doesn't fit neatly into traditional databases.

##### Benefits 

Azure Storage services offer several advantages for developers and IT professionals:

1. **Durable and Highly Available**: Your data is protected from hardware failures, and you can replicate it across locations for added security in case of disasters or outages.

2. **Secure**: Azure Storage encrypts all data, and you have control over who can access it.

3. **Scalable**: It can handle massive amounts of data and performance requirements for modern applications.

4. **Managed**: Microsoft takes care of hardware maintenance, updates, and critical issues.

5. **Accessible**: Your data can be accessed globally using HTTP or HTTPS. Microsoft provides libraries for various programming languages, a REST API, and tools like Azure PowerShell, Azure CLI, Azure portal, and Azure Storage Explorer for easy data management.

### Azure data migration options

Azure supports both real-time migration of infrastructure, applications, and data using Azure Migrate as well as asynchronous migration of data using Azure Data Box.

1. Azure Migrate

Azure Migrate is like your personal assistant for moving your stuff from your current place to a new home in the cloud. It's a one-stop shop where you can plan, execute, and keep an eye on your move to Azure. You get all the tools you need, like a checklist, a map, and even some expert advice. So, whether you're just exploring or ready to make the big move, Azure Migrate has your back.

2. Azure Data Box

Azure Data Box is like a super-fast moving truck for your data. When you have a ton of data to move to or from Azure, Data Box comes to the rescue. It's a special device that can hold up to 80 terabytes of your data. We send it to you, and you can quickly set it up, load your data, and then send it back to us. Your data is uploaded automatically once we get it back. It's a simple and secure way to move big data to and from Azure.

### Azure File Migration Options

Azure also has tools designed to help you move or interact with individual files or small file groups. Among those tools are AzCopy, Azure Storage Explorer, and Azure File Sync.

1. **AzCopy**: It's a command-line tool for copying files to and from your storage account. You can use it to upload, download, copy, and sync files. It can also work with other cloud providers.

2. **Azure Storage Explorer**: This is a user-friendly app that helps you manage files and blobs in your Azure Storage Account. It works on various operating systems and uses AzCopy in the background for file and blob management.

3. **Azure File Sync**: It's like turning your Windows file server into a mini content delivery network. Once installed on your local server, it keeps your files in sync with Azure. You can access your data locally using different protocols, have multiple caches worldwide, replace failed servers easily, and configure cloud tiering for efficient storage.
