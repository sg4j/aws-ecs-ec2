## infrastructure/vpc.yml
This template deploys a VPC, with a pair of public and private subnets spread across two Availabilty Zones. It deploys an Internet Gateway, with a default route on the public subnets. It deploys a pair of NAT Gateways (one in each AZ), and default routes for them in the private subnets.

## infrastructure/security-groups.yml
This template creates necessary Securoty groups for our entire stack.

## infrastructure/load-balancer.yml
This template sets up our ALB in required public subnets. The ALB will be used for accessing our services that are all deployed in private subnets and are only accessible from configured public subnets.

## infrastructure/ecs-cluster.yml
This template sets up our ECS cluster. By default, it creates 2 t2.micro EC2 instances that will be used by ECS for hosting docker containers.

## infrastructure/master_infra.yml
This template consolidates all the above infrastructure stacks in one common stack. All the templates mentioned above are pulled from S3. It will be best if one creates there own S3 repo and then uses this master template to refer to their own S3 location.

## service-httpd.yml
This template creates a basic HTTP docker container by using the default HTTPD image from Docker hub.

## service-gs-springboot.yml
This template uses a customized springboot app. It uses the docker image uploaded at https://hub.docker.com/r/sg4j/gs-spring-boot/. By default, it deploys 2 instances of this service in docker containers within our ECS cluster.
