# AWS Cloudformation VPC for 3-Tier application with HA Bastion Host
* New VPC (10.0.0.0/16)
* Internet Gateway for Internet access
* 6 Subnets in 2 Availability Zones A and B<br>
  Public Subnets A (10.0.11.0/24) and B (10.0.21.0/24) with Public IPs<br>
  Private Subnets A (10.0.12.0/24) and B (10.0.22.0/24) with Local IPs and NAT Internet access<br>
  Database Subnets A (10.0.13.0/24) and B (10.0.23.0/24) with Local IPs and NO Internet access<br>
* 2 NatGateways with ElasticIPs for Private Subnets
* HA Bastion host runs in one of the Public Subnets with an ElasticIP attached<br>
  With a choose of Instance type, Instance AMI ID, Key Name and on demand/spot* instance for the Bastion Host<br>
  After termination, the Bastion host will be automatically relaunched in a different AZ<br>
  The Bastion host will have the same puplic IP address, even after termination<br>
  The Bastion host will have the bare minimum permissions it needs to perform its work (The principle of least privilege)<br>
* All new resources are taged and/or named to let us know that they belong to this project

(!) If you want to use a spot instance for the Bastion host, you need to check the number of spot instance limit in your account. By default, this number is zero and you need to request a limit increase.

![VPC-Image](https://github.com/georgio-sd/aws-cloudformation-vpc-env/raw/master/vpc.jpg)
