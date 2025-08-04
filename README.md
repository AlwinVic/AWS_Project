🚀 Project: Scalable WordPress Deployment on AWS with High Availability and Private Database Layer

Project Details and steps:

1. VPC Setup
 - Create a VPC with 2 public and 2 private subnets across two AZs
 - Add Internet Gateway and NAT Gateway

2. Launch EC2 in Public Subnet
 - Install Apache, PHP, and WordPress
 - Connect EC2 to RDS in private subnet using private IP

3. Create RDS Instance
 - Used MySQL
 - Make sure it's not publicly accessible
 - Create a DB subnet group using private subnets

4. Create and Attach Security Groups
 - EC2 SG: Allow HTTP/HTTPS from ALB, MySQL only from RDS SG
 - RDS SG: Allow port 3306 only from EC2 SG

5. Configure S3 for Media
 - Offload media uploads from WordPress to S3
 - Use a plugin or wp-config.php integration

6. Set Up CloudFront and SSL (ACM)
 - Use CloudFront as CDN for faster delivery
 - Enable HTTPS using AWS Certificate Manager

7. Auto Scaling & Load Balancing
 - Add EC2 instances to Auto Scaling Group behind ALB
 - ALB handles incoming traffic and distributes load

8. Monitoring and Alerts
 - Enable CloudWatch metrics
 - Set alarms for high CPU, memory, or disk usage
