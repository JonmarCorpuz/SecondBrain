AWS Lambda is a serverless computing service that allows users to run code without provisioning or managing servers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/AWS%20Lambda.png)

* Requires zero administration from the user, meaning that they can upload their code and AWS will take care of everything required to run and scale the code with high availability
* Executes a user's code in response to events/triggers 
* Follows a pay-per-use pricing model by charging only for the compute time a user's code consumes
* Automatically scales a user's application by running code in response to each trigger 
* Automatically executes a user's code securely within a dedicated execution environment, which is isolated from other functions 
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
