# GitHub Actions Workflows

This page describes how to use the Github Action created to deploy this Google Public Respository of an e-commerce application to a cluster on any cloud.<br>

Google Repository: https://github.com/GoogleCloudPlatform/microservices-demo.git


## Executing the Pipeline

The URL bellow is the link to my Github Repository that holds the workflow to deploy the application on a cluster.<br>

https://github.com/deciobarrosjr/microservices-demo-google-online-boutique/actions

Once you acessed the URL above, the next step is to manually execute the workflow <span style="color: Chocolate;">deploy-to-cloud.yml</span>, as illustrated by the image bellow:

<br>

The image bellow illustrates an example of deploying the application on an Azure AKS.<br>
<span style="color: red;">NOTE</span>: not all fields is required, you should fill only the fields required by the cloud you are deploying the application on.

![image](/images/deploy-app.jpg)

The CI/CD pipelines for Online Boutique run on standard GitHub-hosted runners (Ubuntu). 

We also host a test GKE cluster, which is where the deploy tests run. Every PR has its own namespace in the cluster.

<br>

## Getting the External IP Address to access the application

The image bellow illustrates how to find, on the workflow execution, the external IP address to acess the application:

<br>

![image](/images/external-ip-deployed.jpg)

<br>

Access the aplication using: <span style="color: Chocolate;">http://<ip_address></span>

<br>

## Requirements to use this application

You will need a cluster deployed on the desired cloud in order to use this workflow. For now, i just tested it on Azure.

<br>

> Azure

To deploy the application on Azure, i created a new cluster using the container:<br>

C:\WORK\VSCODE-workspaces\Hello World\TERRAFORM\Azure\Simple AKS

On this Cluster, the following configuration was required to deploy the amount of resources required to deploy the application:<br>

```ruby
vm-size                 = "Standard_B2s"
node-count              = 2
```