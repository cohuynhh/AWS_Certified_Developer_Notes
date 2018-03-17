#Overview

## Some important aspects *(not in the exam)*

- Centralised control of your AWS account
- Shared access to your AWS account
- Granular permissions
- Identity Federation (Active Directory, Facebook, LinkedIn)
- Multifactor Auth
- Temporary access to users/devices
- Own root password
- Integrates multiple AWS services
- Supports PCI DSS compliance

## Critical terms *

- Users - Groups - Roles - Policies(Policy documents)

- Policies are in top, could be assigned to any of them.

============================================

## Some important aspects

- IAM does not have region

- New users have NO permissions

- Access key ID and Secret are to access services, NOT TO LOGIN.

- Activate MFA (Always)

- Virtual | hardware

- Users access type could: programmatic/console

- You can give permissions into a group for a specific user, special permissions.

- Roles could be used for IAM user in another account. (EC2 instance good sample)


=============================================

## STS Security Token service

### Sources
  - Federation (Active Directory)
  - Mobile Apps (OpenID, Google, Fb)
  - AWs from other services

### Key terms
  - Federation: combining/joining list of users from one service to another
  - Identity broker: take an identity from point A to point B, you need to implement it
  - Identity store: Service like AD, fb, Google.
  - Identities: user of a service, Fb.

## Scenarios

### First Scenario

#### Flow
  Employee User/Pwd => Call identity broker => LDAP Directory => IAM Fed Token
  => Give tokens => IB returns credentials => Requests

### IMPORTANT FOR EXAM
  - Develop an IB to communicate with LDAP and AWS STS
  - IB always authenticates with LDAP first, then with AWS STS
  - Application then gets temporary access to AWS resources

### Second scenario (Role)

The same as first scenario, but in this time the application will use IAM role to interact with S3.
=============================================

## Active Directory Federation

### IMPORTANT FOR EXAM
  * Can you authenticate with AD?
  *   Yes, with SAML.
  * You first need to be authenticated on AD then the temporary credential is assigned.

=============================================

### IMPORTANT FOR EXAM

- First authenticate with id provider
- Get tokens
- Call assumerolewithwebidentity
