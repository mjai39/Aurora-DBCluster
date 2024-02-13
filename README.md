# Aurora-DB Cluster Deployment with CFN Template
Amazon Aurora Global cluster

## Instructions (Individual Stacks)
This creates a VPC with two public subnets and two private subnets in two Availability Zones, 
together with a NAT Gateway and associated routing. Change the Availability Zone locations as needed.
 
1. Create a VPC,Public Subnets,Private Subnets,Nat Gateway,IGW on both the regions.
      - aws cloudformation --region us-west-2 create-stack --stack-name vpc-west --template-body file://vpc-west.yaml
      - aws cloudformation --region us-east-2 create-stack --stack-name vpc-east --template-body file://vpc-east.yaml
2. Create a DB Cluster,EC2 Instance,Security Group with rds-stack.yaml.
      - aws cloudformation --region us-west-2 create-stack --stack-name rds-west --template-body file://rds-stack.yaml --parameters ParameterKey=MasterUserPassword,ParameterValue=***** --capabilities CAPABILITY_NAMED_IAM
      - aws cloudformation --region us-east-2 create-stack --stack-name rds-east --template-body file://rds-stack.yaml --parameters ParameterKey=MasterUserPassword,ParameterValue=***** --capabilities CAPABILITY_NAMED_IAM

## System Design

![alt text](https://github.com/mjai39/Aurora-DBCluster/blob/main/DBDisaster.jpeg?raw=true)
