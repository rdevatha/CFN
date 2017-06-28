# CFN
I have put in the cloud formation templates, which I feel are basics in getting someone started with AWS. 
The flow I would recommend would be, 

1. Create the iam role ( edit out the values in the template, I had intentionally made changes to default values )
2. Create the security groups
3. Create the ELB
4. Create the instances. 

db-ec2instance.yaml template is made specifically for a use case. It assumes you have two snapshots ( one for data and another for log ), each with 50 Gib space. Also assumes snapshot is created from a volume which has a XFS file system. This template in turn would resize for future instances created using this template. 

General Assumptions : 
1. You should know your VPC id, Subnet id's, an AMI-ID. 
2. Know where you would open up port 22 from. 
3. For the load balancers port, as a general values I have opened up only ports 80, 8080, 443. ( change those if you need to access a different port )
4. Classic Load Balancer is used in the template. 
