# TERRA 10 Fargate Labs

## Lab 06 - AppMesh Task

### Create 
Go to ECS and create a new Task Definition
- Task Definition Name: nginx-mesh-XXXXX
     *where XXXXX is your name or something unique it is shared between the Clusters*

Use identical settings as in Lab03 except at the service integtation section:
- Enable App Mesh integration
- Application container name: nginx
- Mesh name: nginx-appmesh
- Virtual Node name: nginx-node1 OR nginx-node2 OR ... 
Click Apply and the console will popup below image which you examine first and then approve :-) 

![alt text](https://github.com/terra10/codefest_ecsfargate/raw/master/lab06-appmesh-task/lab06-mesh2.png "Envoy pop-up")

Look at your task definition now. The result of the popup is that your task  now has an additional container in its definition. This is the envoy sidecar which is technology on which the AWS App Mesh service is based. 
https://www.envoyproxy.io/learn/service-mesh

### Optional
If you like you can examine and enable the AWS Firelens option as well which is a relative (2019) new AWS Service which is a universal (open source) log router. Enabling it will add an additional container to your definition which runs either Fluentd https://www.fluentd.org/ or Fluentbit https://fluentbit.io/

You can compare both here: https://dzone.com/articles/fluentd-vs-fluent-bit-side-by-side-comparison-logz
We won't go further with this in the labs, but it is interesting to know.

### Summary:
By enabling options in your task definition we are able to add "sidecars" to our functional container.