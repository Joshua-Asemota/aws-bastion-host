

# AWS Bastion Host & SSH ProxyJump

## Project Overview
This project demonstrates how to securely access a private Amazon EC2 instance through a bastion host using SSH ProxyJump.

## Architecture
- **VPC:** `10.0.0.0/24`
- **Public subnet:** `10.0.0.0/25`
- **Private subnet:** `10.0.0.128/25`
- **Bastion host:** EC2 instance in the public subnet
- **Private instance:** EC2 instance in the private subnet
- **Access method:** SSH ProxyJump

## Security Configuration
- Bastion security group allows SSH from my public IP only.
- Private instance security group allows SSH from the bastion security group.
- The private instance has no public IP address.
- Separate keypair was use for public and private instances.
- SSH private keys and credentials are excluded from Git.

## Connection
```bash
ssh private_host
```

## Learning Outcomes
- AWS VPC and subnet design
- CIDR allocation
- EC2 provisioning
- Security group configuration
- SSH authentication
- SSH ProxyJump
- Secure access to private instances
