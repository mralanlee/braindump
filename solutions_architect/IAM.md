# IAM - Identity Access Management

Allows you manage users and their level of access to the AWS Console. 

* Centralized control of AWS account
* Shared access to AWS account
* Permissions
* Identity Federation (active directory, Facebook, LinkedIn)
* MFA
* Temporary access for users/devices and services
* Password rotation policy
* Integrates with different AWS services
* Supports PCI DSS Compliance

## Definitions
* Users - End Users (people)
* Groups - collection of users under one set of permissions.
* Roles - Create roles, assign them to AWS resources (without username password auth)
* Policies - Document that defines one or more permissions

New Users are assigned Access Key ID & Secret Access Key, when first created. This is for APIs or Command Line.

Power User Access allows access to all AWS services except for management of groups and users within IAM.
