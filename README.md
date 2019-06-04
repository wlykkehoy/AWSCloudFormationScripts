# AWSCloudFormationScripts

This is a collection of AWS CloudFormation Scripts. The origin of many/most is the DevOps and Cloud Infrastructure course (SEIS665) at St Thomas.

CF File | Description & Notes
--- | --- 
jenkins-cf.json | A Jenkins environment with a Jenkins Master and 1 – 5 Slaves. Note this is a very ‘complete’ setup, creating an IAM role, autoscaling group, user data scripts on/for the EC2 instances, etc. <br/><br/>Used for SEIS665 Lecture 8 exercise and Lecture 11 exercise / homework. <br/><br/>SSH username: ubuntu
s3bucket.json | Creates an S3 Bucket named seis665<random-stuff>. It is a very simple setup. <br/><br/>From SEIS665 Lecture 9.
aws-quickstart-vpc | From the AWS quickstart site; is a template for a VPC with all the trimmings; public & private subnets, NAT gateway, IG, etc.
aws-quickstart-alfresco | From the AWS quickstart site; includes ELB and RDS instance setup.
vpc_single_instance_in_subnet | Sample template showing how to create a VPC and add an EC2 instance with an Elastic IP address and a security group.
BasicWebserverInVPC | From the SEIS665 in-class hands-on exercise. Includes a VPC with 2 subnets, an IG, security groups, and one web server. Outputs the URL of the web server. <br/><br/>When you hit the URL, you will get the message “Hi, I'm instance i-xxxxxxxxxx”
BasicWebserverInVPC2 | Takes BasicWebserverInVPC a step further and adds a load balancer and autoscaling. Outputs the URL of the load balancer. <br/><br/>When you hit the URL, you will get the message “Hi, I'm instance i-xxxxxxxxxx”. Repeated hitting the URL, you will see the instance names changing as the requests will hit the different Instances.
BasicVPC.json | Takes BasicWebserverInVPC and adds an option for either 2 web servers or three. Thus shows how to use conditions. It’s a bit messy/complicated. This one also uses the NetworkInterfaces object to define the networking stuffs for an EC2 Instance.
packer-cf.json | Creates a simple AWS stack with a single server running Packer.
AnsibleSystems.json | Creates an Ansible control node and two hosts to be managed by Ansible. 
corpweb.json | SEIS665 Homework assignment 8. Creates:<br/>-	One VPC with two Subnets; each Subnet is in a separate Availability Zone<br/>-	An Internet Gateway for the VPC<br/>-	A Route Table for the Subnets to route traffic to the Internet via the Internet Gateway<br/>-	Two EC2 Instances (webservers); one in each of the two Subnets<br/>-	A Security Group for the EC2 Instances<br/>-	A Load Balancer for balancing load between the two Instances<br/>-	A Security Group for the Load Balancer<br/><br/>See HW8-01.pdf for details.
docker-single-server.json | Launches a stack containing a single Amazon Linux EC2 instance with the Docker engine software installed.
docker-single-server-v2.json | Basically same as docker-single-server.json but based on Ubuntu servers rather than AWS Linux. Used this stack for the final exam. <br/><br/>SSH username: ubuntu
docker-swarm.json | Launches a Docker Swarm cluster. The number of manager nodes and number of worker nodes are specified via parameters. This is a fairly complex CF topology. See docker-swarm-diagram; note the subnet IP’s are not correct on the diagram. <br/><br/>There is a really cool visualizer exposed on port 8080, which shows what is running on each node of the cluster. <br/><br/>SSH username: ubuntu

If the SSH username is not explicitly noted above, it is the default AWS AMI username, ec2-user.
