# Pub/Sub Overview

Google's Pub/Sub is an asynchronous, scalable, and fully-managed messaging service that decouples services producing messages from services processing those messages

* Allows services to communicate asynchronously, with latencies on the order of 100 milliseconds
* Supports pushing and pulling message deliveries

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Pub/Sub Components

| Pub/Sub Component | Description |
| --- | --- |
| Publisher | The sender of a message |
| Topic | |
| Subscription | The receiver of a message |

## Publisher

* Sends messages by making HTTPS requests 

## Topic

* Can have multiple subscribers that are subscribed

## Subscriber

* Pulls messages from the topic that it's subscribed to through HTTPS requests
* Messages sent by a publisher can also be pushed automatically to its designated subscriber
* Can have multiple clients that are subscribed

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
