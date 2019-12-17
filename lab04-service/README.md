# TERRA 10 Fargate Labs

## Lab 04 - The Fargate Service

Select your cluster and create new service
- Launch type: Fargate
- Task definition: <your just created task here>
- Revision: probably 1
- Service name: **nginx-XXX***
	*where XXX is your name*
- Number of tasks: 1
Next Step
- Select VPC:   ** vpc-0231210a6048235b6 **
- Select subnets  **subnet-0a47a39f97fde2396 and subnet-0d5f5bddb693879fd**
     *note that we use the public subnets, otherwise we cannot reach them*
- Auto-assign public IP: ENABLED
- Loadbalancer: none
Next step
Create service

Wait until the service is running, then copy the public IP and paste it in your browser.

Result: 
![alt text](https://github.com/terra10/codefest_ecsfargate/raw/master/lab04-service/lab04-nginx.png "Nginx")


## Additional information
The container is pulled from docker hub so that is the reason the service runs in a VPC with internet access (thanks to the AWS Internet Gateway).

It is also possible to use the internal AWS ECS repository or a private repository which requires credentials (like Artifactory or ...)

## Summary
Without any servers or EC2 infrastructure you are able to run your (Docker) container in AWS. Also allowing enhanced features like loadbalancing, auto-scaling and self-healing.