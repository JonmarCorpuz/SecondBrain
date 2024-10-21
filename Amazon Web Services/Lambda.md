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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Lamdba Power Tuning

Lambda Power Tuning is an open-source state machine that helps users visualize and fine-tune the memory or power configuration of Lambda functions

* Supports three optimization strategies: Cost, Speed, and Balanced
* Helps users optimize their Lambda functions for cost or performance in a data-driven way
* Powered by AWS Step Functions
* Designed to be easy to deploy, fast to execute, and language agnostic
* Requires a Lambda function ARN as input for it to work, which the state machine will then invoke with multiple power configurations in order to then analyze all the execution logs to suggest the best power configuration to minimize cost or maximize performance
* The inputted Lambda function will run on the user's AWS account and perform actions on its behalf (Ex: *HTTP requests*, *SDK calls*, *Cold starts*, *etc.*)
* Supports cross-Region invocations and parallel exeuction
* Generates a visualization of average cost and speed for each power configuration

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Lambda Layers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Lambda Powertools

Lambda Powertools is a suite of utilities for AWS Lambda functions that's designed to make it easier to adopt best practices (Ex: *Tracing*, *Structured logging*, *Custom metrics*, *Idempotency*, *Batching*, *etc.*)
