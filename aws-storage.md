
## Storage

 - Block Storage ==> EBS - Elastic Block Store
 - File Storage  ==> EFS - Elastic File System
 - Object Storage => S3 - Simple Storage Service

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

Create snapshot for EBS Volume.

## EFS - Elastic File System:
  - Multiple EC2 instances present on different availability zones can use same EFS.
  - EFS is supported by Linux only, for Windows, we need to use FSX.
  - No need to provide the size for EFS as it is elastic.

		sudo su -
		yum install httpd -y
		systemctl start httpd
		systemctl status httpd
		yum install nfs-utils -y

		mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 192.168.0.55:/ /var/www/html - 1A
		mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 192.168.1.60:/ /var/www/html - 1B

Simple Storage Service - S3
============================
 - Scalable object storage service on AWS.
 - object storage - Storing data as distinct objects.
 - Store any amount of data in any format.
 - Each object will be having their own metadata.
 - Bucket - It is a container for objects, like folders.
 - Object - It is a file and any metadata that describes the file which we upload.
 - Public Access - Who can access the bucket.
 - Storage Class - Different cost/options for S3.
 - Static web hosting on S3
 - Versioning

## S3 Usage:

		1. To store the build files - jar files
		2. Terraform - To store terraform.tfstate file securely S3 which supports locking, versioning, and encryption.
		3. We can use S3 as a storage location and as a backup location. 
		4. We can do static website hosting in S3.
		5. S3 can be used to store huge files for Bigdata analytics.
		6. Snapshot of EBS and AMI can be stored in S3.

## create a bucket:
	1. Choose the region: For latency
	2. Bucket Type:
		General Purpose : To be stored across multiple availability zones. 
		Directory : To be stored in single availability zone with faster access.
	3. Bucket Name:
		Rules:
		•	Bucket names must be between 3 (min) and 63 (max) characters long.
		•	Bucket names can consist only of lowercase letters, numbers, dots (.), and hyphens (-).
		•	Bucket names must begin and end with a letter or number.
		•	Bucket names must not contain two adjacent periods.
		•	Bucket names must not be formatted as an IP address (for example, 192.168.5.4).
		•	Bucket names must not start with the prefix xn--.
		•	Bucket names must not start with the prefix sthree-.
		•	Bucket names must not start with the prefix sthree-configurator.
		•	Bucket names must not start with the prefix amzn-s3-demo-.
		•	Bucket names must not end with the suffix -s3alias. This suffix is reserved for access point alias names.
		•	Bucket names must not end with the suffix --ol-s3. This suffix is reserved for Object Lambda Access Point alias names.
		•	Bucket names must not end with the suffix .mrap. This suffix is reserved for Multi-Region Access Point names. 
		•	Bucket names must not end with the suffix --x-s3. This suffix is reserved for directory buckets.
		•	Bucket names must be unique across all AWS accounts in all the AWS Regions .
		•	A bucket name cannot be used by another AWS account in the same partition until the bucket is deleted.
	4. Copy settings from existing bucket if we have.
	5. Object Ownership - To control the ownership - single or multiple accounts.
	6. Block Public Access.
	7. Bucket Versioning - For backup purpose.
	8. Tags - organizing and tracking buckets
	9. Encryption



## Versioning:

	You can use S3 Versioning to keep multiple versions of an object in one bucket so that you can restore objects that are accidentally deleted or overwritten. 
	If you delete an object, instead of removing the object permanently, Amazon S3 inserts a delete marker, which becomes the current object version.
	If you overwrite an object, Amazon S3 adds a new object version in the bucket. The previous version remains in the bucket and becomes a noncurrent version. You can restore the previous version.


## storage class:

	Each object in S3 has a storage class associated with it.
	S3 offers a range of storage classes for the objects that you store.

### S3 Standard:
	The default storage class.
	Suitable for frequently accessed data (more than once a month) with milliseconds access.
	If you don't specify the storage class when you upload an object, Amazon S3 assigns the S3 Standard storage class. 

### S3 Intelligent-Tiering:
	Suitable for data with changing or unknown access patterns
	It optimizes storage costs by automatically moving data to the most cost-effective access tier with a small monthly object monitoring and automation fee.

### Standard-IA:
	Suitable for infrequently accessed data (once a month) with milliseconds access.
	Min storage duration = 30 days
	Min storage duration = Once you upoload the data you need to keep it for certain period of time.

### One Zone-IA:
	Suitable for infrequently accessed data (once a month) with milliseconds access, to be stored in 1 Availability Zone.
	Min storage duration = 30 days	

### Glacier Instant Retrieval:
	Long-lived archive data accessed once a quarter with instant retrieval in milliseconds.
	Min storage duration = 90 days
	
### Glacier Flexible Retrieval:
	Long-lived archive data accessed once a year with retrieval of minutes to hours.
	Min storage duration = 90 days

### Glacier Deep Archive:
	Long-lived archive data accessed less than once a year with retrieval of hours
	Min storage duration = 180 days

### Reduced redundancy:
	Noncritical, frequently accessed data with milliseconds access.
	It is not recommended as S3 Standard is more cost effective.

### Check the S3 storage classes comparison:
	https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html



## static web hosting:

		A static website is a collection of pre-built HTML, CSS, and JavaScript files that are served to a user's browser exactly as they are stored on the server. 
		It does not use server-side processing or databases to generate content on the fly, meaning every visitor sees the exact same information.
















