### AWS VPC Infrastructure with EC2 and Security Groups - Terraform
This project uses Terraform to provision a Virtual Private Cloud (VPC) on AWS, complete with subnets, route tables, an internet gateway, security groups, and EC2 instances. The infrastructure is designed for a two-tier architecture, allowing you to quickly deploy and manage AWS resources.

### Overview
This project automatically sets up a custom VPC in AWS with public subnets, EC2 instances, security groups to allow specific ingress and egress traffic, an internet gateway, and route table associations. It provides a flexible foundation for deploying applications in a secure, scalable AWS environment.

### Architecture
The following resources are created as part of the infrastructure:

* VPC - A Virtual Private Cloud with a CIDR block of 10.0.0.0/16.
* Subnets - Two subnets across different Availability Zones for high availability.
* Internet Gateway - Provides internet access for resources in the public subnets.
* Route Table - Contains routes that direct internet-bound traffic through the Internet Gateway.
* Security Group - Allows inbound traffic on specified ports (SSH, HTTP, custom ports) and allows all outbound traffic.
* EC2 Instances - Two EC2 instances in separate subnets for load distribution.

### Prerequisites

* Terraform installed on your local machine (v0.13 or above).
* AWS CLI configured with appropriate permissions.
* AWS Account with programmatic access.
* A valid AWS profile (default in this case).

### Usage
1. Clone the repository:
   ```
   git clone <repository-url>
   cd <project-directory>
   ```
2. Initialize Terraform:
   ```
   terraform init
   ```
3. Preview Changes:
   ```
   terraform plan
   ```
4. Apply Configuration:
   ```
   terraform apply
   ```
5. Destroy the Infrastructure:
   ```
   terraform destroy
   ```
   
### Resources
This Terraform project provisions the following AWS resources:

1. VPC: Creates a custom VPC with CIDR block.
2. Subnets: Creates two subnets in different availability zones.
3. Internet Gateway: Allows outbound internet access for public subnets.
4. Route Tables: Configures routing for internet traffic through the gateway.
5. EC2 Instances: Deploys two EC2 instances in the VPC.
6. Security Group: Configures rules to allow inbound SSH, HTTP, and custom ports.

### Additional Information
AWS Free Tier Usage: Ensure that your configuration stays within AWS Free Tier limits if applicable to avoid unexpected charges.
Scaling: You can easily scale this architecture by adding more subnets or modifying instance counts.
