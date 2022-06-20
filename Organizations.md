# Organizations
![](https://docs.aws.amazon.com/organizations/latest/userguide/images/AccountOuDiagram.png)

* Centralised management of accounts
* Consolidated billing
* Hierarchical grouping
* Service Control Polices (SCP) associated with accounts or OUs.
* Tag policies.
* AI services opt-out policies
* Backup policies
* Account level IAM policies

## Create an organization
* Create an account, and log in as root user.
* Go to "My Organizations" click on "Create Organization".
* The current account will now be the root master account.
* Invite account
    * Root user of account must accept invitation.
* or, Create account.
* Accounts can be grouped into a hierarchicy of OUs.

## Service Control Policies (SCPs)
* SCPs don't affect users or roles in the management account. They affect only the member accounts in your organization.
* SCP permission inheritance behaves like a filter from the root to the account. 
* A DENY higher up the hierarchy cannot be overriden by an ALLOW.
* For an ALLOW permission to be effective in an account, all parents (OUs, and root) in the accounts hierarchy must also have the ALLOW permission.
* Permission strategies:
    * Deny list strategy
        * FullAWSAccess SCP is attached by default to every OU and account. 
        * Attach an SCP that denies a specific service or set of actions.
        * Deny statements require less maintenance, because you don't need to update them when AWS adds new services. 
    * Allow list strategy
        * Remove the default FullAWSAccess SCP, thus all actions for all services are now implicitly denied. 
        * Attach an SCP that explicit allows actions and resources.
        * You must create allow SCPs and attach them to the account and every OU above it, up to and including the root.
* Examples:
    * Deny access to all actions/services outside of eu-west-1 and 2.
    * Require MFA for certain actions.
    * Require specific tags when creating resources.

## Tag Policies

* Maintain consistent tags across the organization.
* e.g. A tag policy can specify that when the CostCenter tag is attached to a resource
* A tag policy can also specify that noncompliant tagging operations on specified resource types are enforced. In other words, noncompliant tagging requests on specified resource types are prevented from completing.

## Consolidated Billing

* One bill for all member accounts combined.
* Can combine the usage across all accounts in the organization to share:
    * Volume pricing discounts (AWS Data Transfer and S3)
    * Reserved Instance discounts (all accounts can receive the hourly cost benefit of Reserved Instances that are purchased by any other account)
    * Savings Plans.

