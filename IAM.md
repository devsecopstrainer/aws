## IAM:
 - Free service.
 - Global service.
## Identity:
 - When you create an AWS account, you get a root user that has complete access to all AWS services and resources in the account. 
 - Use IAM to set up other identities in addition to your root user, such as administrators, analysts, and developers, and grant them access to the resources they need to succeed in their tasks.
 - Authentication is the process of verifying your identity. You need to provide your login credentials to get authenticated to AWS console.
 - After a user is set up in IAM, they use their sign-in credentials to authenticate with AWS.

## Access management:
 - Once you are authenticated, authorization determines what actions you're allowed to perform or what resources you're allowed to access after your identity has been verified.

## IAM User - Identity and Access Management

 - It is a web service that helps you securely control access to AWS resources.
 - With IAM, you can manage permissions that control which AWS resources users can access.
 - Use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources such as ec2, s3 or DBs.
 - IAM enables you to create and manage users, groups, and roles, each with their own permission and access policies.
 - It is not a good practice to perform all the activities by using root user. So, we should create IAM user.

## IAM Groups:
 - In AWS IAM, "groups" are collections of IAM users. Groups allow you to manage permissions for multiple users collectively, rather than individually assigning permissions for each individual user.

  -  Download AWS CLI - https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
   - Install it

## CLI Commands:

  aws --version	
  aws configure



## Launch EC2 instance in us east 1 using AWS CLI:
 - aws ec2 run-instances --image-id ami-0cae6d6fe6048ca2c --count 1 --instance-type t2.micro --key-name test-key --region us-east-1

## Create S3 bucket:
 - aws s3api create-bucket --bucket testbkt10005 --region ap-south-1 --create-bucket-configuration LocationConstraint=ap-south-1

