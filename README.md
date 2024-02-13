AWS CloudFormation Templates: VPC Setup and EC2 Instance with Apache
This repository contains two AWS CloudFormation templates to automate the setup of essential infrastructure components in AWS. The first template sets up a Virtual Private Cloud (VPC) with public IP addresses and DNS enabled, while the second template deploys an EC2 instance within the existing VPC with Apache web server installed and configured.

Prerequisites
Before deploying these templates, ensure you have the following prerequisites:

An AWS account with appropriate permissions to create CloudFormation stacks.
Familiarity with AWS CloudFormation and its concepts.
Basic knowledge of networking and EC2 instances.
Templates Overview
1. VPC Setup Template
Template File: vpc_setup_template.yml
Description: This template creates a VPC with DNS support and hostnames enabled. It also sets up a public subnet, an Internet Gateway, and necessary route configurations to enable communication with the internet.
Parameters:
VPCStackName: Name of the existing VPC stack to reference.
Region: AWS region for deployment.
Outputs:
VPCId: ID of the created VPC.
PublicSubnet: Subnet ID of the public subnet.
WebServerSecurityGroup: Security group ID for public web servers.
2. EC2 Instance with Apache Template
Template File: ec2_apache_setup_template.yml
Description: This template deploys an EC2 instance within an existing VPC and installs Apache web server on it. It also assigns an Elastic IP to the instance for static addressing.
Parameters:
VPCStackName: Name of the existing VPC stack.
Region: AWS region for deployment.
InstanceType: EC2 instance type.
Outputs:
WebsiteURL: URL of the website hosted on the EC2 instance.
PrivateIPv4Address: Private IPv4 address of the EC2 instance.
PrivateDNSName: Private DNS name of the EC2 instance.
Deployment Instructions
Deploy VPC Setup Template:

Use the CloudFormation console or AWS CLI to deploy the vpc_setup_template.yml.
Provide the required parameters.
After successful deployment, note the output values for further reference.
Deploy EC2 Instance with Apache Template:

Deploy the ec2_apache_setup_template.yml, providing necessary parameters including the name of the existing VPC stack.
Once deployed, access the website using the provided URL in the outputs.
Additional Notes
Ensure that your AWS credentials are properly configured for deployment.
Review and customize the templates as per your requirements before deployment.
Regularly monitor and manage the deployed resources to optimize costs and security.
For detailed instructions on using AWS CloudFormation, refer to the AWS CloudFormation documentation.
