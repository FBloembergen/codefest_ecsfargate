# TERRA 10 Fargate Labs

## Lab 04 - The Fargate Service

Select your cluster and create new service
- Launch type: Fargate
- Task definition: <your just created task here>
- Revision: probably 1
- Service name: nginx-XXX
- Number of tasks: 1
Next Step
- Select VPC
- Select subnets
- Auto-assign public IP: ENABLED
- Loadbalancer: none
Next step
Create service

Wait until the service is running, then copy the public IP and pase it in your browser.

Result: 
![alt text](https://github.com/terra10/codefest_ecsfargate/raw/master/lab04-service/lab04-nginx.png "Nginx")


## Additional information
The container is pulled from docker hub so that is the reason the service runs in a VPC with internet access (thanks to the AWS Internet Gateway).

It is also possible to use the internal AWS ECS repository or a private repository which requires credentials (like Artifactory or ...)

