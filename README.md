# aws-ecs-ec2
AWS ECS CFT templates for EC2 Launch type

This repository has the following templates
vpc.yaml - This template deploys a VPC, with a pair of public and private subnets spread across two Availabilty Zones. It deploys an Internet Gateway, with a default route on the public subnets. It deploys a pair of NAT Gateways (one in each AZ), and default routes for them in the private subnets
