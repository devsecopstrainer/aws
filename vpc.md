## VPC - Virtual Private Cloud
 - Under regions we have Availability Zones. 
 - Under AZs, multiple users create their resources in an isolated way so that they cannot communicate with each other. This service is called as VPC.
 - VPS is a logically isolated virtual network within the AWS cloud where you can launch AWS resources. 
 - We have full control over VPC's network configuration. Ex: IP address ranges, subnets, route tables, and security settings.
 - If two different users create EC2 instances under same physical host, still they cannot communicate with each other because both of them will get created under their own VPC.
 - VPC peering is a networking connection between two VPCs that enables route traffic between them. So, by VPC peering we can make 2 VPCs communicate with each other.
 - When we create the AWS account, AWS provides us default VPCs for each and every region. 
 - When we create EC2 instances, they will get created under the default VPCs.
 - If we do not have any resources then we can delete the default VPC also. We can create default VPC also. 
 - Without VPC, EC2 instances cannot be created.
 - We can create multiple VPCs as well in the same region, but it will create confusion. 

## Subnet:
 - We need to create subnets under Availability Zones so that we can use that particular availability zone. 
 - One subnet cannot use multiple Availability Zones. Subnet will always reside under Availability Zone.
 - We can create multiple subnets under one Availability Zone. 
 - We should use the same IP address range which we used for creating the VPC.
 - We cannot use any other series for this. It won’t allow to do so.

## VPC and Subnet:
 - VPC ia a logically isolated, private network in a public cloud. It is your own secure network.
 - Subnet is a logical division of a VPC, representing a range of IP addresses within the VPC.
 - In one region, we can create maximum 5 VPCs and 200 Subnets can be created in 1 vpc.
 - Once the VPC is created, we cannot change its cidr block range.
 - If we need a different cidr range, we need to create a new VPC.

