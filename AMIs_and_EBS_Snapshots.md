# AMIs and EBS Snapshots
## Create AMI from EBS-backed Instance
* Select instance, Actions -> Image and templates -> Create image 
## Create AMI from EBS Snapshot
* Select snapshot, Actions -> Create image
* Unlike "Create AMI from EBS-backed Instence" can choose the instance architecture.
## EBS Snapshots
* Incremental snapshots
* Stored in S3
### Lifecycle Manager
* Data Lifecycle Manager enables you to automate the creation, retention, copy and deletion of EBS snapshots and EBS-backed AMIs. It also enables you to automate cross-account snapshot copy actions for snapshots that are shared with you, based on Amazon CloudWatch events.
### Encryption
* Snapshots of encrypted volumes are automatocally encrypted.
* Volumes created from encrypted snapshpts are automatically encrypted.
* Volumes created from unencrypted snapshots can be encrypted during creation.
* When copying an unencrypted snapshot, it can be encrypted during the copy.
* An encrypted snapshot can be re-encrypted with a different key.

