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


### Create Resource Group
 az group create --name FirstResourceGroup --location eastus
 
 ### Create VM
 az vm create \
>   --resource-group FirstResourceGroup \
>   --name muyiwaVM \
>   --image UbuntuLTS \
>   --admin-username muyiwa \
>   --generate-ssh-keys

### Output
{
  "fqdns": "",
  "id": "/subscriptions/bc6996bb-6218-4ff9-8b22-caf9b8903a23/resourceGroups/FirstResourceGroup/providers/Microsoft.Compute/virtualMachines/VM1",
  "location": "eastus",
  "macAddress": "00-22-48-21-46-45",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.4",
  "publicIpAddress": "20.106.133.238",
  "resourceGroup": "FirstResourceGroup",
  "zones": ""
}

### Open port 80 for web traffic

az vm open-port --port 80 --resource-group FirstResourceGroup --name muyiwaVM

### Connect SSH to VM

ssh muyiwa@20.106.133.238


### Install Web Server

sudo apt-get -y update
sudo apt-get -y install nginx
