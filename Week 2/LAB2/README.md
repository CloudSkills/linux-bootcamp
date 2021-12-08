# Lab 2: Manage Linux VMs with the AWS CLI

1. Create virtual machine
2. Connect to VM
3. Understand VM images
4. Understand VM sizes
5. VM power states
6. Management tasks

### Notes:

Quickstart: Create a Linux VM
* https://aws.amazon.com/getting-started/launch-a-virtual-machine-B-0/

Using a custom Amazon machine image (AMI)
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.customenv.html

Quickstart: Restart VM via CLI
* https://docs.aws.amazon.com/cli/latest/reference/ec2/reboot-instances.html

Quickstart for AWS CloudShell
* https://docs.aws.amazon.com/cloudshell/latest/userguide/working-with-cloudshell.html


# Things learnt from completing Lab 2.

# 1. Creating a virtual machine.

You can create a virtual machine using the AWS CLI or using the AWS console.using the console is easier. Things to note while creating a VIrtual Machine:

1. You need to save your ssh key as a .pem file. Without it, you cannot securely access your server at a later time.

2. You can assign roles to your EC2 instances which specify how it can communicate with other AWS resources.

# 2 Connecting to the VM
To SSH to the virtual machine on AWS you need to know the location of your .pem file which contains your private key, and your public key address.

you run a bash script which allows you secure connection to your EC2 server instance.

# 3. Understanding AWS AMIs( Amazon Machine Images)

Amazon Machine IMages arefer to snapshots of EC2 instances and their current configurations. They are used to quickly spin up EC2 instances of the same hardware and software configurations, without any customization. They can be applied in AWS autoscaling groups to create a seamsless deployment of a new EC2 instance once the load from the Elastic Load balancer gets too much.

# 4. Understanding the EC2 sizes

# 4. Understanding the EC2 Power States