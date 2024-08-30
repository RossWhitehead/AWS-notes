## Policies
### Identity based policies
* Attached to a user, group or role.
* Manged policies
    * AWS Managed (common use cases), or Customer Managed
    * Can be attached to multiple identities.
* Inline policies
    * Embedded with the identity.
    * Deleted when identity is deleted.

### Resource based policies
* Attached to a resource.
* Not all AWS services support resource based policies. Typically used for S3, SQS, VPC endpoints, and KMS keys.
* Can be used for cross-account access.
