<b>Holiday Challenge</b>

You are required to perform the following tasks

1. Set up 2 EC2 instances on AWS(use the free tier instances).
2. Deploy an Nginx web server on these instances(you are free to use Ansible)
3. Set up an ALB(Application Load balancer) to route requests to your EC2 instances
4. Make sure that each server displays its own Hostname or IP address. You can use any programming language of your choice to display this.
5. Work on building a personal portfolio and CV (Check out resumeworded.com).

Important points to note:

1. I should not be able to access your web servers through their respective IP addresses. Access must be only via the load balancer
2. You should define a logical network on the cloud for your servers.
Your EC2 instances must be launched in a private network.
3. Your Instances should not be assigned public IP addresses.
4. You may or may not set up auto scaling(I advice you do for knowledge sake)
5. You must submit a custom domain name(from a domain provider e.g. Route53) or the ALB’s domain name.

<b>Solution</b>
1. Create a Logical Network
 - Create an Amazon Virtual Private Cloud (VPC)
 - Create 2 public subnet and a private subnet
 - Create an Internet Gateway and attach it to the VPC
 - Create 2 route table (private and public) and associate the public RT to the public subnets, and private rt to the private subnet
 - Create a route in the public route table to direct internet-bound traffic to the Internet Gateway with leaving the private table on local

 2. Create 2 private EC2 instances
 - Create 2 EC2 instances in the private subnet with our VPC
 - Create a security group for the EC2 instances and allow SSH only from within the network
 - Create/attach a key pair for the EC2 instances

3. Create a Bastion & NAT instance
 - Create a Bastion instance in the public subnet with our VPC
 - Create a security group for the Bastion instance and allow SSH only from within your network
 - Create/attach a key pair for the Bastion instance
 - Create a NAT instance in the public subnet with our VPC
 - Create a security group for the NAT instance and allow SSH & HTTP only from within the network
 - Create/attach a key pair for the NAT instance
 - Create a route in the private route table to direct internet-bound traffic to the NAT instance
 
 The Bastion is supposed to be the only instance that can be accessed from the internet snd serve as a jump start for the the two private Ec2. The NAT instance is used to allow the private instances to access the internet.

4. Create an ALB
 - Create an ALB in the public subnet with our VPC
 - Create a security group for the ALB and allow HTTP only from for everyone
 - Create a target group for the ALB
 - Create a listener for the ALB
 - Register the private instances to the target group

5. Deploy an Nginx web server and php using Ansible
   - Create an ansible playbook to install nginx and php on the private instances
   - Create a playbook to deploy a simple php script that displays the hostname of the instance
   - Create a playbook to configure the nginx server to serve the php script

6. Create a custom domain name
 - Create a hosted zone in Route53
 - Create a record set for the ALB
