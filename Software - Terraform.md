Terraform is an infrastructure as code tool that enables you to safely and predictably provision and manage infrastructure in any cloud

* Platform-agnostic, meaning that it can be used with multiple cloud and on-premises providers
* Provides high-level abstraction, meaning that it can be used to manage resources across multiple providers
* Provides a modular approach, meaning that you can create modules grouping multiple resources and then combine and compose those modules to build a bigger solution
* Provides parallel deployment, meaning that it can build a dependency graph of resources (What resources depends on what) and supports parallel changes
* Provides separation of the plan and apply stages, meaning that you can execute only plan commands to inspect the potential changes before actually applying them
* Provides several ways to protect resources against accidental changes or deletion, as well as ways of validating the deployed infrastructure
* Very fast dur to its implementation of a state file to bind local resources or configuration resources to remote real world objects

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform's Architecture

## Terraform Core

The Terraform Core is the central component of Terraform's architecture that's responsible for managing the entire lifecycle of infrastructure resources

## Provider

* Allows the Terraform Core to know how to interact with remote APIs
* Provides the logic to interact with the upstream APIs in order to read, create, update, and delete resources through that provider's API, meaning that Terraform doesn't need to implement all the logic to ineteract with all the remote APIs that it supports because all that can be implemented through plugins via providers
* Anyone can write and publish a provider for a remote API, as long as it follows Terraform's specifications
* We declare the necessary providers in the Terraform project configuration and then Terraform will install those providers during initialization

## Remote APIs

## Terraform Registry

The Terraform Registry is a public repository where users can discover, share, and use Terraform modules and providers

* Acts as a centralized location for reusable public infrastructure code

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Provisioning Infrastructure

| Provisioning Infrastructure Phase | Description |
| --- | --- |
| Phase 1: Plan Phase | |
| Phase 2: 
