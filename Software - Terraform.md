Terraform is an infrastructure as code tool that enables you to safely and predictably provision and manage infrastructure in any cloud

* **Platform-agnostic**, meaning that it can be used with multiple cloud and on-premises providers
* Provides high-level abstraction, meaning that it can be used to manage resources across multiple providers
* Provides a modular approach, meaning that you can create modules grouping multiple resources and then combine and compose those modules to build a bigger solution
* Provides parallel deployment, meaning that it can build a dependency graph of resources (What resources depends on what) and supports parallel changes
* Very fast due to its implementation of a state file to bind local resource blocks to remote real world objects (Ex: *example_s3_bucket_resource_name -> AWS S3 Bucket*)
* Automatically identifies the dependencies and follows the necessary order to create the specified resources
* Only looks for files within the current directory and doesn't look through any subdirectories that the current directory has
* Supports both parallel and sequential management of resources (Inspects the expressions to automatically establish implicit dependencies between ressources)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform's Architecture

## Terraform Core

The Terraform Core is the central component of Terraform's architecture that's responsible for managing the entire lifecycle of infrastructure resources

## Provider

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/vgbihgihjivucvcicicicuxfgufgyfgyhgfhfghfghgfh.png)

* Allows the Terraform Core to know how to interact with remote APIs
* Provides a set of resource types and data sources that the Terraform core can use to call remote APIs
* Providers are developed and maintained separately from Terraform
* Anyone can write and publish a provider for a remote API, as long as it follows Terraform's specifications
* We declare the necessary providers in the Terraform project configuration and then Terraform will install those providers during initialization
* Provider configurations belong to the root module of a Terraform project, meaning that child modules will receive their provider configuration from the parent module

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

* Terraform will first refresh the state of all the resources in the Terraform configuration files to revert any resources that were modified outside of Terraform back to the state that are defined in the Terraform configration files

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Blocks

| Terraform Block | Description |
| --- | --- |
| Terraform Block | |
| Resource Block | |
| Data Block | |
| Variable Block | |
| Output Block | |
| Locals Block | |
| Module Block | |

## Terraform Block

| Terraform Block Block | Description |
| --- | --- |
| cloud | Configures Terraform Cloud |
| backend | Configures a state backend for the project (Can't use any input variables, resource references, and data sources) |
| required_version | Specifes the accepted versions of Terraform for the current project |
| require_providers | Specifies the required providers for the current project or module |

| Version Constraint | Description |
| --- | --- |
| `=` | Allows only the specified version |
| `!=` | Excludes an exact version |
| `>=`, `<=`, `>`, `<` | Allow versions for which the comparison is true |
| `~>` | Allows only the rightmost digit to increment |

* Used to configure the backend, providers, and required versions for your Terraform project
* Only constants are allowed (Input variables or resource references aren't allowed)

## Resource Block

* Used to configure and manage real-world infrastructure objects with Terraform (Ex: *Virtual networks*, *Compute instances*, *DNS records*, *Storage disks*, *etc.*)
* Arguments depend on and vary based on the resource type
* The combination of resource type and resource name must be unique within a module
* Offers a few local-only resources (Ex: *Generating random strings*, *Generating random IDs*, *Private keys*, *Self-Issued TLS certificates*, *etc.*)

## Data Block 

## Variable Block

## Output Block

## Locals Block 

## Module Block

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform State

Terraform State keeps track of the infrastructure managed by Terraform in order to map resources from the configuration to real-world resources, keep track of metadata (Ex: *Resource dependencies*, *etc.*), and improve performance for large infrastructures

* Stored in the **terraform.tfstate** local file by default or can be stored in a remote backend (Ex: *AWS S3*, *Google Cloud Storage*, *Terraform Cloud*, *etc.*)
* Always required in Terraform
* Can also contain the backend configuration and the outputs that are generated by your Terraform project, as well as other sensitive values
* Shouldn't be accessible to everyone since it contains sensitive data
* Keeping track of metadata allows Terraform to known which order resources must be created, updated, or deleted
* Before any planning operation, Terraform will refresh the state with the information from the respective real-world objects by looking into the state file and issuing a couple of API requests via the providers to get the latest state or the latest information related to those real-world objects
* If a real-world object has been modified outside of Terraform and the Terraform configuration for that resource hasn't been updated, Terraform will revert the changes to match the configuration file (If the retrieved information is different from what's in your resource configuration, Terraform will include changes in the plan so that the real world objects match the resource configuration)
* Provides **state locking**, meaning that Terraform will lock the state file while executing write operations to prevent concurrent modifications and state corruption

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Backends

A Terraform backend defines where Terraform stores its state file

* It's important to store this file properly in a place where you can properly control the access permissions
* A Terraform configuration can provide only one backend
* Uses the local backend by default, meaning that the state files will be recorded locally

| Backend Type | Description |
| --- | --- |
| Local | The state file is stored in the same machine as the Terraform project |
| Terraform Cloud | The state file is stored in Terraform Cloud project or workspace | 
| Third-Party | The state file is stored in a remote backend (Ex: *AWS S3*, *Google Cloud Storage*, *etc.*) |

## Local Backend

The state file is stored in the user's local machine

## Terraform Cloud Backend

The state file is stored in Terraform Cloud

## Third-Party Remote Backend

The state file is stored in a remote backend (Ex: *AWS S3*, *Google Cloud Storage*, *etc.*)

* State locking isn't available for all remote backends
* Not all backends require the same arguments
* Requires authentication credentials in order for Terraform to properly access the configuration files

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Meta-Arguments

Meta-arguments are special arguments that change the behavior of Terraform when parsing the declared module

* Allows you to configure Terraform's behavior when it comes to resources and data sources

| Resource Meta-Argument | Description |
| --- | --- |
| `depends_on` | Used to explicitly defines dependencies between resources |
| `count` | Used to define the number of instances of a specific resource that Terraform should create |
| `for_each` | Accepts a map or a set of strings and creates an instance for each entry in the received expression |
| `provider` | Used to explicitly define which provider to use with a specific resource |

| Lifecycle Meta-Argument | Description |
| --- | --- |
| `create_before_destroy` | Overrides Terraform's default behavior of destroying before creating resources the can't be updated in-place to make sure it creates the new resources and then delete the old one |
| `prevent_destroy` | Protects critical resources from being destroyed by having Terraform exit with an error if the planned changes would lead to the destruction of the resources marked with this |
| `replace_triggered_by` | Replaces the resource when any of the referenced items change |
| `ignore_changes` | Allows you to provide a list of attributes that shouldn't trigger an update when modified outside of Terraform |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Data Sources

* Allows you to query or retrieve data from external resources or projects using remote APIs and reference the retrieved information within your Terraform configuration
* Data sources are managed using data blocks in your Terraform configuration

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Variables

* Allows you to create reusable and composable code
* Allows you to customize aspects of Terraform configurations and modules without having to alter the source code

## Terraform Variable Precedence

* Configuration overrides happen at the variable level and not the file level
* Processes files in lexical order whenever there are multiple files on the same level of precedence

| Terraform Variable Precendence Order | 
| --- |
| 4. TF_VAR environmental variables |
| 3. terraform.tfvars |
| 2. *.auto.tfvars |
| 1. -var and -var-file CLI arguments |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Operators

| Operator Type | Operator Symbols | Return Value |
| --- | --- | --- |
| Math | `+`, `-`, `/`, `*` | Number |
| Equality | `=`, `==`, `!=` | Boolean |
| Comparison | `<`, `<=`, `>`, `>=` | Boolean |
| Logical | `&&` | Boolean |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Expressions

## Loop Expressions

| Loop Expression | Description |
| --- | --- |
| `for` | |

## Splat Expressions

* Only works with lists

| Splat Expression | Expression | Description |
| --- | --- | --- |
| Simple Splat | `[*]` | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Functions

| Terraform Function | Description |
| --- | --- |
