# Lab 4: Create and use an SSH public-private key pair for Linux VMs in Azure

1. Supported SSH key formats
2. Create an SSH key pair
3. Provide an SSH public key when deploying a VM
4. SSH into your VM

### Notes:

Quickstart: SSH for Linux VMs
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/mac-create-ssh-keys

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart

# Learnings From Lab 4

# 1. Supported Key Pair formats.
Azure usually use key par arrangements to secure VMs, as they provide better protections against Brute force attaks than regular passwords.

The Key pair formats that azure currently supports include:
1. SSH protocol 2 (SSH-2) RSA public-private key pairs with a minimum length of 2048 bits.

Kindly note that Azure does not support formats such as ED25 and ECDSA for ssh keys

# 2. Creating an SSH Key Pair
An ssh key pair can be created using the  --generate-ssh-key flag at the point you are creating your VM insyance, or you can use Putty or any other SSH tools to create your key pair.

If you run the --generate-ssh-key pair command, your defaul ssh key would be stored in the ~/.ssh/id_rsa.pub file

To view the file, you would have to use the command

```
cat ~/.ssh/id_rsa.pub
```


# 3. Provide an SSH public Key when providing a VM.

When you are deploying a VM, you can specify an SSH pubic key you want, by using the --ssh-key-pair flag and specifyig the name of the ksy pair you want to use to lock up you VM.

# 4. SSHing into your VM.

TO ssh into the VM you created, you would need to have access to the private key file/ the public key file. Tis can either be on your local computer, or attached to your cloud storage.

If you do not have access to the ssh private key, you would not be able to securely connect toy your VM.

Connecting to the VM using the command :->

```
ssh -i id_rsa.pub azureuser@16.123.123.4
```

this would securely connect you to the VM instance using the cloud sheel. After that, you can install your server, and also your updates.


