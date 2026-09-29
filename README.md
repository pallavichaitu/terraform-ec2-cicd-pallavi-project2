# Automated AWS EC2 Deployment Using Terraform and GitHub Actions

## Project Overview

This project demonstrates Infrastructure as Code (IaC) by automating the deployment of an AWS EC2 instance using Terraform and GitHub Actions.

The complete deployment process is automated through a CI/CD pipeline. Whenever changes are pushed to the GitHub repository, GitHub Actions automatically validates, plans, and applies the Terraform configuration to provision AWS infrastructure.
## Architecture
Developer
    │
    ▼
GitHub Repository
    │
    ▼
GitHub Actions CI/CD Pipeline
    │
    ├── Terraform Init
    ├── Terraform Validate
    ├── Terraform Plan
    └── Terraform Apply
    │
    ▼
AWS EC2 Instance
    │
    ▼
Apache Web Server
    │
    ▼
Static Web Page

## Technologies Used

- Terraform
- AWS EC2
- AWS Security Groups
- GitHub Actions
- Git
- Linux
- Apache HTTP Server

## Features
- Infrastructure as Code (IaC)
- Automated EC2 provisioning
- Automated Security Group creation
- CI/CD pipeline using GitHub Actions
- Apache Web Server installation using User Data
- Automatic deployment on code push
- Public web access through EC2

## Project Structure
project-02-ec2-cicd
│
├── .github/
│   └── workflows/
│       └── deploy.yml
│
├── main.tf
├── provider.tf
├── variables.tf
├── terraform.tfvars
├── outputs.tf
├── .gitignore
└── README.md

### Security Group

Configured with:

| Port | Protocol | Purpose |
|--------|---------|---------|
| 22 | TCP | SSH Access |
| 80 | TCP | HTTP Access |

### EC2 Instance

- Instance Type: t3.micro
- Operating System: Amazon Linux 2023
- Public IP Enabled
- Security Group Attached

### User Data Script

Automatically:

- Updates packages
- Installs Apache Web Server
- Starts Apache Service
- Enables Apache on boot
- Creates a custom web page

## CI/CD Workflow

The GitHub Actions workflow performs:
terraform init
terraform validate
terraform plan
terraform apply -auto-approve

Deployment is triggered automatically whenever code is pushed to the main branch.

## Deployment Steps

1. Terraform code pushed to GitHub.
2. GitHub Actions workflow triggered.
3. AWS credentials retrieved from GitHub Secrets.
4. Terraform initializes providers.
5. Terraform validates configuration.
6. Terraform generates execution plan.
7. Terraform provisions AWS resources.
8. EC2 instance launches.
9. Apache web server is configured automatically.
10. Website becomes accessible through the EC2 Public IP.

## Learning Outcomes

Through this project I learned:

- Infrastructure as Code (IaC)
- Terraform resource provisioning
- AWS EC2 deployment
- AWS Security Group configuration
- GitHub Actions CI/CD pipelines
- GitHub Secrets management
- Automated infrastructure deployment
- EC2 User Data scripting
- Infrastructure automation best practices

## Future Improvements
- Remote Terraform State using S3
- Terraform State Locking using DynamoDB
- Application Load Balancer
- Auto Scaling Group
- CloudWatch Monitoring
- Multi-environment deployments
- Terraform Modules

## Author

name: Pallavi
mailid: sugandhi2391@gmail.com

AWS | Terraform | DevOps | Cloud Computing Enthusiast
