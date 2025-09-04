### Cloud Computing:
 - Cloud is a network of remote servers.
 - Cloud Computing is the delivery of computing resources over internet.
 - computing resources - Ex : Storage - SSD, DB, Software, etc.

### Advantages of Cloud Computing:
	1. No need to maintain physical Data Center.
		- Capital Expenses = 0
		- Operational Cost = Pay as you go
	2. Auto scaling feature.
	3. Unlimited capacity.
	4. Go global in minutes.
	
### Types of Cloud:
	1. Private Cloud - Works on private infrastructure. A single organization or business uses this cloud.
	2. Public Cloud - A third-party provider owns and operates the cloud, which is accessible to anyone over the internet.
	3. Hybrid Cloud 
 		- Combination of private cloud with a public cloud. 
 		- store sensitive data on-premises while using the cloud for less sensitive data.

### Horizontal vs Vertical Scaling:
 - Horizontal scaling adds more machines to distribute the workload, offering better fault tolerance and near-infinite scalability, while vertical scaling increases the resources of a single machine, such as CPU or RAM, to boost its performance. 

### Cloud Service Models:
1.	IaaS (Infrastructure as a Service):
 - IaaS is a type of cloud computing that provides users with access to computing resources, like servers, storage, and networking. It allows users to rent these resources on a pay-as-you-go basis, so they don't need to invest in hardware or software upfront. 
 - IaaS customers have full control over the virtual machines and can install and configure their own software and applications.
 - Ex: Amazon Web Services (AWS), Microsoft Azure, Google Compute Engine (GCE)

2. PAAS - Platform as a Service
 - PaaS is a cloud computing model in which customers can develop, run, and manage web applications without having to worry about the underlying infrastructure. PaaS provides customers a platform to build and deploy applications quickly and easily.
 - Ex: AWS RDS

3. SAAS - Software as a Service:
 - SaaS is a cloud computing model in which software applications are hosted on a remote server, and customers access them through a web browser. SaaS eliminates the need for customers to install and manage the software on their own systems.
 - Ex: Office 365, Gmail

### Latency:
 - latency is the delay between a request sent from a user's device and the response from a cloud server, measured in milliseconds, and is influenced by factors like physical distance, network congestion, server processing time, and the number of network hops. High latency leads to slow performance.

### AWS Global Infrastructure
 - The AWS Global Infrastructure comprises AWS Regions and Availability Zones.

### Regions and Availability Zones:
 - AWS Regions are separate geographic areas. AWS Regions consist of multiple, physically separated and isolated Availability zones that are connected with low latency, high throughput, highly redundant networking. 
Availability zones consist of one or more discrete data centres, each with redundant power, networking, and connectivity, and housed in separate facilities.

 - Data Center / Availability Zone = Physical Host 1 + Physical Host 2 + Physical Host ...
 - Region = Data Center 1 + Data Center 2 + Data Center ...
 - AWS Cloud = Region 1 + Region 2 + Region 3 + ...

### Amazon EC2:
 - Amazon Elastic Compute Cloud (EC2) is a web service that provides secure, resizable compute capacity in the cloud. EC2 is a web service that allows users to create and run virtual machines (instances) in the cloud.
An EC2 instance works like a VM for us which gets created on a Physical Host. 
 - Combination of multiple physical hosts will form one Availability Zone or a Data Centre.
 - Combination of multiple Availability Zones will create a region.
 - Combination of multiple regions will form the AWS Cloud. 

### AMI:
 - AMI stands for Amazon Machine Image, which is a template used to create virtual servers in Amazon Web Services (AWS). AMIs are used to launch instances of Amazon Elastic Compute Cloud (EC2).

### ENA 
 - Elastic Network Adapter - For High-Speed Connectivity. If it is yes, then it means the AMI supports high speed connectivity.

### Key Pair:
 - A key pair, consisting of a public key and a private key, private key for your computer and a public key for your instance. It is a set of security credentials that you use to prove your identity when connecting to an Amazon EC2 instance. 
 - Key Pair = public key + private key
 - For Linux instances, the private key allows you to securely SSH into your instance. 
 - For Windows instances, the private key is required to decrypt the administrator password, which you then use to connect to your instance.
 - Amazon EC2 stores the public key on your instance, and you store the private key. 
 - It's important that you store your private key in a secure place because anyone who possesses your private key can connect to your instances that use the key pair.

### Security Group:
 - A security group acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic. Inbound rules control the incoming traffic to your instance, and outbound rules control the outgoing traffic from your instance. 
 - When you launch an instance, you can specify one or more security groups. If you don't specify a security group, Amazon EC2 uses the default security group for the VPC. After you launch an instance, you can change its security groups. There is no additional charge for using security groups. 

### Status Check:
	1. System Status Check ===> 
		This check monitors the underlying AWS infrastructure that your EC2 instance runs on. A failure of this check indicates an issue with the physical host. 
		Ex:
			Loss of network connectivity
			Loss of system power
			Software or hardware issues on the host
			Hardware failure impacting network reachability
		Resolution: AWS involvement is usually required to fix a failed system check. 
	2. Instance Status Check =>
		This check monitors the health of the instance's operating system (OS) and its software and network configuration.
		Ex:
			Failed to boot the OS
			Corrupted file system
			Exhausted memory or CPU
			Incorrect networking or startup configuration
			Incompatible kernel
		Resolution: You must troubleshoot the problem from within the instance. 
	3. EBS Status Check ======> 
		This check monitors the health of the Amazon EBS volumes attached to the instance. 
		It confirms that the volumes are reachable and that I/O operations can be completed. 
		Resolution: Check CloudWatch metrics for the EBS volume.
	

### Public IP:
 - A public IP address is an IPv4 address that's reachable from the Internet. You can use public addresses for communication between your instances and the Internet.
 - A public IP address is assigned to your instance from Amazon's pool of public IPv4 addresses, and is not associated with your AWS account. When a public IP address is disassociated from your instance, it is released back into the public IPv4 address pool, and you cannot reuse it.
 - AWS releases your instance's public IP address when it is stopped, hibernated, or terminated. Your stopped or hibernated instance receives a new public IP address when it is started.
 - If you require a persistent public IP address that can be associated to and from instances as you require, use an Elastic IP address instead.
 - AWS charges for all public IPv4 addresses, including public IPv4 addresses associated with running instances and Elastic IP addresses.

### Private IP:
 - A private IPv4 address is an IP address that's not reachable over the Internet. You can use private IPv4 addresses for communication between instances in the same VPC.
 - A private IPv4 address, regardless of whether it is a primary or secondary address, remains associated with the network interface when the instance is stopped and started, or hibernated and started, and is released when the instance is terminated.







