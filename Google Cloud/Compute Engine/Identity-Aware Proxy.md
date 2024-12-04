# IAP Overview

* Allows you to use an application-level access control model (*Group-based application access*, *etc.*) instead of relying on network-level firewalls by letting you establish a central authorization layer for applications accessed by HTTPS (Ex: *A resource could be accessible for employees and inaccessible for contractors*, *etc.*)
* Used when you want to enforce access control policies for applications and resources
* Works with [signed headers](https://cloud.google.com/iap/docs/signed-headers-howto) or the App Engine standard environment [Users API](https://cloud.google.com/appengine/docs/standard/services/users) to secure your app

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# How IAP Works

## Compute Engine

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/gfonovjvjjsdfdkfndsofkndafklnadsfnlkafndsaf.png)

## GKE

## Cloud Run

## App Engine

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IAP Processes 

## Authentication

* If IAP is enabled, information about the protected resource (*Project number*, *Request URL*, *Any IAP credentials in the request headers or cookies*, *etc.*) is sent to the IAP authentication server
* IAP will then check the user's browser credentials (If none exist, the user is redirected to an OAuth 2.0 Google Account sign-in flow that stores a token in a browser cookie for future sign-ins)
* If the request credentials are valied, the authentication server uses those credentials to get the user's identity (email address and user ID) and then uses it to check the user's IAM role and check if the user is authorized to access the resource (If you're using GCE or GKE, users who can access the application-serving port of the VM can bypass IAP authentication)
* GCE and GKE firewall rules can't protect against access from code running on the same VM as the IAP-secured application

## Authorization
