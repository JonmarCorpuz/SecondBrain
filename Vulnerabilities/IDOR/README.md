# Insecure Direct Object Reference Overview

IDOR allows a user to access resources that don't belong to them by directly referencing the object ID, object number, or filename

* IDOR happens when an application fails to implement access control based on user identity and fails to randomize object IDs by instead keeping reference to data objects predictable

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Hunting for IDOR

## Step 1: Create Two Accounts

Create two different accounts on the target website that you can use to test for access control issues

## Step 2: Discover Features

Discover features that might lead you to an IDOR 

* Pay special attention to functionalities that return user information or modify user data

## Step 3: Capture Requests

Browse through each application feature you mapped and capture all the requests going from your web client to the server

* Find parameters that contain numbers, usernames, or IDs

## Step 4: Change the IDs

Switch the IDs in the sensitive requests and check if the information returned also changes
