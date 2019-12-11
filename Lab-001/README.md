# TERRA 10 Fargate Labs

## Lab 001 - The first Fargate Task

## ECR - Elastic Container Registry
This is our repository for Docker Images. 
You can find it under ECS  Amazon ECR  Repositories. Or type in ECR under Services. This directs you directly to the repository.

Under Reposities you’ll find the repository helloflogo and when opening this you will only find 1 Image with tag: latest. For this course it is good enough to have only the latest tag. However I wouldn’t recommend to use latest. Except maybe for snapshots.
Also keep in mind at any time no tag is given when loading an image ECS will pick latest.


## Task Definitions
With a task we define what we want to run and how to configure it.
Go back to Amazon ECS  Task Definitions. Or type in ECS under Services.

We are now going to create a task Manually.
Press Create new Task Definition
Select Fargate as our target. And press Next Step

!! Do note in all cases where you see Maarten rename this to your own name!!
It is just a name and not linked to your account.

**Task Definition Name:** Fargate<user>
**Task Role:**  ecsTaskExecutionRole
**Task execution role:**  ecsTaskExecutionRole

**Task memory:** 0.5
**Task CPU:** 0.25

Then we will find a blue button:  “Add container”.
This is to configure the container.

**ContainerName:** <user>
**Image:**  779717477382.dkr.ecr.eu-west-1.amazonaws.com/helloflogo
**PortMapping – ContainerPort:** 8080

The last thing we set are container environment settings:

Search for Environment Variables and add the following 2 lines
Key: path   value: /maarten/:name
Key: port   value: 8080


## Additional information:
A lot has been created for us:
Task: https://eu-west-1.console.aws.amazon.com/ecs/home?region=eu-west-1#/taskDefinitions/FargateMaarten
Logging: https://eu-west-1.console.aws.amazon.com/cloudwatch/home?region=eu-west-1#logs:
Role: https://console.aws.amazon.com/iam/home?region=eu-west-1#/roles/ecsTaskExecutionRole
