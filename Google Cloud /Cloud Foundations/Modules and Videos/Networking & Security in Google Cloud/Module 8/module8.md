# Module 8: Keeping an eye on things

This is the Eight hModule of the Entire Cloud Computing Foundations Course.It contains the lab: GSP089 -- Cloud Monitoring: Qwik Start


## Objectives

1. Learn about Infrastructure as Code (IaC)
2. Explore Terraform as an IaC option.
3. Examine the role of monitoring, logging, error reporting, tracing, and profiling in the cloud.
4. Learn how to use Google Cloud operations suite for monitoring, logging, error reporting, tracing, and profiling.

### Infrastructure as Code(IaC)

Creating an environment in Google Cloud can be a lot of work, such as setting up networks and storage and keeping an eye on how they're configured. This process can be done manually by typing in commands to set up your environment as needed, but it's labor-intensive as you have to write new commands

Infrastructure as code, or IaC, simplifies this. It involves defining what your infrastructure should look like as code. IaC tools use templates to create entire architectures automatically. Instead of manually using a console or running commands to build your system, the template does it for you. The same template can also update or remove resources when needed.
Since templates are treated as code, you can store them in repositories, track changes with version control, and share them with others. Templates can even be used for disaster recovery. If your infrastructure needs to be rebuilt for any reason, the templates can be used to automatically restore it.

### Terraform

Terraform is a versatile and widely embraced open-source infrastructure as code (IaC) tool designed to streamline the creation, modification, and enhancement of infrastructure with precision and efficiency. It enables organizations and developers to codify their infrastructure requirements, making it easier to provision and manage resources. Terraform's strength lies in its ability to manage infrastructure not only across various public cloud providers like AWS, Google Cloud, and Azure but also on-premises and in hybrid or multi-cloud environments. 

It achieves this by interacting with APIs, allowing users to define infrastructure configurations in a declarative manner, providing a clear separation between the desired state and the current state, and enabling thorough planning and execution of infrastructure changes. Terraform's flexibility and broad support for platforms and services, coupled with its strong community and version control capabilities, make it a go-to solution for automating and maintaining infrastructure across diverse IT landscapes.

### Monitoring and managing services, applications, and infrastructure

Monitoring is like the foundation of a reliable product. It helps by spotting urgent issues and tracking how people use the application, which can help plan for the future and make the user experience better. Google's Site defines monitoring as collecting and displaying real-time data about a system, like how many queries it's handling, any errors, and how long it takes to process things. Monitoring helps keep the system running, analyze trends, make dashboards, and alert people when things go wrong. It's not just about what users see; it's also about having enough capacity, testing thoroughly, and explaining why problems happen to build trust with users.

### Google Cloud's operations suite

Google Cloud's **operations suite** is a comprehensive set of tools that offers robust capabilities for monitoring, logging, error reporting, and debugging applications running in the cloud. It provides valuable insights into the health, performance, and availability of cloud-based applications, enabling quicker issue identification and resolution. 

Monitoring is a critical aspect of DevOps, and it starts with collecting real-time quantitative data about a system, such as metrics that measure CPU usage, query counts, error rates, and more. Google Cloud collects over a thousand streams of metric data by default, which can be utilized in dashboards and alerts. Logging, on the other hand, records various types of data, including audit logs for tracking user activity, agent logs for ingesting data from cloud instances, network logs for monitoring network services, and service logs for developer-created logs. Error reporting helps identify and analyze crashes and exceptions in cloud services, while Cloud Trace provides latency data analysis for distributed applications. Cloud Profiler, on the other hand, offers CPU and heap usage insights without impacting application performance, making it a valuable tool for optimizing code.
