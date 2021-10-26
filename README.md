# website-terraform
Deploy a highly available website USING Terraform

Configure existing instances to serve a custom website
Create an Elastic Load Balancer with the instances in its pool
Create public subnets and security groups to secure the deployment For demonstration purposes, the website is a simple web page that echoes back the instance ID of the EC2 instance that served the request.

Configuring Network Resources for Elastic Load Balancing with Terraform
now have two instances serving your custom website. The instances are running in private subnets in different availability zones and are assigned to the default security group for the VPC that allows all traffic. There are a few resources that need to be created to allow for an Elastic Load Balancer (ELB) to securely distribute traffic between the instances:

Public subnets for each availability zone must be created so the load balancer can be accessed from the internet
This requires additional resources such as an internet gateway to connect to the internet, and route tables that route to the internet
A security group to allow traffic from the internet to the public subnets that will house the ELB on port 80 (HTTP)
A security group to allow traffic from the ELB in the public subnets to the instances in the private subnets on port 80 (HTTP)
 will make use of separate configuration files to make the configuration more manageable.

Configuring an Elastic Load Balancer with Terraform
after completion the private tier of the website infrastructure and we have two public subnets and a security group for an ELB. In this  Step,  will complete the scenario by adding a cross-zone ELB to distribute traffic to the web servers running in the private subnets. The website will then be highly available since the ELB will allow you to continue serving the website while one instance is down.
Destroying Resources with Terraform
