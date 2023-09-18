# Module 10: You have the data, but what are you doing with it?

This is the Tenth Module of the Entire Cloud Computing Foundations Course.It contains the following labs:-
1. GSP089 -- Google Cloud Pub/Sub: Qwik Start - Python
2. GSP499 -- Cloud Endpoints: Qwik Start

## Objectives

1. Define machine learning (ML), understand the terminology used, and identify the value proposition.
2. Explore Vertex AI, Google’s unified AI platform.
3. Use Google APIs to apply a range of pre-trained ML models.

### Machine Learning and Artificial Intelligence

Artificial intelligence, or AI, encompasses computer processes that imitate human intelligence. For example, in online word processors, AI helps with spelling and grammar checks. Machine learning, on the other hand, is a toolset that allows solving complex problems using data without writing custom code. 

Deep learning, a subset of machine learning, adds layers to improve learning depth, particularly for unstructured data like images, speech, and text. It's different from traditional AI because machines learn from data, becoming intelligent through training. 

Training involves providing examples, like showing tax returns to estimate taxes owed or previous journeys to predict trip times. During training, each example has an input and a correct answer, known as the label. After training, the model can predict outcomes for new data. 

The quality of training data significantly impacts model performance. Standard algorithms or models exist independently of use cases, such as image classification networks. Despite using the same algorithm, trained models for different tasks differ. 

Google Cloud offers various options for building machine learning models:
1. BigQuery ML
2. AutoML
3. Custom training
4. Pre-built APIs

### ML models with Vertex AI

Google has integrated AI into products like Gmail, Google Maps, Google Photos, and Google Translate. However, creating AI technologies and putting machine learning models into action comes with its share of challenges. These include handling vast amounts of data, choosing the right machine learning model, and having enough computing power. Moreover, there are difficulties in transitioning machine learning models into real-world production environments, which require scalability, monitoring, and continuous integration.

Google's answer to these production and usability challenges is **Vertex AI**, an integrated platform that brings together all aspects of the machine learning process and workflow. This unified platform simplifies the entire journey of creating, managing, and deploying machine learning models, making it easier to work at scale over time.

The benefits of Vertex AI can be summarized as the Four S's: It's 
1. Seamless, ensuring a smooth experience from data preparation to model deployment. 
2. Scalable, thanks to built-in machine learning operations (MLOps) that manage resources automatically.
3. Sustainable, allowing for the reuse and sharing of created artifacts and features. 
4. Speedy, generating models with significantly fewer lines of code compared to competitors.

### AutoML

AutoML, which stands for automated machine learning, is a user-friendly solution within Vertex AI that simplifies the process of building high-quality custom machine learning models without requiring extensive machine learning expertise or coding skills. It automates many of the manual tasks typically associated with training and deploying machine learning models. AutoML is a versatile tool that can handle different data types and objectives, making it a valuable asset for various machine learning projects.

AutoML achieves its automation through two key technologies: 
1. Transfer learning -- Transfer learning allows AutoML to leverage pre-trained models on large datasets, reducing the need for extensive data and computation.
2. Neural architecture search. -- Neural architecture search, helps AutoML find the best model architecture for a specific project, similar to finding the most suitable book in a library.

AutoML combines these technologies to train and evaluate multiple machine learning models, ultimately selecting the best-performing one. This approach benefits data scientists in several ways. Firstly, it's a no-code solution, meaning it doesn't demand in-depth machine learning expertise or coding skills. Data scientists can focus on defining business problems and improving model results, rather than getting bogged down in complex coding.

### Custom training

Custom training within Vertex AI Workbench provides you with the flexibility to create your own machine learning (ML) environment, allowing you to control every aspect of the ML development process, from data preparation to model deployment, using code.

If you prefer coding your machine learning model, Vertex AI Workbench offers this option, serving as a comprehensive development environment for the entire data science workflow, including data exploration, model training, and deployment.

Before diving into coding, you need to decide on the environment for your ML training code, and there are two choices: 
1. Pre-built containers 
2. Custom containers.

### Pre-Built APIs

Pre-built APIs are essentially ready-made services that can act as fundamental building blocks for creating applications without the need to develop your own custom models. They streamline the process by eliminating the time and effort required to build, curate, and train a new dataset, allowing you to focus directly on making predictions.
