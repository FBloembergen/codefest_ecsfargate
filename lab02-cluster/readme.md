# TERRA 10 Fargate Labs

## Lab 02 - The ECS cluster 

Navigate to ECS (Elastic Container Service), make sure to be in the “ireland” region. That’s where the party is.

https://eu-west-1.console.aws.amazon.com/ecs/home?region=eu-west-1#/getStarted

- Create a new cluster
- Networking Only (Fargate) because the other options are for physical servers and we dont need EC2 instances at all
- Name your cluster with an unique id, like your own name
- Make sure to enable Cloudwatch Insights for detailed logging

## Additional informastion:
An AWS ECS Fargate cluster is an empty box. You can use it to group services with their tasks, but it has no other use at all. The network and runtime logic is all determined on task and service level. Two services running in cluster A could therefor not communicate with eachother if network wise this would not be configured, like a service in cluster A and one in cluster B could if they run in the same network subnet.

One AWS ECS cluster can host both ECS (IAAS) and ECS Fargate (serverless) tasks combined. EKS (Kubernetes) however has it's own cluster.