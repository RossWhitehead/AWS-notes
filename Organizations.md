# Organizations
![](https://d1.awsstatic.com/Diagram_AWS-Organizations_How-It_Works_v2.bfd7468ac7f8e008a15dcb6a8d0a26db743ea163.png)

## Create an organization
* Create an account, and log in as root user.
* Go to "My Organizations" click on "Create Organization".
* The current account will now be the root master account.

## Add member accounts
* Invite account
    * Root user of account must accept invitation.
* or, Create account.

## Compliance

### AWS Artifact
* Compliance info on demand

## Service Control Policies (SCP)
* Central control over available permissions for all accounts in an organisation.
* Default policy is FullAWSAccess.
* Policies can be attached to individual accounts.
* Applies to all users in an account, including the root user.

## AWS Cost Explorer
