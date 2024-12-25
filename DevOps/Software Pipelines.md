# Software Pipeline Overview

A software pipeline is a process that uses automation and tools to facilitate movement through each phase of the software development lifecycle

* Helps developers release changes quickly
* Allows developers to modify an application's code without disturbing other parts of the project
* Everything from the build process to validation tests should be automated

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CI/CD Pipeline

Continuous Integration and Continuous Delivery/Deployment is a process used to create software and automate updates

* Minimizes downtime and reduces interruptions caused by human errors
* The less the development team needs to manually touch the code, the less likely it is that unintentional errors will occur

## Continuous Integration

CI is the phase where developers continuously create and update code that's uploaded into a shared repository (Ex: *Uploading a code automatically triggers a validation process, builds an image, and then stores the code in a repository*)

## Continuous Delivery/Deployment

CD refers to the steady automatic release of software builds to a testing environment and then to a production environment in real time

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CI/CD Stages

## Source

* Developers compile their code into a shared repository

## Build 

* Developers implement edits to the source code in the shared repository, which triggers a build

## Test

* Automated security tests check the new build's integrity
* If any bugs are found in the source code, the pipeline stops the process until developers fix the problem

## Deploy

* The software gets deployed to end users within minutes
