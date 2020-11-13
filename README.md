# CloudFormation-exercise



<p align="center">
<img src="https://user-images.githubusercontent.com/20606917/99008085-1c9f4500-250b-11eb-8fa4-0fe876c92191.png" width="400">
</p>


### Requirements
![arquitectura](https://user-images.githubusercontent.com/20606917/99007910-c6320680-250a-11eb-832b-563de65b8b76.png)

Create necesary files to create the following:
  - Create a VPC (2 private subnets and 2 public subnets)
  - RDS instance working with mysql
  - EC2 instance and install and configure a wordpress server using the userdata
  - Create a route53 record for the wordpress public ip

All this work needs to be deployable using CloudFormation Nested Stacks

### Steps to use this files

  - Go to Amazon S3 and upload all the files
  - Go to CloudFormation and create a Stack
  - Select <main.yml> file on your S3 bucket  and copy the URL on CloudFormation
  - When all the resources all created go to the route53 record created
  - Start using wordpress


### Tech

#### main.yml file:
___

It is the root of all nested stacks. This file will control the call for the other stacks in order to deploy all the architecture. Each stack depends of the previous one. 

#### vpc.yml file:
___

This file will deploy a VPC that allows to launch resources. Within the VPC are added 4 different subnets, 2 private subnets and 2 public subnets. Whithin one private subnet the RDS instance will be deployed, security is the main objective of use this. 
Subnets are deployed in different availability zones. It also has internet access, so that the instances can communicate through the internet gateway. The subnets are in a public routing table so they can be accessed without any problem.

#### rds.yml file:
___

Here you can find all the RDS instance definition and configuration needed to work with mysql. There is also the configuration of the security group that the RDS instance has to communicate with the Wordpress server

#### ec2wordpress.yml file:
___

This file will deploy an EC2 instance with custom userdata in order to set up wordpress enviroment, this wordpress will use the MySql instance that was previously deployed with RDS.

#### route53.yml file:
___

In this file you can find all the needed configuration to take the public ip that EC2 instance expose and make an A DNS type record int route53 service. 
