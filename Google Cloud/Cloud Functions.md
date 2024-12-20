# Cloud Functions Overview

Cloud Functions is a FaaS service product that offers users a serverless execution environment to run event-driven code without the need to manage or provision servers

* Runs single-purpose functions in response to an event (Ex: *File being uploaded to Cloud Storage*, *A message being written to a message queue*, *etc.*)
* The code that executes must be short-running (Up to 60 minutes for HTTP functions and 10 minutes for event-drive functions)
* Supports multiple programming languages
* Often used to call other services (Ex: *Third-party APIs*, *etc.*)
* Helps avoid dependencies between services by providing the possibility to move workloads from one stage to another
* Each invocation of a Cloud Function runs in a separate instance, meaning that functions don't share memory or viables
* The execution of one function is independednt of all others (The life cycles of Cloud Functions aren't dependent on each other)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Function Components

## Event 

An event is a particular action that happens in the cloud (Ex: *A file being uploaded to Cloud Storage*, *etc.*)

* For each Cloud Functions enabled events that occur, you can define a trigger

### HTTP 

Invokes a function by making an HTTP request using POST, GET, PUT, DELETE, and OPTIONS calls 

### Cloud Storage 

A function can be triggered every time a user deletes, uploads, or achives a file in Cloud Storage 

### Cloud Pub/Sub 

A function can be triggere every time a user writes to a Pub/Sub topic

* Remember that messages in Pub/Sub are encoded to allow for binary data in a place where text data is expected

### Cloud Firestore

Either create, delete, or write an event 

### Cloud Firebase 

Invokes database triggers, remote configuration triggers, and authentication triggers 

## Trigger 

A trigger is the function that you want to execute when an event occurs

* Declares that an action should be taken

## Function

* One function instance can handle only one request at a time (1 function invocation = 1 function instance)
* A function instance that completes executing its task, it may be reused for future requests

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Function Environments

* Each time a function is invoked, it's run in a separate instance frmo all other invocations (There's no way of sharing information between invocations of functions using only Cloud Functions)
* Some particular runtime versions may be recommended over others

## 1st Generation Cloud Run Environment

* Can only make 1 concurrent request per function instance
* Uses the App Engine default service account by default (PROJECT_ID@appspot.gserviceaccount.com)

## 2nd Generation Cloud Run Environment

* Offers longer request timeout and larger instance sizes
* Can make up to 1000 concurrent requests per function instance
* Offers multiple function revisions and traffic splitting (Not supported in the 1st generation Cloud Run environment)
* Uses the default compute service account by default (PROJECT_NUMBER-compute@developer.gserviceaccount.com)
