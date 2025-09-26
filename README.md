# Cloud Shell Scripting Repository
This repository contains practical shell scripts specifically designed for cloud environments like AWS. These scripts focus on automation, infrastructure management, cloud operations, and resource inventory.

## Introduction
This collection focuses on real-world cloud operations including AWS services automation, resource management, monitoring, deployment scripts, and comprehensive resource listing.

## Script Categories

### 📋 Resource Inventory & Listing
```aws_resource_list.sh``` - Master script to list all active AWS resources in a specific service across regions

### 🚀 AWS EC2 Management
```ec2-instance-management.sh``` - Start, stop, terminate EC2 instances

```ec2-backup-automation.sh``` - Automated EBS snapshots and AMI creation

```ec2-monitoring.sh``` - CloudWatch metrics and instance health checks

### 💾 AWS S3 Operations
```s3-bucket-management.sh``` - Create, configure, and manage S3 buckets

```s3-backup-sync.sh``` - Automated backup to S3 with versioning

```s3-lifecycle-policies.sh``` - Manage object lifecycle and storage classes

### ⚡ AWS Lambda & Automation
```lambda-deployment.sh``` - Automated Lambda function deployment

```cloudwatch-alerts.sh``` - Setup monitoring alerts and notifications

```cost-optimization.sh ```- Identify and optimize AWS costs

### 🐳 Container Management
```ecr-management.sh``` - ECR repository management and image pushes

```ecs-deployment.sh``` - ECS service updates and task management

```fargate-scaling.sh``` - Auto-scaling scripts for Fargate services

### 🔒 Security & Compliance
```iam-user-audit.sh``` - IAM user and policy reviews

```security-group-audit.sh``` - Security group configuration checks

```compliance-checks.sh``` - AWS Config and compliance validations

### 🗄️ Database Operations
```rds-backup-management.s```h - RDS snapshot and backup automation

```rds-performance-monitoring.sh``` - Database performance metrics

```dynamodb-operations.sh``` - DynamoDB table management
## Resource Listing Capabilities
- Service-specific filtering: List only active resources per service

- Regional focus: Target specific regions at a time

- Status-based filtering: Filter by resource state (running, stopped, available, etc.)

- Multi-format output: Table, JSON, and CSV formats

- Tag-based filtering: Filter resources by specific tags

## Prerequisites
- AWS CLI installed and configured

- Appropriate IAM permissions for the operations

- jq (for JSON parsing)

- Basic understanding of AWS services
  
## AWS CLI Setup

```bash
# Install AWS CLI (Linux)
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# Configure AWS CLI
aws configure

# Verify installation
aws sts get-caller-identity
```

## Master Script Examples
``` bash
# Make scripts executable
chmod +x aws_resource_list.sh
chmod +x "List Resources/"*.sh

# List active EC2 instances in current region
./aws_resource_list.sh --service ec2 --status running

# List all S3 buckets in specific region
./aws_resource_list.sh --service s3 --region us-west-2

# List available RDS instances across multiple regions
./aws_resource_list.sh --service rds --regions us-east-1,eu-west-1 --status available

# List Lambda functions with environment variables
./aws_resource_list.sh --service lambda --region ap-southeast-1 --output json

# List resources with specific tags
./aws_resource_list.sh --service ec2 --region us-east-1 --tags "Environment=Prod,Project=WebApp"
```

## File Structure

```text
shell_scripting/
├── README.md
├── List Resources/
│   ├── aws_resource_list.sh
├── aws/
│   ├── ec2/
│   │   ├── ec2-instance-management.sh
│   │   ├── ec2-backup-automation.sh
│   │   └── ec2-monitoring.sh
│   ├── s3/
│   │   ├── s3-bucket-management.sh
│   │   ├── s3-backup-sync.sh
│   │   └── s3-lifecycle-policies.sh
│   ├── lambda/
│   │   ├── lambda-deployment.sh
│   │   └── cloudwatch-alerts.sh
│   ├── security/
│   │   ├── iam-user-audit.sh
│   │   ├── security-group-audit.sh
│   │   └── compliance-checks.sh
│   └── database/
│       ├── rds-backup-management.sh
│       ├── rds-performance-monitoring.sh
│       └── dynamodb-operations.sh
├── templates/
│   ├── script-template.sh
│   └── iam-policy-template.json
└── utils/
    ├── aws-cli-check.sh
    └── dependency-check.sh
