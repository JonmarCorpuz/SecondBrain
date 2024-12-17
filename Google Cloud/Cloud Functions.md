# Cloud Functions Overview

Cloud Functions is a FaaS service product that offers users a serverless execution environment to run event-driven code without the need to manage or provision servers

* A lightweight computing option that's well suited to event-driven processing
* Runs code in response to an event (Ex: *File being uploaded to Cloud Storage*, *A message being written to a message queue*, *etc.*)
* The code that executes must be short-running (Cloud Functions isn't designed to execute long-running code)
* Supports multiple programming languages and time bound, meaning that they have a time limit
* Often used to call other services (Ex: *Third-party APIs*, *etc.*)
* Helps avoid dependencies between services
* Each invocation of a Cloud Function runs in a separate instance, meaning that functions don't share memory or viables
* The execution of one function is independednt of all others (The life cycles of Cloud Functions aren't dependent on each other)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Function Components

| Cloud Function Component | Description |
| --- | --- |
| Event | Something that happens |
| Trigger | The Function call that responds to an event | 
| Function | A function that takes the event data and performs the action that the user wants to perform |

## Event 

| Event Type | Description |
| --- | --- |

## Trigger 

## Function

* One function instance can handle only one request at a time (1 function invocation = 1 function instance)
* A function instance that completes executing its task, it may be reused for future requests

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Function Environments

| Cloud Function Environment | Description |
| --- | --- |
| 1st Generation | |
| 2nd Generation | |

## 1st Generation Cloud Run Environment

* Can only make 1 concurrent request per function instance
* Uses the App Engine default service account by default (PROJECT_ID@appspot.gserviceaccount.com)

## 2nd Generation Cloud Run Environment

* Longer request timeout
* Larger instance sizes
* Can make up to 1000 concurrent requests per function instance
* Offers multiple function revisions and traffic splitting, which aren't supported in the 1st generation Cloud Run environment
* Uses the default compute service account by default (PROJECT_NUMBER-compute@developer.gserviceaccount.com)
