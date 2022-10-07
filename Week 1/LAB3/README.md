# Lab 3: Manage Azure disks with the Azure CLI

1. Default Azure disks
2. Azure data disks
3. VM disk types
4. Launch Azure Cloud Shell
5. Create and attach disks
6. Prepare data disks
7. Take a disk snapshot

### Notes:

Quickstart: Manage Azure disks
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-disks

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart


# Things learned from performing Lab 3: Manage Azure disks with the Azure CLI


# 1. Default data disks with Azure
These are teh default data disks which are attched to an AZ VM instance once it is created.
Two disks are usually attahced:
1. Operating system disks:-> This can be up to 2TB in size and it usually hosts the operatinig system of the virtual machine.

It is labelled /dev/sda by default

The OS dik is optimized caching OS performance. The OS disk should not be used for application or data

2. TEmporary disks:-> These are default ssds that are allocated to the same Azure hosts as teh VM. The disks are highly performat and used for temporary data processing opeations. 
```
If the VM host is removed, data stored on teh temproray sisks is removed
```

THe size of the temporary disk is determined by the VM size

# 2. Azure data disks
To install and store data on your VM, additional data disks have to be created. THe size of the VM determines the amount of the disks that can be attached.

# 3. VM disk types
Azure provides tw types of disks that can be attached:->
Standard disks and Premium disks
1. Standards disks can be attached and used for development and testing purposes
2. Premium disks can be perfect for VMs running production workload. THey are backed up by Premium SSDs with low latenchy. e.g
DS series, DSv-series Gseries

# 5. Attaching a disk to a VM
TO attach a disk to a VM, you use the VM disk attach command. Mind you that after you attach the sisk to the VM, you need to prepare it before you can use it.

# 6. Preparing a data disk
TO prepare a data disk, you need to ssh to your local shell, and partition the drive, and prepare the operating system using partitions

# 7.Taking a snapshot of data disks:
Snapshots are usually taken to ensure a backup of the current state of the drive, and files present, before additional confihurations are made. This is to proveide an image to roll-over to incase an error occurs during a configuration 


