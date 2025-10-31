# Ansible-AWS-VPC-Automation

[![Ansible](https://img.shields.io/badge/Ansible-2.9%2B-blue.svg)](https://www.ansible.com/)
[![AWS](https://img.shields.io/badge/AWS-VPC-orange.svg)](https://aws.amazon.com/vpc/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/YOUR-USERNAME/ansible-aws-vpc-automation/graphs/commit-activity)

> **Production-ready Infrastructure as Code (IaC) solution for automating AWS VPC deployment with multi-AZ architecture, NAT Gateway, Internet Gateway, and Bastion Host using Ansible.**

## 🎯 Overview

This project provides a comprehensive Ansible automation framework for deploying and managing AWS Virtual Private Cloud (VPC) infrastructure. Designed with DevOps best practices, it enables rapid, consistent, and repeatable infrastructure provisioning across multiple environments.

### Business Value

- **⚡ Speed**: Deploy complete VPC infrastructure in under 15 minutes
- **🔒 Security**: IAM role-based authentication with encrypted secrets management
- **📊 Consistency**: Identical infrastructure across all environments using IaC
- **💰 Cost Optimization**: Automated resource tagging and multi-environment support
- **🔄 Disaster Recovery**: Rapid infrastructure recreation in alternate regions
- **📝 Audit Trail**: Complete version control of infrastructure changes

## ✨ Features

### Core Infrastructure Components

- ✅ **VPC Creation** with customizable CIDR blocks
- ✅ **Multi-AZ Deployment** across 2-3 availability zones
- ✅ **Public & Private Subnets** with automatic CIDR calculation
- ✅ **Internet Gateway** for public subnet connectivity
- ✅ **NAT Gateway** with Elastic IP for private subnet outbound traffic
- ✅ **Route Tables** with automatic association
- ✅ **Security Groups** with customizable rules
- ✅ **Bastion Host** (Jump Server) for secure private resource access
- ✅ **VPC Flow Logs** for network monitoring and compliance

### Automation Features

- ✅ **Idempotent Playbooks** - Safe to run multiple times
- ✅ **Multi-Environment Support** - Dev, Staging, Production
- ✅ **Secrets Management** - Ansible Vault integration
- ✅ **Dynamic Inventory** - AWS EC2 plugin support
- ✅ **Rollback Capability** - Infrastructure cleanup playbooks
- ✅ **CI/CD Integration** - GitHub Actions workflows
- ✅ **Comprehensive Logging** - Detailed execution logs
- ✅ **Cost Tagging** - Automatic resource tagging for cost allocation

  
**Traffic Flow:**
- **Public Subnet → Internet**: Route Table → Internet Gateway
- **Private Subnet → Internet**: Route Table → NAT Gateway → Internet Gateway
- **External → Bastion**: Internet → IGW → Bastion (Public Subnet)
- **Bastion → Private Instances**: SSH via private IP addresses

For detailed architecture documentation, see [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)

---

## 📦 Prerequisites

### Required Tools

| Tool | Version | Purpose |
|------|---------|---------|
| **Ansible** | 2.9+ | Infrastructure automation |
| **Python** | 3.8+ | Ansible runtime and boto3 |
| **boto3** | Latest | AWS SDK for Python |
| **botocore** | Latest | Low-level AWS service access |
| **AWS CLI** | 2.x | AWS command-line operations |
| **Git** | 2.x | Version control |

### AWS Requirements

- **AWS Account** with appropriate permissions
- **IAM Role** or **Access Keys** with the following permissions:
  - EC2 Full Access
  - VPC Full Access
  - IAM PassRole (for attaching roles to instances)
- **AWS Region** with at least 2 availability zones

### Knowledge Prerequisites

- Basic understanding of AWS VPC concepts
- Familiarity with Ansible playbooks and roles
- Linux command-line experience
- SSH key management knowledge



