# Pub/Sub Overview

Google's Pub/Sub is an asynchronous, scalable, and fully-managed messaging service that decouples services producing messages from services processing those messages

* Allows services to communicate asynchronously, with latencies on the order of 100 milliseconds
* Supports pushing and pulling message deliveries

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Pub/Sub Components

## Publisher

A publisher is a sender of a message

* Sends messages by making HTTPS requests 

## Topic

* Can have multiple subscribers that are subscribed

## Subscription

## Subscriber

A subscriber is a receiver of a message

* Pulls messages from the topic that it's subscribed to through HTTPS requests
* Messages sent by a publisher can also be pushed automatically to its designated subscriber
* Can have multiple clients that are subscribed

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Deploy Pub/Sub

## Step 1: Create a Topic

```Bash
gcloud pubsub topics create <TOPIC_NAME>
```

## Step 2: Create a Subscription

* Subscriptions can be pulled (The application reads from a topic) or pulled (The subscription writes messages to an endpoint)

```Bash
glcoud pubsub subscriptions create <SUBSCRIPTION_NAME> --topic <TOPIC_NAME>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# How Pub/Sub Works

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/vnmbnvmnvcncmvnmxcxnmcnxmxcxnxm.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Publisher-Subscriber Relationship Types

| Publisher-Subscirber Relationship Type | Description |
| --- | --- |
| One to Many | |
| Many to One | |
| Many to Many | |
