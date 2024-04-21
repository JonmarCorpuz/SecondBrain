AWS Lambda is a serverless computing service that allows users to run code without provisioning or managing servers in response to events and triggers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/AWS%20Lambda.png)

* Follows a pay-per-use pricing model by charging only for the compute time a user's code consumes
* Automatically scales a user's application by running code in response to events and triggers within a dedicated execution environment that's isolated from other functions for up to 15 minutes
* Each event or request that comes in spins up its own instance of a Lambda function, which runs in a microVM that's powered by Firecracker and that'll shut down on its own after a period of time, meaning that it only runs when it needs to run
* Users are responsible for the code they provide to a lambda function, while Lambda manages the resources and performs operational and administrative tasks on behlaf of the users
* Supports various programming languages and custom runtimes, and is more suited for quick processing (Ex: *Web backend handling request*, *Backend report processing service*, *Microservice hosting*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AWS Lambda Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/HQH_LlrGRkq3H9mASnI1Qg_0bef7cf0cd064c6590ae6894edda74f1_image.png)

## Event/Trigger

An event or trigger refers to a specifc occurrence or action that initiates the execution of a Lambda function (Ex: *AWS related events*, *HTTP requests*, *Scheduled events*, *etc.*)

* Enables users to integrate a Lambda function with other AWS services 

## Code

The code refers to the actual program or function that the user writes and uploads to the Lambda service for execution

* Contains the logic that defines the functionality that the user wants the Lambda function to perform
* Can be packaged along with any dependencies or libraries it requires to run into a deployment package, which can be yploaded to AWS Lambda

### Lambda Function Handler

The AWS Lambda function handler is the method in a user's function code that processes events

* Lambda runs the function handle when the function is invoked
* When the function handler exits or returns a response, it becomes available to handle another event

## Configuration

The configuration refers to the settings and parameters that define how a Lambda function behaves and operates

* Function settings
* Runtime environment, which specifies the programming language and version that AWS Lambda will use to execute the Lambda function's code
* Environment variables
* Concurrency and scaling
* Logging and monitoring
* Permissions and security
* Tags

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/AWS%20Lambda.png)

# Lambda Features

## Lamdba Power Tuning

## Lambda Layers
