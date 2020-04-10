##### 1. creates a new load balancer. The subnets are the two subnets where ec2 instances are launched and the security group is the security group  that are attached to EC2 instances

aws elbv2 create-load-balancer --name alblab-load-balancer --subnets <SUBNET 1 ID> <SUBNET 2 ID> --security-groups <SECURITY GROUP ID>

##### 2. creates a target group  

aws elbv2 create-target-group --name my-targets --protocol HTTP --port 80  --vpc-id <VPC ID>

##### 3. Register targets

aws elbv2 register-targets --target-group-arn <TARGET GROUP ARN>  --targets Id=<INSTANCE 1 ID> Id=<INSTANCE 2 ID>
  
##### 4. Create listener

aws elbv2 create-listener --load-balancer-arn <LOAD BALANCER ARN>  --protocol HTTP --port 80  --default-actions Type=forward,TargetGroupArn=<TARGET GROUP ARN>
  
##### 5. Describe target health

aws elbv2 describe-target-health --target-group-arn <TARGET GROUP ARN>
