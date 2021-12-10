# Lab 1: Install a LAMP stack on an Azure Linux VM

1. Create a resource group
2. Create a virtual machine
3. Open port 80 for web traffic
4. SSH into your VM
5. Install Apache, MySQL, and PHP
6. Install WordPress

### Notes:

Tutorial: Install a LAMP stack on an Azure Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-lamp-stack

Sample Gist
* https://gist.github.com/mikepfeiffer/96d659042f0575a617648a33c92b8f4a

Build and run a web application with the MEAN stack on an Azure Linux virtual machine
* https://docs.microsoft.com/en-us/learn/modules/build-a-web-app-with-mean-on-a-linux-vm/

MEAN Stack App
* https://github.com/MicrosoftDocs/mslearn-build-a-web-app-with-mean-on-a-linux-vm


# Things Learnt From Week 3 labs

# 1. Creating a resource group
An azure resource group can be conceptualized as a folder which is used to group related, interdependent or logically linked Azure resources together.

When creating an Azure Resource Group, you need to specify the following:

1. The region you want the Resource Group to be located. 
2. The name of the Resource Group that is being created.

You can also add various resources you want, to be part of the Resource Group created.

*Please note that the reouseces present in a particular resource group should have a similar life cycle*

[Click here to view some of the learning resources consulted](https://www.alachisoft.com/resources/docs/ncache/containerization/azure/create-azure-resource-group.html)


# 2. Creating a virtual machine
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

# 3. Opening port 80 for web traffic.
Port 80 refers to the default port on the server uses for external web traffic connection By default, it is sclodes to prevent inbound traffic from the internet into your server. You can open the port to allow web traffic into the port.
