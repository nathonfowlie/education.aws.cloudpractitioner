# Identity & Access Management (IAM)

## Overview

- Users can be limited to programmatic access only, and/or the management console.
- Can copy permissions from an existing user, or attach existing policies.
- Users can be tagged.
- There's 3 ways to access AWS - management console (password + MFA), cli (access key), and sdk (access key).
- Users are mapped to a physical user (duh....)
- Groups can't be nested.
- Policy is a JSON  document outlining  permissions for users or groups.
- Roles permit AWS resources/services to access other resources/services.

## Best Practise

- Delete root access keys.
- Activate MFA.
- Create individual IAM users.
- Use groups to assign permissions.
- Set an IAM password policy.
- Follow the least privilege principle.

## Multi-factor Authentication (MFA)

- Should be enabled for all users.

### Supported MFA Devices

- Virtual MFA (Google Authenticator, Authy)
- U2F Security Key (Yubikey)
- Hardware Key Fob (Gemalto)
- Hardware Key Fob for GovCloud (SurePassID)

## AWS CloudShell

- Cloud based CLI that can be used in lieu of the AWS CLI on your local machine.
- Uses the same credentials as the logged in user.

## IAM Roles

Common roles are EC2 instance roles, Lambda function roles, and CloudFormation roles.

## IAM Security Tools

- **IAM Credentials Report (account level)** - List all users in an account and their various credentials..
- **IAM Access Adviser (user level)** - Service permissions granted to a user and when the services were last accessed.

## Shared Responsibility Model

There's a shared responsibility model for identity management on AWS -

**AWS** is responsible for -

- Infrastructure (global network security).
- Configuration & vulnerability analysis.
- Compliance validation.

**Customers** are responsible for -

- Users, Groups, Roles, Policies management & monitoring.
- Enabling MFA on all accounts.
- Rotating keys.
- Using IAM tools to apply appropriate permissions.
- Analyze access patterns and review permissions.

