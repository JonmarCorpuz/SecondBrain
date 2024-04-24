AWS Identity and Access Management is a web service provided by AWS that enables users to securely control access to AWS services and resources

* Allows organizations to create and manage users, groups, roles, and permissions within their AWS environment
* Provides granular control over access to AWS resources by attaching policies, which are defined permissions that specify what actions are allowed or denied on which resources, to users, groups, roles, or AWS resources
* Supports MFA
* Allows organizations to use identities from external IdPs
* Controls access to AWS services (Ex: *Amazon S3*, *Amazon EC2*, *Amazon RDS*, Amazon DynamoDB*, *etc.*)
* Provides an Access Advisor feature, which shows the services and resources that each user or role has accessed and the actions performed within the last 90 days, helping to identify unused permissions and enforce least privilege access
* Logs API calls made to the service, providing a detailed audit trail of actions taken by users, groups, and roles within the AWS environment

* Manages the login credentials and permissions to an AWS account and the permissions used to sign API calls made to AWS services
* Not responsible for application level access management
* Allows you to create AWS IAM users that other users can access with their own AWS IAM user
* Provides a centralized view of who and what are allowed inside your AWS account (Authentication), as well as who and what have permissions to use and work with your AWS account (Authorization)
* Allows you to share access to an AWS account and resources without having to share your set of access keys or password, as well as share granular access to those working in your account, so that people and services only have permissions to the resources they need
* Global and not specific to any one Region
* Integrated with many AWS services by default
* Supports MFA and identity federation (The process of linking)
* Isn't used for website authentication and authorization
* Doesn't support controls for protecting operating systems and networks

# IAM Concepts

## IAM User

An IAM User is a person or service that interacts with AWS

* An IAM user is defined with the user within your AWS account, and any activity done by that user is billed to your account
* Once that IAM user is created, that user can now sign in to gain access to the AWS resources inside your account
* IAM users have associated credentials, which include an access key ID and a secret access key, that are used to sign AWS API call requests
## IAM Group

An IAM Group logical container of users with similar permissions

* Instead of attaching policies directly to individual users, you can create IAM groups, assign policies to those groups, and then add users to the groups
* All users in the group inherit the permissions assigned to the group
* Groups can have many users
* Users can belong to many groups
* Groups cannot belong to groups

## IAM Role

An IAM Role is an identity that has associated AWS credentials that can be temporarily assumed by an entity or service wanting access to another AWS account or service

* Defines a set of permissions and policies that determine what actions can be performed on AWS resources
* Doesn't have any login credentials
* IAM Roles are assumed programmatically, temporary, and automatically rotated, meaning that the credentials they offer expire
* Roles aren't associated with a specific user or group but can be assumed by many different IAM users, AWS services, or even by trusted entities outside of AWS 
* Used to grant permissions dynamically rather than attaching policies directly to IAM users
* Provides a more flexible and secure way to control access to AWS resources
* Often used in scenarios where temporary and secure access is required 
* Easier to maintain compared to IAM users since the temporary credentials for IAM roles expire after a defined period of time, meanwhile IAM users have long-term credentials in the form of username and password combinations or a set of access keys that only expire when the admin of that account rotates those keys

## IAM Policy

An IAM Policy is a JSON document that defines the permissions granted to users, groups, or roles

* Specifies which actions are allowed or denied on which AWS resources
* Can be attached to users, groups, roles, or directly to AWS resources

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

# AWS IAM Identity Center

AWS IAM Identity Center is an IdP that lets users sign in to a user portal with a single set of credentials

* Provides users access to all their assigned accounts and applications in one central location
* Enables you to sync your users and groups from thirds-party IdP to AWS IAM Identity Center
* Separates the duties between your IdP and AWS, ensuring that your cloud access management isn't inside or dependent on your IdP

# Multi-Account Strategies

* 
