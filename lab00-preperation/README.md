# TERRA 10 Fargate Labs

## Lab 000 - Prepared setup

## ECS - Create cluster

Navigate to ECS (Elastic Container Service), make sure to be in the “ireland” region. That’s where the party is.

As this training is Fargate we are going to setup a Networking only cluster.
For now we are going to create a new VPC.
Select: Create a new VPC for this cluster
``` 
10.0.0.0/16
10.0.0.0/24
10.0.1.0/24
```
For this course 2 subnets are enough.
Press Create

These subnets have 254 ip addresses available each which should be more than enough.
Go to CloudFormation to see what is happening!

Results:
 * VPCvpc-0adc34d6cb40367d7
 * Subnet 1subnet-096398da96466d1e1
 * Subnet 1 route table associationrtbassoc-09f34f64991059514
 * Subnet 2subnet-0c9416d4928830762
 * Subnet 2 route table associationrtbassoc-01891338d8b21c657
 * VPC Availability Zoneseu-west-1a, eu-west-1b, eu-west-1c
 * Internet gatewayigw-052800124935b19b3
 * Route tablertb-0c17747f71a6bc36c
 * Amazon EC2 routeEC2Co-Publi-1C1NSNJXHSV9Y
 * Virtual private gateway attachmentEC2Co-Attac-178W8U5Q798TK
This also shows what has to be created to make all of this work.

