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
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm

### Step 1: Create a Resource Group.
> Here is the input code for creating my resource group:

```
az group create --location eastus --name MyResourceGroupVM
```
> Here is the output code for creating a resource group:

```
{
  "id": "/subscriptions/b5549425-9749-48f8-8db1-e22c7d47472d/resourceGroups/myResourceGroupVM",
  "location": "eastus",
  "managedBy": null,
  "name": "myResourceGroupVM",
  "properties": {
    "provisioningState": "Succeeded"
  },
  "tags": null,
  "type": "Microsoft.Resources/resourceGroups"
}
```


### Step 2: Create a VM
Code input:
```
az vm create
--resource-group myResourceGroupVM
--name tegasVM
--image UbuntuLTS
--admin-username tega
--generate-ssh-keys
```

> Here is the output code for creating my virtual machine:

```
{
  "fqdns": "",
  "id": "/subscriptions/b5549425-9749-48f8-8db1-e22c7d47472d/resourceGroups/myResourceGroup/providers/Microsoft.Compute/virtualMachines/tegasVM",
  "location": "eastus",
  "macAddress": "00-0D-3A-52-F7-64",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.4",
  "publicIpAddress": "52.191.113.133",
  "resourceGroup": "myResourceGroup",
  "zones": ""
}
```
### Step 3: Create a VM with a specific VM image
Code input:
```
az vm create
--resource-group myResourceGroupVM
--name tegasVM
--image OpenLogic:CentOS:7.5:latest
--generate-ssh-keys
```

> Here is the output codee:

```
{
  "fqdns": "",
  "id": "/subscriptions/b5549425-9749-48f8-8db1-e22c7d47472d/resourceGroups/myResourceGroupVM/providers/Microsoft.Compute/virtualMachines/tegasVM",
  "location": "eastus",
  "macAddress": "00-22-48-28-FB-C3",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.5",
  "publicIpAddress": "52.170.102.44",
  "resourceGroup": "myResourceGroupVM",
  "zones": ""
}
```

### Step 4: Create a VM with a specific VM Size
Code input:
```
az vm create
--resource-group myResourceGroupVM
--name myVM3
--image UbuntuLTS
--size Standard_D2_v2
--generate-ssh-keys
```

> Here is the output code:

```
{
  "fqdns": "",
  "id": "/subscriptions/b5549425-9749-48f8-8db1-e22c7d47472d/resourceGroups/myResourceGroupVM/providers/Microsoft.Compute/virtualMachines/myVM3",
  "location": "eastus",
  "macAddress": "00-0D-3A-14-21-08",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.4",
  "publicIpAddress": "13.82.83.216",
  "resourceGroup": "myResourceGroupVM",
  "zones": ""
}
```

### Step 5: Resize a VM
1. To show the size of my VM:

> Code input:

```
az vm show --resource-group myResourceGroupVM --name tegasVM --query hardwareProfile.vmSize
```

> Here is the output:

```
"Standard_DS1_v2"
```


2. To Change to size of my VM to available size options:
> Code input:

```
az vm resize --resource-group myResourceGroupVM --name tegasVM --size "Standard_B1ms"
```

> Here is a partial output:

```
{
  "additionalCapabilities": null,
  "applicationProfile": null,
  "availabilitySet": null,
  "billingProfile": null,
  "capacityReservation": null,
  "diagnosticsProfile": null,
  "evictionPolicy": null,
  "extendedLocation": null,
  "extensionsTimeBudget": null,
  "hardwareProfile": {
    "vmSize": "Standard_B1ms",
    "vmSizeProperties": null
  },

  },
  "tags": {},
  "type": "Microsoft.Compute/virtualMachines",
  "userData": null,
  "virtualMachineScaleSet": null,
  "vmId": "ab10b743-bffc-426d-afc6-259fd69282aa",
  "zones": null
}
```

## View and Understand VM States

#### To find the current powerstate  of my VM:

>input

```
az vm get-instance-view
--name tegasVM
--resource-group myResourceGroupVM
--query instanceView.statuses[1] --output table
```
>output

```
Code                Level    DisplayStatus
------------------  -------  ---------------
PowerState/running  Info     VM running
```
#### To get IP address:
>input

```
az vm list-ip-addresses --resource-group myResourceGroupVM --name tegasVM --output table
```
>output

```
PowerState/running  Info     VM running
tega@Azure:~$ az vm list-ip-addresses --resource-group myResourceGroupVM --name tegasVM --output table
VirtualMachine    PublicIPAddresses    PrivateIPAddresses
----------------  -------------------  --------------------
tegasVM           52.170.102.44        10.0.0.5
```
