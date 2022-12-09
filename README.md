# Analytics For IoT Logical Architecture

## Overview of Analytics for IoT

 SAS® Analytics for IoT is a complete AI-embedded IoT analytics solution that covers the entire IoT analytics life cycle.  It was created for all types of users --business users, engineers, data scientist and IT professionals--who want to accelerate time to value (new insight, fast & accurate decision making, desirable outcomes) from their use cases.  The solution enables them to organize their diverse IoT data, create data selections, visually explore massive volumes of high frequency data, and launch data sets that can be leveraged in SAS, third party and open source applications.  With this capability, organizations can extend the use of IoT analytics and collaboration across the enterprise, while optimizing their ecosystem of IoT investments –SAS, third party and open source.

 ## Logical Architecture
 ![img](/images/AIoT.JPG)

## Components of Analytics for IoT

SAS Analytics for IoT is built on a robust technical architecture. The solution package includes SAS Event Stream Processing, SAS Event Stream Manager, SAS Data Preparation, SAS Visual Analytics, SAS Visual Statistics, SAS Visual Data Mining & Machine Learning, SAS Visual Forecasting, SAS Model Manager, SAS Intelligent Decisioning, SAS Visual Text Analytics, SAS/ACCESS, and more.  Full packaging for SAS Analytics for IoT is available in the links below.  SAS Analytics for IoT also includes a proven, sensor-focused data model spanning telemetry, ERP, MES, CRM, Smart Devices, and beyond.  As well as an integrated business-focused user interface for selecting data, visually exploring it, and launching it into SAS, third party and open source applications.

## Platform compatibility
![img](/images/SupportedCloud.JPG)

## Data Flow

Lets discuss the architecture by taking an example of Industrial IoT use case where end manufacturer can connect assets using OPC UA(Open Platform Communication Unified Architecture). The manufacturer will have the assets and inustrial components connected to the edge gateway enabled with SAS Event Stream Processing(ESP) at the edge and utilize the out of the box connector for OPC UA to ingest real time data. This will enable use of Predictive Maintainence for improving asset efficieny, reduce cost by optimizing production, mitigate any discruption by utilizing machine learning & advance analytics to production and predict outages.This can also help in ensuring production uptime with real time alerts and great insights for manufacturing data.

Data flow for the solution will be as follows:

1. Industrial devices which can communicate via OPC UA or Modbus can directly publish data to SAS ESP at the edge by utilizing native connectors of ESP. ESP edge runs as a docker container on the edge gateway and enables analytical capabilities closer to where the data originates.It scores the data against the analytics model running at ESP for predicting machine failure or remaining useful life(RUL) etc.

2. The Ingestion,provisioning & device management service as shown in the figure will connect edge device virtually to the cloud/on-premise for further data processing and model retraining. It could be also used for device management and updates by using bi-directional communication.The service could be your on-premise service or a service from cloud provider e.g. Azure IoT Hub, AWS IoT Core or GCP IoT Core.

3. The message bus e.g. Azure Event Hub,Amazon Kinesis Data Stream, Google Cloud Pub/Sub,Apache Kafka or Rabbit MQ stores the data for further data integration & processing.

3. SAS ESP server on cloud/on-premise processes the telemetry data from mesage bus and enables aggregation,correlation and advance analytics on data from different edge devices across production floor site by utilizing low latency data stores e.g. redis,aerospike or singlestore and provides integration with third party services and business integration whether it is sending a SMS or an email notification or invoking a workflow.

4. Data is also stored in enterprise data lake for further processing or analytical model retraining purposes.

5. Data is explored by visualizing it in SAS visual Analytics.
 
## Edge

SAS Event Stream Processing(ESP) for Edge Computing addresses challenges presented by growing list of operational streaming data sources which creates bottleneck for data transmission and data storage;
ESP provides a scalable, flexible streaming analytics engine for problems ranging from streaming pattern
matching to sophisticated and powerful computer vision algorithms for object detection and
classification. It can be deployed quickly to various edge devices using standard container
technology or bare metal deployments to maximize the value of analytics on the edge,
close to where the data originates.

You can deploy SAS Event Stream Processing for Edge Computing in one of two ways:

* directly onto a Linux system
* with Docker
### Hardware requirements for SAS ESP on the edge

| Item | Recommended Level |
| -----|:-----------------:|
| CPU | Dual or quad-core x86_64 compatible processor. 64-bit ARMv8 chipsets are supported.|
|Memory|4 GB of available RAM|
|Disk Space| 400 MB - 1.5 GB free space for the installation|

### Hardware requirements for Docker container deployment of SAS ESP on edge
|Item| Recommended Level|
| -----|:-----------------:|
|CPU| Dual or quad core x86_64 compatible processor|
|Memory|4 GB of available RAM|
|Disk Space| 750 MB or more of free space for the installation|

## Ingestion, Provisioning & Device Management

Cloud gateway acts as a central message hub for communication between an IoT application and its attached devices. You can connect devices and their backend solutions reliably and securely.

[Azure IoT Hub](https://azure.microsoft.com/en-us/services/iot-hub/), [AWS IoT Core](https://aws.amazon.com/iot-core/?nc=sn&loc=0) & [GCP IoT Core](https://cloud.google.com/iot-core) supports device-to-cloud telemetry, uploading files from devices, and request-reply methods to control your devices from the cloud. The cloud gateway also supports monitoring to help you track device creation, device connections, and device failures.

Each of the service supports scaling to millions of simultaneously connected devices and millions of events per second to support different IoT workloads.

## Message Bus

Whether you are using a serverless or fully managed streaming data service like [Azure Event Hub](https://azure.microsoft.com/en-us/services/event-hubs/#overview), [AWS Kinesis data stream](https://aws.amazon.com/kinesis/data-streams/) or [Google cloud Pub/Sub](https://cloud.google.com/pubsub) or building your own custom message bus utilizing Apache kafka or RabbitMQ, you can have the messaging middleware infrastructure which helps in buidling your data pipelines for streaming analytics and enabling event driven architecture. Message bus will act as the event ingestor and decouple event producers(e.g. IoT Assets or Sensors) and event consumers (e.g. event stream processing application like SAS ESP).

## Stream Processing

Stream processing involves ingesting a continuous data stream to quickly analyze, filter, transform , aggregate or enhance the data in real time. Data is passed off to an application, data store or another stream processing engine after it is processed. Stream processing enables real-time analytics and in the diagram you can see SAS Event stream processing which enables you to quickly process and analyze a large number of continuously flowing events. It works with various SAS solutions to provide real-time streaming event analysis for manufacturing, health-care, energy and utilities, financial services, cyber security, and fraud detection.


## Model Building, Data Exploration, Reporting, ModelOps

There are diffrent components of SAS Analytics for IoT which can be utilized for analytical model building, exploring data from IoT devices/systems, creating reports, managing models and retraining them as described below:

**SAS Visual Data Mining and Machine Learning** which is part of SAS Analytics for IoT combines data wrangling, exploration, feature engineering, and modern statistical, data mining, and machine learning techniques in a single, scalable in-memory processing environment. 

It provides a comprehensive, visual interface for accomplishing all steps related
to the analytical life cycle. In addition to innovative machine learning and deep
learning techniques for analyzing structured and unstructured data, it integrates
all other tasks in your analytical processes. From data preparation and
exploration to model development and deployment, multiple personas work
in the same, integrated environment.

**SAS Visual Analytics** enables you to explore, discover, and predict by using your data. You can explore data quickly to identify patterns, trends, and opportunities for further analysis. The highly visual, drag-and-drop data interface of SAS Visual Analytics accelerates analytic computations and enables organizations to derive value from massive amounts of data. It’s easy to create and share reports and
dashboards that monitor business performance.

**SAS Model Manager** helps streamline analytical model registration, deployment, monitoring, and management of SAS and open-source models, keeping them in one central place for data scientists and information technology (IT) teams. Using SAS Model Manager, you can store models in a common model repository, and organize them within projects and folders. You can also evaluate models for champion model selection, monitor performance of models, and publish models. All model development and model maintenance personnel, including data modelers, validation testers, scoring officers, and analysts, can use SAS Model Manager.

**SAS Decision Manager** helps organizations manage data, business rules, analytical models, and optimization techniques. Business rules capture the logic of business decisions and are one of the core components of decision management systems. Business rules make the decision-making process transparent and adaptable, allowing organizations to respond quickly to new information. You can use SAS Decision Manager to create a database of business rules, connect those rules together into rules flows, and publish the rule flows for use by other applications. Using SAS Decision Manager, you can
store models and organize them within projects or folders, validate candidate models, assess candidate models for champion model selection, publish and monitor champion models in a production environment
or retrain models.

## Management & Business Integration

Business integration action could be raising alarms, sending SMS message or an email or integrating with business applications like ERP and CRM or even integrating with third party visualization tool. With SAS Analytics for IoT you have out of the box tools & connectors to integrate with open source & third party software.  

## Key features of SAS Analytics for IoT

Analytics for IoT offers following features:

 1. Flexible Data Model for Sensor Data and Related Domains
 2. Streeamlined ETL for accelerated time to value
 3. Data Profile to understand currently available data
 4. Unified Business-focused Data Selection User Interface
 5. Explorations to reduce and visualize high frequency data
 6. Cross-Domain Data Selections to identify patterns across customer, product, and process domains
 7. Launchers for:
    * VA
    * VDMML
    * SAS Studio
    * Comma-delimited files
 8. Streaming Model Execution via Event Stream Processing
 9. Public APIs to integrate with other products & custom solutions

 ## Hardware & Resource Requirements

 For hardware and resource requirements refer to the [link](https://go.documentation.sas.com/doc/en/itopscdc/v_028/itopssr/n0ampbltwqgkjkn1j3qogztsbbu0.htm).

## Demo
[![Demo Video](http://img.youtube.com/vi/CoqOglnWveE/0.jpg)](http://www.youtube.com/watch?v=CoqOglnWveE)

## Contributing

This project does not accept contributions.

## License

This project is licensed under the [SAS License Agreement for Corrective Code or Additional Functionality](LICENSE).

## Additional Resources

* Analytics for IoT Pricing & Offering: [Link](http://sww.sas.com/wwm/pricing/analyticsforIOTviya4.php)
* Analytics for IoT public page: [Link](https://www.sas.com/en_us/software/analytics-iot.html)
* Analytics for IoT packaging overview: [Link](http://sww.sas.com/wwm/pricing/privatepackaging/final_overviews.php#V)
* SAS ESP documentation: [Link](https://go.documentation.sas.com/doc/en/espcdc/v_020/espca/titlepage.htm?homeOnFail)
