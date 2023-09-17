# Module 5: There’s an API for that!

This is the Fifth Module of the Entire Cloud Computing Foundations Course.It contains the following labs:-
1. GSP094 -- Google Cloud Pub/Sub: Qwik Start - Python
2. GSP499 -- Cloud Endpoints: Qwik Start

## Objectives

1. Explore the purpose and benefit of APIs.
2. Compare Cloud Endpoints and Apigee API Management, two different API management tools
3. Examine Pub/Sub, a Google Cloud tool to handle distributed message-oriented architectures at scale.

### The Purpose of APIs

Application developers structure their software to create a clear and well-defined interface that conceals unnecessary intricacies. This interface is then documented, and it is referred to as an API. The core implementation of the software may undergo changes, but as long as the interface remains intact, other software components utilizing the API do not need to be aware or concerned about these changes. APIs serve the purpose of simplifying communication between different and diverse software resources.

Currently, the most widely adopted architectural style for services is **Representational State Transfer** (REST). REST defines a specific set of constraints and agreements that a service must adhere to. It takes the successful principles used in web development and applies them to services. When a service adheres to these REST constraints, it is termed as RESTful. REST APIs utilize HTTP requests to execute operations such as GET, PUT, POST, and DELETE.

### Cloud Endpoints

Cloud Endpoints is a comprehensive system designed for the development, deployment, and management of APIs on various Google Cloud backends. It operates as a distributed API management solution, employing a distributed Extensible Service Proxy that functions within its dedicated Docker container. Cloud Endpoints offers a range of essential features, including an API console, hosting capabilities, logging, monitoring tools, and more, all aimed at facilitating the creation, sharing, maintenance, and security of your APIs.

Cloud Endpoints is compatible with applications running on platforms such as App Engine, Google Kubernetes Engine, and Compute Engine. It caters to a diverse array of clients, including those on Android, iOS, and JavaScript. Additionally, Cloud Endpoints supports both the Open API specification and the gRPC API specification.

Furthermore, Cloud Endpoints extends its support to service-to-service authentication and user authentication through Firebase, Auth0, and Google authentication mechanisms. The combined efforts of the Extensible Service Proxy, Service Management, and Service Control collaborate to validate incoming requests, log critical data, and efficiently handle high traffic volumes. The Logging and Trace features allow you to access detailed logs, trace information, and metrics that pertain to aspects like traffic volume, latency, request and response sizes, as well as error occurrences.

### Apigee API management

Another Google Cloud platform available for developing and managing API proxies is Apigee API Management. Unlike Cloud Endpoints, Apigee API Management has a specific focus on business problems, like rate limiting, quotas, and analytics. In fact, many Apigee API Management users provide a software service to other companies. Backend services for Apigee API Management don't have to be in Google Cloud, and as a result, engineers also often use it to take apart legacy applications.

So, instead of replacing a large, important application in one move, they can use Apigee API Management to peel off its services individually.This allows them to stand up microservices to implement each in turn, until the legacy application can finally be retired.

### Pub/Sub 

A Google Cloud asynchronous messaging service and API that supports distributed message-oriented architectures at scale.

One of the early stages in a data pipeline is data ingestion, which is where large amounts of streaming data are received. Data, however, may not always come from a single, structured database. Instead, the data might stream from a thousand, or even a million, different events that are all happening asynchronously.

Challenges to data ingestion:
1. The first is that data can be streamed from many different methods and devices, many of which might not talk to each other and might be sending bad or delayed data.
2. The second is that it can be hard to distribute event messages to the right subscribers. A method is needed to collect the streaming messages that come from IoT sensors and broadcast them to the subscribers as needed.
3. The third is that data can arrive quickly and at high volumes.
4. The fourth challenge is ensuring that services are reliable and secure, and perform as expected.

The name **Pub/Sub** is short for Publisher/Subscriber, or publish messages to subscribers. Pub/Sub is a distributed messaging service that can receive messages from various device streams such as gaming events, IoT devices, and application streams. Pub/Sub ensures at-least-once delivery of received messages to subscribing applications, with no provisioning required. Pub/Sub’s APIs are open, the service is global by default, and it offers end-to-end encryption. 

The 'publisher' refers to the server that is the first node in the cluster, and contains the writeable copy of the config DB. The 'subscribers' are the second, and all other nodes which just contain a replicated copy of the DB (hence the publisher/subscriber name; they are references to SQL replication roles).

A central element of Pub/Sub is the **topic**. A topic is a named resource to which messages are sent by publishers. 

Similarly, a publisher can send data to a topic that has no subscriber to receive it or a subscriber can be waiting for data from a topic that isn’t getting data sent to it, like listening to static from a bad radio frequency. Pub/Sub supports many different inputs and outputs, and you can even publish a Pub/Sub event from one topic to another.