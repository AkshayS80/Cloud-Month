# Module 9: You have the data, but what are you doing with it?

This is the Ninth Module of the Entire Cloud Computing Foundations Course.It contains the following labs:-
1. GSP103 -- Dataproc: Qwik Start - Console
2. GSP104 -- Dataproc: Qwik Start - Command Line
3. GSP105 -- Dataprep: Qwik Start
4. GSP192 -- Dataflow: Qwik Start - Templates
5. GSP207 -- Qwik Start - Python

## Objectives

1. Explore big data managed services in the cloud.
2. Examine using Dataproc to run Apache Hadoop, Apache Spark, and other big data technologies as a managed service in the cloud.
3. Learn about building ETL pipelines as a managed service by using Dataflow.
4. Explore BigQuery as a managed data warehouse and analytics engine.

### Big Data Management Services

Enterprise storage systems are now dealing with data sizes in petabytes, which is a million gigabytes or a thousand terabytes. Depending on the industry, a petabyte can be either substantial or relatively small. Many companies are collecting and storing data for insights into their operations, and this is where big data solutions come in. 
Google offers three managed services for data processing: 
1. Dataproc for running open-source software like Apache Hadoop and Apache Spark, 
2. Dataflow for stream processing, and 
3. BigQuery for fast SQL analytics on large datasets.

### Dataproc

**Dataproc** is a powerful tool for running **Apache Hadoop** and **Apache Spark**, which are essential for big data processing. It's designed to be **cost-effective, quick, and easy to use**. You only pay for what you use, and clusters can start, scale, and shut down rapidly. It supports a wide range of open-source tools, making it versatile for various projects. Dataproc is fully managed, eliminating the need for specialized administrators. It integrates seamlessly with other Google Cloud services like Cloud Storage, BigQuery, and Cloud Bigtable, providing a comprehensive data platform. You can use Dataproc for tasks like processing large log data efficiently, scaling Spark clusters for analytics, or running machine learning algorithms on massive datasets. It's a valuable resource for organizations working with big data, unlocking the power of the cloud without added complexity.

### Dataflow

**Dataflow** is a Google-managed service for handling big data tasks efficiently. It sets up pipelines to process both real-time streaming data and large-scale batch data, which involves tasks like data extraction, transformation, and loading (ETL). Dataflow simplifies tasks by automating resource management, optimizing performance, and ensuring fault tolerance. It integrates smoothly with other Google Cloud services like Cloud Storage, Pub/Sub, Datastore, Cloud Bigtable, and BigQuery for seamless data processing across platforms.

1. Create a BigQuery dataset and table by using Cloud Shell and/or the Google Cloud console
2. Run the pipeline 
3. Submit a query.

### BigQuery

**BigQuery** is Google's fully-managed data warehouse that handles vast amounts of data, making it simpler for businesses to gain insights. It handles all the infrastructure complexities, leaving you free to run SQL queries to answer crucial business questions. BigQuery supports machine learning, geospatial analysis, and business intelligence. You can pay based on the data processed and stored, or opt for a fixed monthly fee. Data is automatically encrypted at rest, and it integrates seamlessly with various Google Cloud services. Loading data into BigQuery can be done in batches, through streaming, or via SQL queries. BigQuery excels at lightning-fast analytics on massive datasets, enabling real-time insights and integration with visualization tools. It also features built-in machine learning capabilities, making it accessible to data analysts without extensive coding or ML expertise. This functionality can be accessed through the BigQuery web UI, bq command-line tool, REST API, or external tools like Jupyter notebooks and BI platforms.
