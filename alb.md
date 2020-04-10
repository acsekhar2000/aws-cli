# creates a new load balancer. The subnets are the two subnets where ec2 instances are launched and the security group is the security group  that are attached to EC2 instances

aws elbv2 create-load-balancer --name alblab-load-balancer --subnets <SUBNET 1 ID> <SUBNET 2 ID> --security-groups <SECURITY GROUP ID>
