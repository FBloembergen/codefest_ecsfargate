# TERRA 10 Fargate Labs

## Lab 05 - Loadbalancer

### Create the application loadbalancer (Theory)
As with the Internet Gateway there is a max of 5 loadbalancers unless upgraded using a service call.
For this training we already created one. You can create one using the following instructions.

Go to EC2 and create an ALB
https://eu-west-1.console.aws.amazon.com/ec2/v2/home?region=eu-west-1#LoadBalancers:

- Create
- Select Application Load Balancer (ALB)
- Select an unique name
- Choose internet facing
Next
- Select the default VPC and the public subnets.
Next, Configure Security
- Select the default security group
Next, Configure Routing
- Select an unique name for the target group
- Target type choose IP
Next, Register targets
Next, Review
Create

Summary:
We created an application load balancer that forwards HTTP (port 80) traffic to a new target group. Normally you can configure target groups to point to 1-n servers to load balancer their load. In this case we let the container register itself dynamically.


### Use the loadbalancer with your Fargate service
Go to ECS and create a new Service definition, name it nginx-alb-someUniqueName
Use the same settings for the Nginx container but this time enable the loadbalancer option:

![alt text](https://github.com/terra10/codefest_ecsfargate/raw/master/lab05-loadbalancer/lab05-alb.png "ALB")

![alt text](https://github.com/terra10/codefest_ecsfargate/raw/master/lab05-loadbalancer/lab05-container2alb.png "ALB 2")

## Additional information
