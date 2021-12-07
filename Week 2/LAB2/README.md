# Lab 2: Manage Linux VMs with the AWS CLI

1. Create virtual machine
2. Connect to VM
3. Understand VM images
4. Understand VM sizes
5. VM power states
6. Management tasks

### Notes:

## 1. Create virtual machine
> Code input
```
aws ec2 run-instances
--image-id ami-0d718c3d715cec4a7
--instance-type t2.micro
--key-name pirumkey
```
## 2. Connect to VM
* On the aws portal, connect into the VM using an SSH Client.
* Give permission with inputting `chmod 400 pirumkey.pem` into the ssh client terminal
* Input this next `ssh -i "pirumkey.pem" ec2-user@172.31.7.224`
* Provide `ECDSA-key` from windows prompt. Give permission and successfully connect into the VM

## 3. Understand VM images
#### Creating a custom Amazon Machine Image (AMI):
* Launch and instance and select Community AMI
* Select an AMI and configure the instance
* Connect the instance with SSH
* In the Amazon EC2 console, stop the EC2 instance. Then on the Instance Actions menu, choose Create Image (EBS AMI).

#### To use your custom AMI in an Elastic Beanstalk environment

* Open the Elastic Beanstalk console
* In the navigation pane, choose **Environments**
* In the navigation pane, choose **Configuration.**
* In the **Capacity** configuration category, choose **Edit.**
* For **AMI ID**, enter your custom AMI ID. `ami-026683b6e50b73b60`
* Choose **Apply.**
> Scrrenshot of Instance created in Elastic Beanstalk Console with Custom image.

![Custom image instance](images/Customami.png)


Quickstart: Create a Linux VM
* https://aws.amazon.com/getting-started/launch-a-virtual-machine-B-0/

Using a custom Amazon machine image (AMI)
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.customenv.html

Quickstart: Restart VM via CLI
* https://docs.aws.amazon.com/cli/latest/reference/ec2/reboot-instances.html

Quickstart for AWS CloudShell
* https://docs.aws.amazon.com/cloudshell/latest/userguide/working-with-cloudshell.html
