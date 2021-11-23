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

1. ### Supported SSH key formats
Azure currently supports SSH protocol 2 (SSH-2) RSA public-private key pairs with a minimum length of 2048 bits. Other key formats such as `ED25519` and `ECDSA` are not supported.

2. ### Create an SSH key pair
Use the `ssh-keygen` command to generate SSH public and private key files. By default, these files are created in the ~/.ssh directory. You can specify a different location, and an optional password (passphrase) to access the private key file. If an SSH key pair with the same name exists in the given location, those files are overwritten.

The following command creates an SSH key pair using RSA encryption and a bit length of 4096:

> Here is the input code for creating an SSH key pair using RSA encryption:

```
ssh-keygen -m PEM -t rsa -b 4096
```
> Here is the output with the randomart image:

```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/tega/.ssh/id_rsa): tukeypair
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in tukeypair.
Your public key has been saved in tukeypair.pub.
The key fingerprint is:
SHA256:n6agf9i9+nQuk7Z1SCIRGP90TVj2w9DrRxP4vVHirfk tega@cc-4224239c-6d77fcf57-kbmrg
The key's randomart image is:
+---[RSA 4096]----+
|      .o.    +*  |
|      .. .  .=++.|
|        o . ..o=*|
|         + .  .==|
|        S o . .++|
|         o + .oo.|
|      .o .=.+ ...|
|     ...o+*+ .  E|
|    ....o++=.    |
+----[SHA256]-----+
```

3. ### Provide an SSH public key when deploying a VM
Code input:

To display my public key, I used the `cat` command.
```
cat tukeypair.pub
```

> Here is the output code for creating my virtual machine:

```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQC5OnFcbE+0bNAz044SCVxuOqcXfywLV6lnY2IiJ3YE6KhHtLo4yB+7+1M9YXa2Yvl/nvphYwGVWkdwXHwnJUtVO1JUCq6kE0H/HAeGEHVqC9lJcLsRHnIKfB0EBxvBuNKZN5ibwPKUGy2pNpVLEh1xUQrso1QLB++pVILSF3ly5ji+qhb0Okk8bZ7e2JMEg22llrJ2ThuthtcuICan7UUDqJoV4Zhu3qZXEd/fbjdif1IoNVfAy/XqRgO37orydanuW4XdftnogvV+nVicxMH1mYvMoPnh14DfjmURvsq8wm1lDIY/3pjG7obPD/dDQ17Ycp+sTQyGX4E3DKqt/mJbgr0FwJo5mbUghxfNeYnBXax2ExcYMf0VI6lDEj8jjytOoGOqNQPMicwMYzBBQ72FIoroNJfpAvd/slQzYQ05R5YC9tt8K8j6Isq8G/tm42EQovvYLdOM7KLX8KAE5H2iUvIpEu5NVpjz0+ECFSfjdHELfJw0KU9I/FERjl0CgEbrln6HYE7xxh8q6uuZf+Tg6c8X/ObEGLTkvyjl/vbFwkOpkdnvq6n/czQ7ZShqVB7l/XHiBgA67v4tGJ4bjC7MPONYCS55ub9cHcPKD7DVOL/cUYoMyozCc4cO0cnkodfSaRgjY6sENViAQb6bOzL8BG7g+LfoClRsh45cKHDdQw== tega@cc-4224239c-6d77fcf57-kbmrg
```
* To Provide the SSH public key when deploying a VM, provide the `--ssh-key-values` where the public key files is

> Code input:

```
az vm create  
--resource-group MyResourcegroupdisk --name tegasVM --image UbuntuLTS --admin-username tega --ssh-key-values tukeypair.pub
```

> Here is the output code:

```
{
  "fqdns": "",
  "id": "/subscriptions/b5549425-9749-48f8-8db1-e22c7d47472d/resourceGroups/MyResourcegroupdisk/providers/Microsoft.Compute/virtualMachines/tegasVM",
  "location": "eastus",
  "macAddress": "00-0D-3A-8B-D0-68",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.4",
  "publicIpAddress": "20.124.99.169",
  "resourceGroup": "MyResourcegroupdisk",
  "zones": ""
}
```

4. ### SSH into your VM

Code input:

SSH into my VM using the public IP Address.
```
ssh -i tukeypair tega@20.124.99.169
```

> Here is the output code for creating my virtual machine:

```
The authenticity of host '20.120.80.158 (20.120.80.158)' can't be established.
ECDSA key fingerprint is SHA256:IBYnAJMlmhe/xojAT4OiH18rngF33zmJ57Wkw3Gy6eo.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '20.120.80.158' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.6 LTS (GNU/Linux 5.4.0-1063-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 19 10:55:19 UTC 2021

  System load:  0.0               Processes:           108
  Usage of /:   4.7% of 28.90GB   Users logged in:     0
  Memory usage: 5%                IP address for eth0: 10.0.0.4
  Swap usage:   0%

0 updates can be applied immediately.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.
```
> Here is a screenshot of the apache2 web server in action after opening port 80:

![apache2 web server](images/apache2.png)
