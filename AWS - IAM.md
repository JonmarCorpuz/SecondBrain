AWS Identity and Access Management is a web service provided by AWS that enables users to securely control access to AWS services and resources

* Allows organizations to create and manage users, groups, roles, and permissions within their AWS environment
* Provides granular control over access to AWS resources by attaching policies, which are defined permissions that specify what actions are allowed or denied on which resources, to users, groups, roles, or AWS resources
* Allows organizations to use identities from external IdPs
* Logs API calls made to the service, providing a detailed audit trail of actions taken by users, groups, and roles within the AWS environment
* Manages the login credentials and permissions to an AWS account and the permissions used to sign API calls made to AWS services
* Provides a centralized view of who and what are allowed inside your AWS account (Authentication), as well as who and what have permissions to use and work with your AWS account (Authorization)
* Isn't used for website authentication and authorization

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IAM Components

## IAM User

An IAM user is an entity that represents a person or an application within an AWS environment

* Any activity done by a user is billed to the IAM user account that they used to perform that activity
* IAM users have associated credentials that are used to sign AWS API call requests (Ex: *Username*, *Password*, *Access key ID*, *Secret access key*, *etc.*)

## IAM Group

An IAM group is a collection of IAM users

* Allows users to manage permissions and policies for multiple users collectively rather than individually
* All IAM users in a group inherit the permissions that was assigned to it
* Can only contain IAM users

## IAM Role

An IAM Role is an identity that can be temporarily assumed by an entity or service wanting access to another AWS account or service

* Defines a set of permissions and policies that determine what actions can be performed on AWS resources
* Roles aren't associated with a specific user or group but can be assumed by many different IAM users, AWS services, or even by trusted entities outside of AWS 
* Used to grant permissions dynamically rather than attaching policies directly to IAM users
* Easier to maintain compared to IAM users since the temporary credentials for IAM roles expire after a defined period of time, meanwhile IAM users have long-term credentials in the form of username and password combinations or a set of access keys that only expire when the admin of that account rotates those keys

## IAM Policy

An IAM Policy is a JSON document that defines the permissions granted to IAM users, IAM groups, or IAM roles

* Enables precise and secure control over how AWS resources are accessed and used by specifying which actions are allowed or denied on which AWS resources
* Can be attached to users, groups, roles, or directly to AWS resources
* Applies an explicit deny rule, meaning that if any policy explicitly denies an action, the action is denied, even if other policies allow it
* Helps users keep track of any changes made to policies and ensure roll back if needed by supporting versioning

### Managed IAM Policies

Managed IAM policies are standalone policies that can be attached to multiple IAM users, IAM groups, or IAM roles

* Can be either AWS managed, which are predefined policies by AWS, or customer managed, which are policies created and managed by the user

### Inline IAM Policies

Inline IAM policies are policies that users create and manage that are directly embedded into a single IAM user, IAM group, or IAM role

* Useful to ensure that the policy is strictly tied to a specific entity and when a one-to-one relationship between a policy and an entity is desired

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IAM Features

## IAM Authentication

IAM Authentication refers to the process of verifying the identity of users, services, or applications attempting to access resources within an AWS environment using AWS IAM

* Ensures that only authorized entities can access AWS resources

## IAM Authorization

IAM Authorization refers to the process of determining whether an authenticated entity is permitted to perform specific actions on AWS resources based on the permissions granted to them

* Ensures security by enforcing access control policies and restricting unauthorized access to AWS resources
* Can be attached to AWS users, except the root user, and AWS groups, where the AWS users in that group would inherit the permissions
* Applied using IAM policies, which are JSON-based documents containing the following elements:

	```JSON
	{
	"Version": "Policy language version"
		"Statement":[{
			"Effect":"Allow or Deny",
			"Action":"API call",
			"Resource":<Amazon Resources that the actions are allowed to be performed against>
			"Conditions":{
				<Conditions to further restrict access>
			} 
		}]
	}
	```
	* Version: Defines the version of the policy language, which specifies the language syntax rules that are needed by AWS to process a policy
	* Effect: Specifies whether the statement will allow or deny access
	* Action: Specifies the action that will be allowed or denied
	* Resource: Specifies the object or objects that the policy statement covers

## AWS IAM Identity Center

AWS IAM Identity Center is an IdP that lets users sign in to a user portal with a single set of credentials

* Provides users access to all their assigned accounts and applications in one central location
* Enables you to sync your users and groups from thirds-party IdP to AWS IAM Identity Center
* Separates the duties between your IdP and AWS, ensuring that your cloud access management isn't inside or dependent on your IdP

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Access Advisor

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)


