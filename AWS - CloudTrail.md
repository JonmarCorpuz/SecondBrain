CloudTrail enables operational and risk auditing, governance, and compliance over an AWS account

* Every action taken by a user, role, or service are recorded as events
* Automatically active when an AWS account when it gets created

# CloudTrail Features

## Event History

The Event history is a feature that provides visibility into an AWS account's activity by recording AWS Management Console actions and API calls that were made

* Provides a viewable, searchable, downloadable, and immutable record of the last 90 days of activity in an AWS Region
* Allows users to search events by filtering on a single attribute
* Each event listed in the history includes detailed information and the response elements returned by the AWS service

## CloudTrail Lake

CloudTrail Lake provides a managed audit and security lake

* Allows users to run SQL-based queries on their events
* Converts existing events in row-based JSOn format to Apache ORC format, which is a columnar storage format that's optimized for fast retrieval of data

## Trails

A trail is a set of rules that defines how CloudTrail captures, manages, and stores information about events in an AWS account

### Organization Trails

An organization trail is a feature that enables the management of audit logging for all AWS accounts within an AWS Organization

* Provides a centralized way to collect and manage event logs across mutliple accounts by enabling users to create a single trail that applies to all the accounts in the organization
* Organization trails are automatically applied to all member accounts in an organization
* Ensures that compliance and governance standards are uniformely enforced across all accounts
* Supports the scalability of governance, compliance, and risk management processes as the organization grows
