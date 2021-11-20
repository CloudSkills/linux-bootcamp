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


**ANSWERS TO MY WEEK1 LAB1**
1. launching Azure Cloudshell
# Definition: 
Azure Cloud Shell is a shell used to manage and develope Resources.
i launched Azure Cloud Shell by clicking on the square with a "greater than" sign at the top right side of my Azure portal, a new environment opened up for me to type in my command after running some connections.

2. Creating a Resource group
# Definition
Resource Group is a tool that holds related related resources for an Azure solution.

I created a resource group by entering the following command in my Cloud Shell:
az group create -- HarryVM_group -- location eastus

3. Creating a Virtual Machin
# Definition: 
Virtual Machines are computer files typically called an image which behaves like an actual computer, it is one of the files which contains everything and runs in Windows, Linux etc.

I created my Virtual Machine by running the following command on my Cloud Shell:

az vm create \
--resource-group HarryVM_group \
--name HarryVM \
--image UbuntuLTS \
--admin-username Harry \
--generate-ssh-keys

4. Opening port 80 for web traffic

I opened port 80 on cloud Shell by running th below command:

az vm open-port --port 80 --resource-group HarryVM_group --name HarryVM

5. Connecting to my Virtual Machine

I connected to my Virtual Machine using the below command on my cloud shell:

ssh Harry@40.68.254.142

6. Web Server Installation

To install my Web Server I ran the following command:

sudo apt-get -y update
sudo apt-get -y install nginx





