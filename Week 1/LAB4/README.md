# Lab 4: Create and use an SSH public-private key pair for Linux VMs in Azure

1. Supported SSH key formats
2. Create an SSH key pair
3. Provide an SSH public key when deploying a VM
4. SSH into your VM

### Notes:

# ANSWERS TO WEEK 1 LAB 4

1. Supported SSH key formats

Azure currently supports SSH protocol 2 (SSH-2) RSA public-private key pairs with a minimum length of 2048 bits. Other key formats such as ED25519 and ECDSA are not supported.

2. Creating an SSH public pair.

on my cloudshell I created ssh public pair by running the following commad:
 az vm create --name HarryVM --resource-group HarryVM_group --image UbuntuLTS --generate-ssh-keys

 3. 


Quickstart: SSH for Linux VMs
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/mac-create-ssh-keys

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart