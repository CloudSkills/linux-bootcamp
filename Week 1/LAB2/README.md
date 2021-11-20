# Lab 2: Manage Linux VMs with the Azure CLI

1. Create resource group
2. Create virtual machine
3. Connect to VM
4. Understand VM images
5. Understand VM sizes
6. VM power states
7. Management tasks

### Notes:

# ANSWERS TO MY WEEK1 LAB2

I created a Resource Group, VM and connected to my VM as shown in lab1 above.

4. UNDERSTANDING VM IMAGES

 In one sentence, you can think of VM Images as a more comprehensive image for Microsoft Azure Virtual Machines.  The new and improved VM Image encompasses the full definition of a virtual machine’s storage, containing the OS disk and all data disks. 
 
  It captures the disk properties (such as host caching) you need in order to deploy a VM in a reusable unit.  Similar to OS Images, a VM Image is a collection of metadata and pointers to a set of VHDs (one VHD per disk) stored as page blobs in Azure Storage.

 A VM Image containing a single VHD with a generalized operating system is essentially the OS image you are familiar with today.  Over time, you will notice that VM Images will become the main image construct for Microsoft Azure Virtual Machines. 
 
 There are two types of VM Images – generalized and specialized – each serving their own purpose.  A generalized VM Image contains an OS disk, which, as the name suggests, has been generalized (for Windows, you have run Sysprep and for Linux, you have executed ‘waagent –deprovision’) and needs to be provisioned during deployment time.  OS Images today are generalized.  This type of VM Image is meant to be used as a “model” to quickly stamp out similar virtual machines, such as scaling out a front-end to your application in production or spinning up and tearing down similar development and test environments quickly. 
 
 A specialized VM Image contains an OS disk, which is already provisioned.  It is similar to a disk today in that it is “ready-to-use”, but unlike a disk, the VHDs of a VM Image are treated as read-only and copied when deploying a new virtual machine.  A specialized VM Image is meant to be used as a “snapshot” to deploy a VM to a good known point in time, such as checkpointing a developer machine, before performing a task which may go wrong and render the virtual machine useless.  It is not meant to be a mechanism to clone multiple identical virtual machines in the same virtual network due to the Windows requirement of Sysprep for image replication.


 5. UNDERSTANDING VM SIZES

 Virtual machine size basically defines the amount of resources it could consume. The machine size defines the number of CPU cores, memory size, temporary disk size, etc. The size of the virtual machine can be changed anytime, even after the machine is deployed.

The cost of the size may change within different locations/regions. A region is the geographic area grouping data centers in that location. It gives users the ability to run applications where needed.

WE HAVE SIX TYPES OF VM SIZES WHICH ARE:

1. General purpose	B,
 Dsv3, Dv3, Dasv4, Dav4, DSv2, Dv2, Av2, DC, DCv2, Dv4, Dsv4, Ddv4, Ddsv4, Dv5, Dsv5, Ddv5, Ddsv5, Dasv5, Dadsv5.
 
 FUNCTION: Balanced CPU-to-memory ratio. Ideal for testing and development, small to medium databases, and low to medium traffic web servers.

2. Compute optimized	
F, Fs, Fsv2.

FUNCTIONS:
 FX	High CPU-to-memory ratio. Good for medium traffic web servers, network appliances, batch processes, and application servers.


3. Memory optimized
Esv3, Ev3, Easv4, Eav4, Ev4, Esv4, Edv4, Edsv4, Ev5, Esv5, Edv5, Edsv5, Easv5, Eadsv5, Mv2, M, DSv2, Dv2

FUNCTIONS:
High memory-to-CPU ratio. Great for relational database servers, medium to large caches, and in-memory analytics.

4. Storage optimized
Lsv2	

FUNCTIONS:
High disk throughput and IO ideal for Big Data, SQL, NoSQL databases, data warehousing and large transactional databases.

5. GPU	
NC, NCv2, NCv3, NCasT4_v3, ND, NDv2, NV, NVv3, NVv4, NDasrA100_v4, NDm_A100_v4	

FUNCTIONS:
Specialized virtual machines targeted for heavy graphic rendering and video editing, as well as model training and inferencing (ND) with deep learning. Available with single or multiple GPUs.

6. High performance compute	
HB, HBv2, HBv3, HC, H	

FUNCTIONS:
Our fastest and most powerful CPU virtual machines with optional high-throughput network interfaces (RDMA).

6. UNDERSTANDING VM POWER STATES

VM POWER STATES are simply different power phases that a VM can exisit, we have 6 types of power states which indicates entirely different states of the VM.

There are six power states that a VM can exist in:

1. Starting: Indicates that the VM is being started.
2. Running: Indicates that the VM is running.
3. Stopping: Indicates that the VM is being stopped.
4. Stopped: Indicates that the VM is stopped. Note that VMs in the stopped state still incur compute charges.
5. Deallocating: Indicates that the VM is being deallocated.
6. Deallocated: Indicates that the VM is completely removed from the hypervisor.

7. MANAGEMENT TASKS





Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart