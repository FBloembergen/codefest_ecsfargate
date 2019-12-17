# TERRA 10 Fargate Labs (Theory)
ONLY Do this lab if you are doing this outside this training!  
Otherwise just read this for your knowledge.

## What is Amazon VPC? (Virtual Private Cloud)

Amazon VPC lets you provision a logically isolated section of the Amazon Web Services (AWS) cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address ranges, creation of subnets, and configuration of route tables and network gateways. 

## Lab 001 -Network

As this training is about Fargate and not setting up a network we have created this already.

DEMO Private Subnet (AZ1)     10.0.64.0/19  
DEMO Private Subnet (AZ2)     10.0.96.0/19  
DEMO Public Subnet (AZ1)      10.0.0.0/19  
DEMO Public Subnet (AZ2)      10.0.32.0/19  

Each have more than enough available IP adresses.


## How to do it outside this training

Navigate to AWS VPC and make sure to be in the “ireland” region. That’s where the party is.

https://eu-west-1.console.aws.amazon.com/vpc/home?region=eu-west-1#dashboard:
This contains a default VPC out of the box.
In this account you should see at least 2 VPCs.

Each of them have 1 or more subnets. As mentioned abover we are using the DEMO subnets.

## Using the wizard

Go to:
https://eu-west-1.console.aws.amazon.com/ecs/home?region=eu-west-1#/clusters

Press **Create Cluster**

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

