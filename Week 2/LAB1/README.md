# Lab 1: Create a Linux virtual machine with the AWS CLI

1. Launch AWS Cloud Shell
3. Create virtual machine
4. Open port 80 for web traffic
5. Connect to virtual machine
6. Install web server
7. View the web server in action

### Notes:

Quickstart: Create a Linux VM
* https://aws.amazon.com/getting-started/launch-a-virtual-machine-B-0/

Quickstart for AWS CloudShell
* https://docs.aws.amazon.com/cloudshell/latest/userguide/working-with-cloudshell.html


# Things learnt from completing Lab 1

# 1 Launching AWS CLoud Shell

AWS cloud shell is a free shell environment provided with 1gb free of storage, which can be used to communicatet with your AWS resources via your browser. You do not need special configurations as most of the things you need to communicate with the AWS resources already exist within cloud shell.

# 2. Creating a Virtual Machine:
You can create a virtual machine using the AWS CLI or using the AWS console.using the console is easier. Things to note while creating a Virtual Machine:

1. You need to save your ssh key as a .pem file. Without it, you cannot securely access your server at a later time.

2. You can assign roles to your EC2 instances which specify how it can communicate with other AWS resources.

# 3. Opening Port 80 for Web traffic.
By default, port 80 is closed for web traffic. This means that normal users on the internet cnnot view the files hosted n your EC2 instance. It also means that if you install an APACHE server on your EC2 instance, the users of the internet would not be able to view the files. Hence, you need to open port 80 to allow web traffic.

# 4. SSH to the virtual machine.
To SSH to the virtual machine on AWS you need to know the location of your .pem file which contains your private key, and your public key address.

you run a bash script which allows you secure connection to your EC2 server instance.

# 5. Installing a webserver on AWS EC2
Installing a webserver on an EC2 instance can be accomplished in a similar way to Azure, by instlling APACHE server to it.

# 6. Viewing the Webserver in action:

 To view the webserver in action, you need to use the public ip address of your EC2 instance. You would be able to see the APACHE homepage which is server by the Apache server.