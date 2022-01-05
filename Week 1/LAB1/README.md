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
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstar

 **Create a Linux virtual machine with the Azure CLI**

I created a new folder on my desktop named: GITHUB_LOCAL_REPO
I downloaded Git bash on my desktop through google engine
I opened the Git Bash by right clicking on my mouse to click on GIT BASH HERE
GIT BASH TERMINAL will display Ismail-Schull tech@DESKTOP-3Q4EMU4 MINGW64 ~/Desktop/SCHULL TECH/GITHUB_LOCAL_ REPO/linux-bootcamp/linux-bootcamp (main)

And I input git init
it display Reinitialized existing Git repository in C:/Users/Ismail-Schull tech/Desktop/SCHULL TECH/GITHUB_LOCAL_ REPO/linux-bootcamp/linux-bootcamp/.git/

Then I input git clone and copy mikeplifer's code on his github platform in front it 
And 
display $ git clone https://github.com/CloudSkills/linux-bootcamp.git
fatal: destination path 'linux-bootcamp' already exists and is not an empty directory.
I have all the weeks assignment in my personal folder now.

I forked mikeplifer's to my own github account.
Thank you.





FOR LAB1 ASSIGNMENT


**1. Launch Azure Cloud Shell**

I log into portal.azure.com

and it load the azure microsoft page
I clicked on the Cloudshell icon by the top right hand side

and it displayed Cloudshell terminal. I clicked on the BASH icon and the terminal was displayed successfully.


**2. Create a resource group**

I type into the bash cloudshell az group create --resource-group abiodexlab1 --location eastus

the resource group was successfully created.


**3. Create virtual machine**

I typed az vm create --resource-group abiodexlab1 --name abioweb --image ununtults --generate-ssh-keys --admin username ismail

and it load successfully.




**4. Open port 80 for web traffic**

I typed az vm open port --port 80 --resource-group abiodexlab1 --name abioweb

and it loaded successfully. 


**5. Connect to virtual machine**


I typed ssh ismail@20.102.72.223 and it was connected to the virtual machine


**6. Install web server**
I typed sudo apt-get -y update and it was updated


then, i typed sudo apt-get -y install nginx and ngnix was installed.


**7. View the web server in action**

I copied my pubic Ip address 20.102.72.223 and it displayed that my nginx was successfully installed.

Thank you.


