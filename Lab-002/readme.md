#Services
A service describes whic task we want to run where. And how we want to scale it  

## Lab 002 - The first Fargate Service
**Press Create Service**  
**Step1:** Configure Service  
**Launchtype:** FARGATE  
**Task Definition:**  <user>  
**Service name:** <user>  
**Number of tasks:** 1  
Leave the rest as is  

**Step 2: Configure Network**  
**Cluster VPC:** Select your VPC. (It probably is already filled in for you.)  
**Subnets:** Select at least 1 of your Subnets.  
**Security group:** take default   (in other labs we create our own)  
**Auto-assign public IP:** ENABLED    (just for this exercise)  

No LoadBalancer (Lab-003)  
And disable service discovery integration (Lab-003)  

**Press next**  
**Press next**  
**Press Create Service**  
**Press View Service**  

### Now test our service
First check out our ip, we need this to test our application.  
Press your *Cluster* --> *Service* --> *Your task*. This shows some details and Network settings:  

Network details:
![Image of Running Task](https://github.com/terra10/codefest_ecsfargate/tree/master/Lab-002/runningtask.png "test")


### Logging
Then we can have a quick look at the log:  
https://eu-west-1.console.aws.amazon.com/cloudwatch/home?region=eu-west-1#logs:  
It shows which port the container is listening to.  

Security Groups  
The only thing that is blocking our calls is the firewalls around our cluster.  
Let’s open these for now (not recommended in live environment)  

Go to EC2  Security Group  select you group(the group name partly contains the name of the created cluster)  
Add your port to the inbound rules.  
Do note we could have configured our container to listen to port 80.  

Testing  
Go to your page.  
http://<ip>:<your_port>/<your_path>/<ANY STRING HERE>  
(The reason for <your_path> should be clear later on: LAB D)  
Where name can be anything. In the logging you will see your message:  
11:04:00  
2019-06-19T11:04:00.950Z INFO [flogo.activity.log] - Hello {"name":"maarten"}  

Where name is the last part of the url.  


Congratulations, you have your first container running on Fargate!  


Clean up: Stop your container that is running on the cluster. Either by removing the Service or update the desired count to 0.  
