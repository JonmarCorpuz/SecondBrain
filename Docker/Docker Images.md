# Docker Image Overview

A Docker image is a self-contained and read-only template that encapsulates everything needed to run your application

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Docker Image Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-09%20102840.png)

## Base Image

A [base image](https://docs.docker.com/build/building/base-images/#:~:text=A%20base%20is%20the%20image,FROM%20instruction%20in%20the%20Dockerfile.&text=For%20most%20cases%2C%20you%20don,base%20image%20in%20your%20build.) is the image that your image extends

* Refers to the contents of the `FROM` instruction in the Dockerfile

## Runtime Environment

The [runtime environment](https://www.techopedia.com/definition/5466/runtime-environment-rte) is the environment in which a program or application is executed (Ex: *Python*, *Node.js*, *etc.*)

## Libraries and Dependencies

The libraries and dependcies refers to all external code that your application relies on

## Application Code

The application code is your own source code or binaries

## Configuration

The configuration refers to the configurations for your application and its environment
