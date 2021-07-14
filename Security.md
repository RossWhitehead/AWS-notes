# Security

## Root User

### Securing
* Activate MFA for root user.
* Delete root user access keys.
* Create IAM users for administrators.
    * Create Administrators groups.
    * Attach AdministratorAccess policy to the group.
    * Assign users to the group.
* Limit root user actions with SCPs (Service Control Policies).
* Apply a secure IAM password policy.

### Actions that only a root user can do
* Change account settings (account name, email, root password).
* Change AWS support plan.
* View certain tax invoices.
* Restore IAM user permissions.
* Register as a seller in RI marketplace.
* Create CloudFront key pair.
* Configure S3 bucket with MFA delete.
* Resolve S3 bucket policy with invalid VPC ID or VPC endpoint ID.
* Sign up for GovCloud.
* Close AWS account.

## Service Control Policies (SCP)
* Central control over available permissions for all accounts in an organisation.
* Default policy is FullAWSAccess.
* Policies can be attached to individual accounts.
* Applies to all users in an account, including the root user.

## Permissions Boundary
* Limits effective permisions of roles and users
* 





