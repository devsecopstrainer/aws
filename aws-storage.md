
## Storage

Block Storage ==> EBS - Elastic Block Store
File Storage  ==> EFS - Elastic File System
Object Storage => S3 - Simple Storage Service

## EBS (Elastic Block Store)

 - It is a block storage service that lets you store persistent data on EC2.
 - Root volume is the storage in EC2 where our OS is getting installed. This is called as EBS.
 - We can attache multiple EBS volumes to a single EC2 instance.
 - EBS volumes are created under Availability Zones.
 - EBS volumes can be attached to the instances running under same Availability Zone.
 
## EBS Volume Types:
 - SSD:
	- SSD-backed volumes are optimized for transactional workloads involving frequent read/write operations.
	- SSD-backed volume types include General Purpose SSD and Provisioned IOPS SSD.
	- GP2 and GP3 SSDs cannot be attached to multiple instances where as IOPS SSDs can be.
	- gp2 - General Purpose 2
		- Suitable for standard storage option for most EC2 instances. 
		- They work well for various applications, from small databases to boot volumes.
	- gp3 - General Purpose 3
		- This is an upgraded version of the general-purpose storage, offering better performance and flexibility.
	- io1 - Provisioned IOPS SSD v1 - (Input/Output Operations Per Second Solid State Drive)
		- Suitable for large databases or applications that demand low latency and high throughput.
		- throughput - rate at which data is processed or transmitted by a system, quantified in bits or bytes per second.
	- io2 - Provisioned IOPS SSD v2 - (Input/Output Operations Per Second Solid State Drive)
		- Suitable for highest levels of performance, durability, and reliability, such as critical production databases or applications where downtime is not an option.

 - HDD:
	- HDD volume types include Throughput Optimized HDD and Cold HDD.
	- Throughput Optimized HDD:
		- st1 volumes are suited for large, sequential workloads, such as data warehouses, log processing, or streaming workloads.
	- Cold HDD:
		- Designed for workloads that requires infrequent access to data, such as archival storage, backups, or long-term storage of data that's accessed less frequently.
			
 - Previous Generation:
	- Magnetic (standard) volumes are previous generation volumes that are backed by magnetic drives. 
	- They are suited for workloads with small datasets where data is accessed infrequently and performance is not of primary importance. 

## Create EBS Volume:

	1. Create one EC2 instance on region AP South 1b
	2. Connect to the instance and check the attached volumes using : lsblk   ==> list block
	3. Create one EBS volume: 
		EC2 > Elastic Block Store > Volumes > Create volume > 
			Volume type > gp3
			Size (GiB) > 2
			IOPS > 3000
			Throughput (MiB/s) > 125
			Availability Zone > 1b
			Snapshot ID - optional > Dont create
			Create volume
	4. Attach the EBS to EC2:
		select the ebs > action > attach volume
		> choose the instance from the drop down
		Device name > /dev/sdf  > (f-p)
		Attach volume 
	5. check the volume status from ec2 by using > lsblk
	6. Format the drive: sudo mkfs.ext4 /dev/xvdf
	7. Mount the SSD to the data directory:
		1. create a directory under /
			mkdir my-ssd
		2. Mount the SSD to the data directory	
			mount /dev/xvdf /my-ssd/

