# Aurora-DBCluster
Amazon Aurora Global cluster


### This creates a VPC with two public subnets and two private subnets in two Availability Zones, 
### together with a NAT Gateway and associated routing. Change the Availability Zone locations as needed.
 
## Usage from the command line:

###   aws cloudformation --region us-west-2 create-stack --stack-name vpc-west --template-body file://vpc-west.yaml

###   aws cloudformation --region us-east-2 create-stack --stack-name vpc-east --template-body file://vpc-east.yaml

## Create Amazon Aurora RDS stack with global cluster:
###   aws cloudformation --region us-west-2 create-stack --stack-name rds-west --template-body file://rds-stack.yaml --parameters ParameterKey=MasterUserPassword,ParameterValue=*****

###   aws cloudformation --region us-east-2 create-stack --stack-name rds-east --template-body file://rds-stack.yaml --parameters ParameterKey=MasterUserPassword,ParameterValue=*****


