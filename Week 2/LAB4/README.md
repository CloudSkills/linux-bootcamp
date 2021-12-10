# Lab 4: Manage Packages and Services on a Linux VM (Azure or AWS)

1. Create a Linux VM
2. Install the Apache Web Server
3. Start the service status via command line
4. Investigate the service status via command line
5. Stop the service 

Challenge: Create a boostrapping script that will install and start this service on new EC2 VMs

### Notes:

Install and Configure Apache (Ubuntu)
* https://ubuntu.com/tutorials/install-and-configure-apache#1-overview

How to install Apache on RHEL 8 / CentOS 8 Linux
* https://linuxconfig.org/installing-apache-on-linux-redhat-8

How to use cloud-init to customize a Linux virtual machine in Azure on first boot
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-automate-vm-deployment

Create bootstrap actions to install additional software
* https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html


# Things Learnt from finishing Lab 4

# 1. Creating a VM.
A Virtual Machine is a single compute instance on the AZURE CLOUD. A virtual machine gives you hardware and Operating software resources to run your application.
To create a VM you use the following command

```
az vm create \
  --resource-group myResourceGroup \
  --name myVM \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys
```

# 2. Installing the Apache webserver.
The Apache web server can be installed using a remote SSH connection between your pc and your linux instance.

You run the following lines of code:

```
sudo apt-get update
sudo apt-get install apache2
```

once these commands are done, you can paste the public IP address in your browser to see your VM instance.

# 3. Starting the Azure VM command:
To start the stopped Azure VM using Az CLI, we can use the az vm start command. 

```
 az vm start -n vmname -g RGname --verbose
```

# 4. Investigate the service Status usng command line.

To investigate the service status, we can use cloud shell. This tells us the state of all our VMs / resources which have been created.

the following command can be used to get the service status

```
get-azvm -status

```

# 5. To stop the service
You can stop your virtual machine using the Azure cloud shell powershell command line.

to stop your service you can run the command:

```
az vm stop -n cloudskillsserver -g cloudskillsRG --verbose
```

Note that your stopped server would still be billed in Azure, So you have to deallocate it.


