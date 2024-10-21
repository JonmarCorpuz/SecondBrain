
* A fully managed, message queing service that can be used to decouple and scale microservices, distributed systems, and serverless applications
* Reduces the complexity and overhead associated with managing and operating message-oriented middleware
* Allows users to send, store, and receive messages between software components at virtually any volume, without losing messages or requiring other services to be available

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Retrieving Messages 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/3QKUCv46QKSEw5tKZB6Wiw_ece62d9ec28a4cfba7bf372df8d99df1_Reading1.5A.png)

## Short Polling

Short polling is a method used to retrieve messages from an SQS queue by sending individual requests to the SQS service every time the client wants to check to messages

* May result in frequent requests to the SQS service, which can lead to increased costs and unnecessary load on the SQS service

![]()

1. Client sends a request to the SQS service to receive messages from a specific queue
2. SQS service checks the queue for messages (If there are messages available in the queue at the time of the request then the service immediately returns them to the client along with a successful response and vice-versa)
3. Client processes the received messages and takes appropriate action based on the message content
4. Client then may choose to repeat the process by sending another request to the SQS service to receive more messages

## Long Polling

Long polling is a method used to retrieve messages from an SQS queue by sending requests to the SQS service and keeping those connections open in case the client wants to wait and check for any incoming messages again

* Helps reduce the number of empty responses returned by the SQS service
* Helps optimize costs and improve efficiency by reducing the number of unnecessary requests made by the client to check for new messages
* Reduces false empty responses by querying all SQS servers in the user's VPC

![]()

1. Client sends a receive message request to the SQS service for a specific queue while specifying a wait time
2. SQS service will continue checking the queue for messages during the specified wait time (If there are messages available in the queue while the connection is open then the service immediately returns them to the client along with a successful response and vice-versa)
3. Client processes the received messages and takes appropriate action based on the message content
4. Client then may choose to repeat the process by sending another request to the SQS service to receive more messages
5. Useful for applications that require real-time or near-real-time message processing with minimal latency
