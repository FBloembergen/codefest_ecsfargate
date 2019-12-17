# TERRA 10 Fargate Labs

## Lab 07 - AppMesh Exploring

You know have a general idea of the ECS Task Definition and App Mesh configuration. However to get App Mesh to work with service discovery is only possible through massive amount of Cloudformation scripting. So we will inspect the terra10 app mesh configuration and show a demo of te result.

### Inspect ECS Fargate Task
Go to ECS Fargate task: https://eu-west-1.console.aws.amazon.com/ecs/home?region=eu-west-1#/taskDefinitions
- Select the DEMO-ColorTeller-red task revision 2
- Look at the 3 container definitions in the task

### Summary ECS Fargate Task
The Task Definition consists of 3 containers which is the colorteller APP, the envoy proxy for AWS App Mesh and the AWS X-Ray Daemon to support end-to-end tracing.

### Inspect Route 53 
Go to Route 53 https://console.aws.amazon.com/route53/home?region=eu-west-1#hosted-zones: 
- Select the terra10.local 
- Examine the records

### Summary: Route 53
This Route 53 hosted zone is created with Service Discovery scripts which actually sets up a whole network segment for the envoy proxies that run as sidecars to communicate with each oter. When the AWS ECS Fargate Service starts it will register it's Task private IP in Route 53 and with termination the A records will be removed.

### Inspect App Mesh
Go to App Mesh: https://eu-west-1.console.aws.amazon.com/appmesh/meshes?region=eu-west-1
- Select the terra10-mesh
- Examine the virtual service (exposed entry to the service mesh)
- Examine the virtual nodes which shows 3 different nodes (the endpoints of the sidecar attached to the colorteller tasks)
- Examing the virtual router which shows the route and the weight (notice the weight on blue) which will result in 50% of the traffic to the blue colorteller

![alt text](https://github.com/terra10/codefest_ecsfargate/raw/master/lab07-appmesh-exploring/lab07-virtualroute.png "Virtual Route")

### Summary App Mesh
The App Mesh is basically a configurable, low‑latency infrastructure layer designed to handle a high volume of network‑based interprocess communication among application infrastructure services using application programming interfaces (APIs). The service, nodes and routes are the basic network components necessary for this communication.

### Inspect X-Ray
Go to the X-Ray service map: https://eu-west-1.console.aws.amazon.com/xray/home?region=eu-west-1#/service-map

### Summary App Mesh
When the demo will start watch for the the tracing.

And now ... we wait :-)