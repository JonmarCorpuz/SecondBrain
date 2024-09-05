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
* You can't have two different versions of the same provider installed side by side in the same project

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

* Executes until there are no more changes to be applied

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

# Terraform Input Variables

* Allows you to create reusable and composable code
* Allows you to customize aspects of Terraform configurations and modules without having to alter the source code

## Terraform Variable Precedence

* Configuration overrides happen at the variable level and not the file level
* Processes files in lexical order whenever there are multiple files on the same level of precedence

| Terraform Input Variable Precendence Order | 
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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Modules

* Seen as a collection of .tf files that are kept in the same directory
* Allows you to group related parts of your infrastructure to make the code easier to understand and improve maintainability (Organize configuration)
* Allows you to encapsulate sets of resources to prevent unintended changes and mistakes that can happen in complex code bases (Encapsulate configuration)
* Allows you to reuse entire sets of components, allowing you to improve consistency, save time, and prevent errors (Re-use configuration)
* Published modules support versioning, automatically generate documentation, allow browsing version histories, show examples and READMEs, etc.

| Terraform Module Type | Description |
| --- | --- |
| Root Module | The set of files in the main working directory |
| Child Module | A local module that's called by the root module |
| Published Module | A remote module from either a public or private registry that's called by the root module |

## Standard Terraform Module Structure

```Bash
$ tree complete-module/
.
├── LICENSE
├── README.md
├── main.tf
├── variables.tf
├── outputs.tf
├── ...
├── modules/
│   ├── nestedA/
│   │   ├── README.md
│   │   ├── variables.tf
│   │   ├── main.tf
│   │   ├── outputs.tf
│   ├── nestedB/
│   ├── .../
├── examples/
│   ├── exampleA/
│   │   ├── main.tf
│   ├── exampleB/
│   ├── .../
```

| Standard Terraform Module Structure File | Description |
| --- | --- |
| LICENSE | Specifies how the module can be used by others |
| README.md | Contains documentation for the module |
| main.tf | The main entry point for module resources |
| variables.tf | Contains all variables for the module |
| outputs.tf | Contains all outputs from the module |

## Terraform Module Best Practices

* Build modules when useful abstraction of our infrastructure can be identified
* Build modules when certain groups of resources always need to be created together and strongly depend on each other
* Build modules when hiding the infrastructure details of a certain part of your infrastructure will lead to better developer experience
* Use object attributes to group related information under object-typed variables to make it easier to work with your Terraform projects in the long term
* Seperate long-lived from short-lived infrastructure (Resources that change rarely shouldn't be grouped together with resources that change often)
* Modules should be only reusable blocks of your infrastructure
* Don't expose all the internals of the module for configuration via variables
* Output as much non-sensitive information as possible
* Define a stable input and output interface (Ensure that changing a variable name won't mess up your code's logic)
* Extensively document variables and outputs
* Favor a flat and composable module structure instead of deeply nested modules since they become harder to maintain over time and increase the configuration complexity for the module's users
* Thoroughly validate the infrastructure created by your module and don't rely on the users to always pass valid input values
* Make your dependencies explicit by requiring the information via input variables
* Keep a module's scrope narrow (Don't try to do everything inside a single module)

## Public Terraform Module Conditions

* The module must be on Github and must be a public repo (Required only for public registries)
* Repositories must use the following naming format: terraform-<provider>-<name>, where <provider> is the provider where resources are created and <name> is the type of infrastructure managed by the module
* The module repository must have a simple one sentence descripiton
* The module should adhere to the standard module structure (Ex: *main.tf*, *outputs.tf*, *variables.tf*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Object Validations

## Preconditions

* Used from within resources and data blocks
* Can't reference the resource itself
* Can be used to check the validity of data blocks or variables that the resource is referencing (Ex: *Invalid IP address syntax, *etc.*)
* Doesn't validate resources that aren't known to Terraform during the plan phase (Some information is only known to Terraform during the apply phase)
* Terraform will exit without going into the apply phase if it detects an issue

## Postconditions

* Used from within resources and data blocks
* Can reference the resource itself
* Can be used to check the validity of the resource's configuration
* Validation is deferred until the apply phase and will interrupt the creation of resources if it detects an error but it won't automatically destroy the resources that it created before the interruption

## Check Assertions

* Used from outside resources and data blocks
* Can reference information from across the current Terraform project
* Results only in a warning and doesn't stop the applying process

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# State Manipulation

## Tainting

* Forcing the recreation of a resource that's tracked by a Terraform configuration
* Can be used when a certain resource goes into an invalid state, but the configuration is correct and hasn't changed
* Tainting marks a resource for recreation (Applying a Terraform configuration will destroy the resource if it exists already and recreate a new one)

## Importing 

* Importing existing resources into a Terraform project, and start managing them with IaC

## Refactoring

* Renaming resources without recreating them, and then moving them inside and outside of modules whenever needed
* Prevents recreation due to changing resource addresses in Terraform

## Untracking

* Removing a resource from a Terraform configuration without actually destroying that resource
* Useful when we want to manage the resource independently of the Terraform project

## Generating Configuration

* Leveraging Terraform's code generation feature to generate a best-effort configuration based on existing resources
* Can be used when importing resources into Terraform

## Fine-Grained State File Changes

* Forcing state unlocking or pulling and pushing the state file from remote backends to perform careful, fine-grained editing in case something is wrong with it

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Workspaces

* Uses a single code-base for different environments
* Allows us to leverage the same configuration directory to create different environments in order to reduce code duplication and avoid installing multiple copies of modules and providers
* Resources from other workspaces aren't considered when using the CLI in a workspace
* Different workspaces correspond to different state data (Terraform stores them in different .tfstate files)
* Terraform always has a default workspace that gets created when you intialize a Terraform project without specifying a workspace
* Not every backend supports workspaces
* Shouldn't be used in Terraform configuration files to make conditional decisions 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Terraform Cloud

* Allows us to execute and manage Terraform code in a secure remote environment instead of locally
* Provides access control to approving infrastructure changes
* Supports secure state and secret storage
* Provides private registries for sharing modules within an organization
* Provides policy controls for managing the contents of Terraform projects
* Allows you to check the run history of terraform plan and apply commands
* Resources are organized into workspaces, which can be then organized into projects

| Terraform Component | Local Terraform | Terraform Cloud |
| --- | --- | --- |
| Configuration | Saved on disk | Saved in a VCS repository and can be called via API or commands from the CLI |
| State File | Saved locally or by using a remote backend | Saved in a Terraform Cloud workspace |
| Secrets | Passed via environment variables or through the prompt | Saved in a Terraform Cloud workspace |

## Terraform Cloud Workspaces

* A required component of Terraform Cloud projects
* Can be linked to branches of VCS repositories and you can also specify which files and directories within the VCS repository that you want to plan and apply
* You can create workspace variables to store data (Ex: *Access keys for remote authentication*, *etc.*)
* Terraform Cloud keeps track of the state for each of the runs that were triggered

| Terraform Cloud Workspace Workflow | Description |
| --- | --- |
| Version Control Workflow | Trigger runs based on changes to configuration in remote repositories (Ex: *Github repositories*, *etc.*) |
| CLI-Driven Workflow | Trigger runs in a workspace using the Terraform CLI |
| API-Driven Workflow | Trigger runs using the Terraform Cloud API |
