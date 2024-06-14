# AWS CloudFormation Deployment Guide

## Overview

This repository contains AWS CloudFormation templates to deploy a scalable web application infrastructure on Amazon Web Services (AWS). The stack includes resources such as EC2 instances, Security Groups, an Application Load Balancer, and Auto Scaling Groups.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Prerequisites

Before deploying the stack, ensure you have the following:

- An AWS account: You need an active AWS account to deploy the resources.
- AWS CLI installed and configured: Install the AWS CLI and configure it with your AWS account credentials.
- Basic understanding of AWS CloudFormation: Familiarize yourself with AWS CloudFormation, which is used to provision the infrastructure resources in a repeatable and predictable manner.
- Basic understanding of AWS services like EC2, VPC, and ALB: Have a basic understanding of Amazon EC2, Virtual Private Cloud (VPC), and Application Load Balancer (ALB) as these services are utilized in the deployment.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Deployment Instructions

##Clone the Repository:

   git clone https://github.com/viralp2020/AWS-cloudFormation.git
   cd aws-cloudformation-webapp

Clone the repository containing the CloudFormation templates to your local machine and navigate to the project directory.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

##Deploy the Stack:

This command will create a CloudFormation stack with the specified parameters.

Deploy the CloudFormation stack using the AWS CLI. Replace your-stack-name with your desired stack name and provide appropriate values for the parameters.

aws cloudformation create-stack --stack-name your-stack-name --template-body file://template.yaml --parameters ParameterKey=EnvName,ParameterValue=YourEnvName ParameterKey=VPCCIDR,ParameterValue=10.10.0.0/16 ParameterKey=PublicSubnetACIDR,ParameterValue=10.10.1.0/24 ParameterKey=PublicSubnetBCIDR,ParameterValue=10.10.2.0/24 ParameterKey=PublicSubnetCCIDR,ParameterValue=10.10.3.0/24
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

##Monitor Stack Creation:

This command will provide details about the stack including its current status.

You can monitor the progress of stack creation in the AWS Management Console or using the AWS CLI. Use the following command to describe the stack:

aws cloudformation describe-stacks --stack-name your-stack-name
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
##Access the Application:

Once the stack creation is complete, you can access your application using the DNS name of the Application Load Balancer provided in the CloudFormation stack outputs.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
##Cleaning Up

To avoid incurring unnecessary costs, remember to delete the CloudFormation stack after you've finished using it. Use the following command to delete the stack:

aws cloudformation delete-stack --stack-name your-stack-name

