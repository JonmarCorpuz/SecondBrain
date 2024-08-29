Terraform is an infrastructure as code tool that enables you to safely and predictably provision and manage infrastructure in any cloud

* **Platform-agnostic**, meaning that it can be used with multiple cloud and on-premises providers
* Provides high-level abstraction, meaning that it can be used to manage resources across multiple providers
* Provides a modular approach, meaning that you can create modules grouping multiple resources and then combine and compose those modules to build a bigger solution
* Provides parallel deployment, meaning that it can build a dependency graph of resources (What resources depends on what) and supports parallel changes
* Provides separation of the plan and apply stages, meaning that you can execute only plan commands to inspect the potential changes before actually applying them
* Provides several ways to protect resources against accidental changes or deletion, as well as ways of validating the deployed infrastructure
* Very fast dur to its implementation of a state file to bind local resources or configuration resources to remote real world objects
* Automatically identifies the dependencies and follows the necessary order to create the specified resources

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform's Architecture

## Terraform Core

The Terraform Core is the central component of Terraform's architecture that's responsible for managing the entire lifecycle of infrastructure resources

## Provider

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/vgbihgihjivucvcicicicuxfgufgyfgyhgfhfghfghgfh.png)

* Allows the Terraform Core to know how to interact with remote APIs
* Provides the logic to interact with the upstream APIs in order to read, create, update, and delete resources through that provider's API, meaning that Terraform doesn't need to implement all the logic to ineteract with all the remote APIs that it supports because all that can be implemented through plugins via providers
* Anyone can write and publish a provider for a remote API, as long as it follows Terraform's specifications
* We declare the necessary providers in the Terraform project configuration and then Terraform will install those providers during initialization

## Remote APIs

A remote API is an interface provided by Terraform that allows users to interact with Terraform configurations and state files over the network

* Facilitates various operations that can be performed remotely

## Terraform Registry

The Terraform Registry is a public repository where users can discover, share, and use Terraform modules and providers

* Acts as a centralized location for reusable public infrastructure code

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Workflow

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/qjkhjdkhqdkhqkdhjqkdjkqjdkjqkdjkqdjkqjdkqjdkqjdkjqd.png)

| Provisioning Infrastructure Phase | Description |
| --- | --- |
| Step 1: Terraform Initialize | |
| Step 2: Plan Phase | |
| Step 3: Apply Phase | |
| Step 4: Destroy Phase | |

## Terraform Initialize

Initializing Terraform prepares a working directory for use with Terraform 

* Downloads and installs the necessary providers that are specified in the file that contains your Terraform configuration
* Ensures that the correct versions of the installed providers are locked in the .terraform.lock.hcl file
* Terraform initialization needs to be done everytime you add a provider or change a version in your Terraform configuration so that it can update the lock file and the installed provider

### .terraform.lock.hcl 

The .terraform.lock.hcl file is a dependency lock file that Terraform generates automatically when you run `terraform init`

* Locks the exact versions of providers and modules used in your Terraform configuration to ensure that Terraform applies the same versions across all environments
* Helps maintain consistent behavior and reproducibility of Terraform runs
* Helps track changes to dependencies
* Contains hashes for multiple platforms to allow it to be used in different OS environments

### .terraform

The .terraform folder contains all the data necessary to execute Terraform configurations

* Specific to each user's environment and contains potentially sensitive data and binary files that aren't suitable for version control systems
* Stores the provider plugins that Terraform needs to manage the resources specified in your configurations
* Downloads and stores any modules to allow Terraform to reuse them without needing to re-download them for every operation
* May include a plugins directory which includes the necessary lock information that details the specific versions and configurations of the plugins being used 

## Plan Phase 

## Apply Phase

## Destroy Phase
