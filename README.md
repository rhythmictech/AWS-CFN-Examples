# AWS-CFN-Examples
Example CloudFormation Templates

# Description
Various CloudFormation templates to handle routine AWS tasks and also achieve specific tasks. Most of these
templates are standalone, though you will find that many depend on each other in subtle ways. For example,
most of our scripts expect a VPC to already exist in another stack. Many people create their VPCs by hand
rather than in a stack. The templates are easily modified to fit whatever your scheme is.

# Security
* iam-password-policy
   Uses a custom resource to create an IAM Password Policy via CloudFormation. 

# Network
* main-vpc
   The VPC script creates a basic VPC with 3 public, 3 app (private) and 3 DB subnets. The public subnets each
   have a NAT gateway. A common route table is used to route public traffic to the Internet gateway. The app
   and DB subnets each share one route table per AZ, routing traffic out the respective NAT gateways. This
   design yields a simple 3 AZ setup ready for use in most scenarios, with properly configured networking.

# WordPress
* wordpress-with-efs-and-cloudfront
   Creates the foundation for a WordPress site sitting behind CloudFront, an ELB and an ASG. This is suitable
   for high availability, using EFS to share files across multiple instances within the ASG. 

