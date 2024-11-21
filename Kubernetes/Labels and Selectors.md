# Labels Overview

Labels are key-value pairs that are attached to Kubernetes objects to specify identifying attributes of objects that are meaningful and relevant to users, but don't directly imply semantics to the core system

* Enables users to map their own organizational structures onto system objects in a loosely coupled fashion, without requiring clients to store these mappings
* Can be attached to objects at creation time and subsequently added and modified at any time
* Each object can have a set of key-value labels defined
* Allows for efficient queries and watches
* Don't provide uniqueness (Expect many objects to carry the same labels)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Labels Syntax

* Valid label keys have two segments: an optional prefix and a name, separated by a slash

## Name Segment

* The name segment is required
* Must be 63 characters or less
* Must begin and end with an alphanumeric character (`[a-z0-9A-Z]`)
* Can have dashes (`-`), underscores (`_`), and dots (`.`) between alphanumerics

## Prefix

* The prefix is optional
* If specified, the prefix must be a DNS subdomain
* Can't be longer than 253 characters in total, followed by a slash (`/`)
* If the prefix is omitted, the label Key is presumed to be private to the user
* Automated system components (*kube-scheduler*, *kube-controller-manager*, *kube-apiserver*, *kubectl*, or other third-party automation) that add labels to end-user object must specify a prefix

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# labelSelector

The labelSelector API is used by users to select a set of objects

* Can be made of multiple requirements that must all be satisfied
* For some API types, the labelSelector of two instances must not overlap within a namespace
* Supports two types of selectors: equality-based and set-based

## Equality-Based Requirement

## Set-Based Requirement
