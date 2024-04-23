Kinesis is a platform that collects, processes, and analyzes real-time stream data

* Enables users to build applications that can continuously capture, store, process, and analyze vast streams of data in real time
* Provides a set of tools to handle everything from data ingestion and storage to real-time analytics and insights

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kinesis Family

The Kinesis Family refers to the different Kinesis services that are designed for real-time processing and analysis of streaming data

## Kinesis Data Streams

Kinesis Data Streams is a highly scalable real-time data streaming service that's designed to capture, process, and store large streams of data records in real time as it arrives

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Kinesis%20Data%20Streams%20Example.png)

* Designed to continuously capture gigabytes of data per second from hundreds of thousands of sources that usually become available in milliseconds
* Enables users to build applications that require continuous data ingestion and real-time processing from multiple sources
* Ensures high durability and availability by storing captured data records across multiple AZs in a region for up to a year
* Designed to simplify the real-time collection and processing of data streams by managing the infrastructure, storage, networking, and configuration needed to process large streams of data

## Kinesis Video Streams

Kinesis Video Streams is a fully managed service designed to securely stream video from connected devices to AWS for analytics, ML, and other processing

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Kinesis%20Video%20Streams%20Example.png)

* Enables users to build applications that can play, process, and analyze video streams in real-time
* Simplifies the complexity associated with capturing, storing, and managing video streams
* Enables users to build applications that can take advantage of live and recorded video data without having to worry about the underlying storage or infrastructure
* Provides a secure channel for streaming video from devices to the AWS cloud while using encryption to protect data both in transit and at rest
* Supports both real-time and batch video processing to allow the analysis of video data as it's being streamed or after it's stored
* Enables automated video analysis for object detection, facial recognition, and other AI-drive insights
* Eliminates the need for managing storage infrastructure by automatically storing the video data that's streamed to Kinesis Video Streams in the AWS cloud, where it can be easily accessed for processing and analysis
* Allows users to stream video from devices by providing SDKs for integrating Kinesis Video Streams with a variety of devices and applications

## Kinesis Data Firehose

Kinesis Data Firehose is a fully managed service designed to automatically capture, transform, and load streaming data into AWS services for near real-time analytics with existing business intelligence tools

* Simplifies the process of loading large amounts of streaming data into data lakes, data stores, and analytics services
* Enables users to transform their data before loading it into the destination by calling an AWS Lambda function to transform incoming data or convert the data format before storing it
* Scales automatically to accommodate the volume of incoming data
* Enables users to reduce storage costs and enhance data security by supporting data compression and ecryption

## Kinesis Data Analytics

Kinesis Data Analytics is a fully managed service that enables users to easily process and analyze streaming data in real time

* Allows users to write standard SQL queries against incoming streams of data in order to gain insights and respond to new information quickly
* Processes and analyzes streaming data as it arrives, which is crucial for applications that need to make immediate decisions based on the latest information
* Allows users to use SQL to easily query streaming data
* Ensures that a user's data processing can grow with their data by automatically scaling to match the volume and throughput rate of their incoming data streams
* Handles the provisioning, configuration, and scaling of the resources needed in order to reduce the complexity of building, managing, and integrating streaming data processing applications

