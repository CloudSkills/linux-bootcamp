# Lab 1: Create a Linux virtual machine with the Azure CLI

1. Launch Azure Cloud Shell
2. Create a resource group
3. Create virtual machine
4. Open port 80 for web traffic
5. Connect to virtual machine
6. Install web server
7. View the web server in action

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-cli

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart


# LEARNINGS FROM COMPLETING LAB ONE

## 1. LAUNCHING AZURE CLOUD SHELL
Azure cloud shell is an interactive, specially designed shell, that runs on the browser. It gives users access to the Azure Resource Manager, which can be used to configure all of the resources available on Azure Cloud.

It serves as an alternative to using the Azure console. You can choose if you would like to emulate either a Bash shell or a PowerShell while using the Azure Cloud Shell. 

### Using the cloud shell :-> Points noted.
1. To use the cloud shell, you should already have an azure subscription running. This means that it can also be classified as one of Azure's resources
2. To use the cloud shell you need to have a persistent disk. This volume retains data even after the power is turned off/ the container is destroyed.

# 2. CREATING AN AZURE RESOURCE GROUP
An azure resource group can be conceptualized as a folder which is used to group related, interdependent or logically linked Azure resources together.

When creating an Azure Resource Group, you need to specify the following:

1. The region you want the Resource Group to be located. 
2. The name of the Resource Group that is being created.

You can also add various resources you want, to be part of the Resource Group created.

*Please note that the reouseces present in a particular resource group should have a similar life cycle*

[Click here to view some of the learning resources consulted](https://www.alachisoft.com/resources/docs/ncache/containerization/azure/create-azure-resource-group.html)

# 3. CREATING A VIRTUAL MACHINE
An Azure Virtual Machine can be created using either the cloud shell or the Azure console. Which is the GUI we can see on the Azure Portal.

Using the Console, you can follow the following steps to create the Virtual Machine.

*Please note that this is also part of the subscription based plans on Azure, as you may be charged for creating Virtual Machines*

1. Select the create VIrtual MAchine option from the console.
2. Specify the image you want the Virtual Machine to run on, this can also be seen as the operating system of the Virtual box.
3. Specify the port you want for inbound traffic
4. Create your Public and private Key Pairs whuch you would use to access and configure your Virtual box
5. Create your virtual box


