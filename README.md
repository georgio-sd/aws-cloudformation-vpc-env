# AWS Cloudformation VPC for 3-Tier application with HA Bastion Host
* New VPC (10.0.0.0/16)
* Internet Gateway for Internet access
* 6 Subnets on 2 Availability Zones A and B
  Public Subnets A (10.0.11.0/24) and B (10.0.21.0/24) with Public IPs 
  Private Subnets A (10.0.12.0/24) and B (10.0.22.0/24) with Local IPs and NAT Internet access
  Database Subnets A (10.0.13.0/24) and B (10.0.23.0/24) with Local IPs and NO Internet access
* 2 NatGateways with ElasticIPs for Private Subnets
* HA Bastion host runs in one of the Public Subnets with an ElasticIP attached
