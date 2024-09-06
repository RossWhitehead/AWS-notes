## Policies

During authorization, the AWS enforcement code uses values from the request context to check for matching policies and determine whether to allow or deny the request. 

### Evaluation Logic

The evaluation logic for a request follows these rules:

* By default, all requests are implicitly denied. (Alternatively, by default, the AWS account root user has full access.)
* An explicit allow in an identity-based or resource-based policy overrides this default.
* If a permissions boundary, Organizations SCP, or session policy is present, it might override the allow with an implicit deny.
* An explicit deny in any policy overrides any allows.

### Identity based policies
Attached to a user, group or role.

* Managed policies
    * AWS Managed (common use cases), or Customer Managed
    * Can be attached to multiple identities.
* Inline policies
    * Embedded with the identity.
    * Deleted when identity is deleted.

### Resource based policies
Attached to a resource.

* Not all AWS services support resource based policies. Typically used for S3, SQS, VPC endpoints, and KMS keys.
* Can be used for cross-account access.

### Permission boundaries

You can use permissions boundaries to delegate permissions management tasks, such as user creation, to IAM users in your account.


### Organisation Service Control Policies (SCPs)

### Policy Simulator

Policy Simulator tool enables testing access for principles based on their assigned policies and permission boundaries.

### Example policies

#### AdministratorAccess

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}
```

#### AmazonS3ReadOnlyAccess

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:Get*",
                "s3:List*",
                "s3:Describe*",
                "s3-object-lambda:Get*",
                "s3-object-lambda:List*"
            ],
            "Resource": "*",
            "Condition": {
                "StringEquals": {
                    "aws:RequestedRegion": "eu-central-1"
                }
            }
        }
    ]
}
```


