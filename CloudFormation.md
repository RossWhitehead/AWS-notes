# CloudFormation

## Templates

* Blueprints for building AWS resources.
* Templates specify:
    * Resources
        * With Type and Properties
        * Ref functions references related resources.
        * GetAttr references attributes of related resources.
    *  Parameters - for user input
    *  Mappings - conditional values
    *  Output Values

```yaml
AWSTemplateFormatVersion: 2010-09-09
Description: A sample template
Resources:
  MyEC2Instance:
    Type: 'AWS::EC2::Instance'
    Properties:
      ImageId: ami-0ff8a91507f77f867
      InstanceType: t2.micro
      KeyName: testkey
      BlockDeviceMappings:
        - DeviceName: /dev/sdm
          Ebs:
            VolumeType: io1
            Iops: 200
            DeleteOnTermination: false
            VolumeSize: 20
  MyEIP:
    Type: 'AWS::EC2::EIP'
    Properties:
      InstanceId: !Ref MyEC2Instance
```

## Stacks

* Unit of management for related resources.
* Resources in a stack are defined by the stack's CloudFormation template.

## Change Sets

![](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/images/update-stack-changesets-diagram.png)

* Change sets allow you to preview how proposed changes to a stack might impact your running resources.
