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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Container Registries

* Allows you to do versioning to help you keep track of different versions of your images for easy rollback and updates
* Allows you to collaborate with other people by sharing them your images
* Provides a secure environment for storing sensitive images
* Allows you to automate image building and deployment as part of your CI/CD pipeline

## Public Registries

Public registries (*[Docker Hub](https://hub.docker.com/)* are open to everyone and host a vast collection of images from various sources

## Private Registries 

Private registries are used for storing proprietary or sensitive images and offer granular access control

## Self-Hosted Regristries

## Cloud-Hosted Registries

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Distroless Docker Images

A distroless image is a minimal Docker image that contains only the necessary runtime dependencies of applications

* Provides enhanced security since there are fewer components (*OS*, *Shell utilities*, *etc.*) in the image, meaning that there are fewer potential vulnerabilities and a smaller attack surface
* Has a reduced image size, which allows for faster image pulls and reduced storage requirements
* Improved performance (*Quicker startup times*, *Lower resource consumption*) since it's smaller and has fewer components
* Easier to audit and verify
* Harder to troubleshoot since there are no shell utilities or debugging tools
* Managing dependencies is more complex, as you need to ensure all required libraries and binaries are included in the build process
* Increases build complexity since creating distroless images often involves more complex Dockerfiles and build processes
