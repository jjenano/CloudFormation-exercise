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
