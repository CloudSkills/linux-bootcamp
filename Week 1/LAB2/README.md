# Lab 2: Manage Linux VMs with the Azure CLI

1. Create resource group
2. Create virtual machine
3. Connect to VM
4. Understand VM images
5. Understand VM sizes
6. VM power states
7. Management tasks

### Notes:

Quickstart: Create a Linux VM

- https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm

Quickstart for Bash in Azure Cloud Shell

- https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart

# 1. CREATING A RESOURCE GROUP

Resource groups are groups of azure cloud resources which have the same life cycle and are logically linked to gether. To create a resource group using the cloud shell, the followng commands were run:->
az group create --name demoResourceGroup --location westus

```
az group create --name demoResourceGroup --location westus
}
```

# 2. Creating a Virtual Machine

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

# 3 Connecting to the VM

Usually, you can connect to your virtual machine using your local chell. This requires a Secure Shell Connection to an authorized port on your Virtual Box. For this, you usually need the SSH key and a local bash shell to connect to your VM securely

# 4. Understanding VM images.

VM images refer to several operating systems that can be run on a virtual machine. Examples include CentOS, Windows Server OS, Kali, Ubuntu.
To see the full list of VM images that you can run on your VM, you use the following command

```
az vm image list
```

# 5. Understanding VM image sizes

The VMimage sizes refer to the different sizes of the operating systm, and the minum requirements they need to run on the system. They show the power to memory ratio of the VM image

# 6. Understanding VM power states

The VM power states include the current operating state of the virtual machine. it can either be:

1. Starting: Indicates that the VM is being started.
2. Running: Indicates that the VM is running.
3. Stopping: Indicates that the VM is being stopped.
4. Stopped: Indicates that the VM is stopped. ...
5. Deallocating: Indicates that the VM is being deallocated

# 7. Management tasks

Management refers to the tasks and processes required to maintain your business applications and the resources that support them. Azure has many services and tools that work together to provide complete management. These services aren't only for resources in Azure, but also in other clouds and on-premises. Understanding the different tools and how they work together is the first step in designing a complete management environment.

They include:

1. Govern
2. Secure
3. Configure
4. Monitor
5. Protect
