# Lab 1: Install a LAMP stack on an Azure Linux VM

1. Create a resource group
2. Create a virtual machine
3. Open port 80 for web traffic
4. SSH into your VM
5. Install Apache, MySQL, and PHP
6. Install WordPress

### Notes:

Tutorial: Install a LAMP stack on an Azure Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-lamp-stack

Sample Gist
* https://gist.github.com/mikepfeiffer/96d659042f0575a617648a33c92b8f4a

Build and run a web application with the MEAN stack on an Azure Linux virtual machine
* https://docs.microsoft.com/en-us/learn/modules/build-a-web-app-with-mean-on-a-linux-vm/

MEAN Stack App
* https://github.com/MicrosoftDocs/mslearn-build-a-web-app-with-mean-on-a-linux-vm


# Things Learnt from Week 3 labs

## 1. Creating an Azure Resource Group

![Azure Logo](data:image/png;base64,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)


An Azure resource group can be conceptualized as a collection of Azure resources in a particular region. Resource groups are used to group related, interdependent or logically linked Azure resources together.

When creating an Azure Resource Group, you need to specify the following:

1. The region you want the Resource Group to be located. 
2. The name of the Resource Group that is being created.

You can also add various resources you want, to be part of the Resource Group created.

*Please note that the reouseces present in a particular resource group should have a similar life cycle*

[Click here to view some of the learning resources consulted](https://www.alachisoft.com/resources/docs/ncache/containerization/azure/create-azure-resource-group.html)


## 2. Creating a virtual machine
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

This command specifies the following:
1. The resource group you want your Azure VM to belong to
2. The image of your VM
3. The flag to generate your SSH keys
4. Your admin username.

## 3. Opening port 80 for web traffic.
Port 80 refers to the default port on the server uses for external web traffic connection. By default, your VM is set to prevent inbound traffic from the internet into your server. You can open the port to allow web traffic into the port.

&#x26A0; Kindly note that if your port 80 is not opened up to web traffic, no one can see the website hosted in your server.


## 4. SSH into your VM.
You can connect to your virtual machine using your local shell. This requires a Secure Shell Connection to an authorized port on your Virtual Box. For this, you usually need the SSH key and a local bash shell to connect to your VM securely.

## 5. Installing APACHE, MYSQL AND PHP.

1. **Installing Apache:** To install apache on your Linux server, you would have to use the command:

```
sudo apt-get update
sudo apt-get install apache2
```
2. **Installing MYSQL:**
mysql will serve as the data base for our wordpress site. to install my sql, you can use the following command:

```
sudo apt-get install mysql-server
```
after that, you install what would help you securely connect with your sql database. which is secure connection.
```
sudo mysql_secure_installation
```

&#x26A0;  Make sure you remember your login credentials to your SQL database


3. **Installing PHP My Admin:**
To install php, you would have to run the command on your shell:

```
sudo apt-get install php libapache2-mod-php php-mysql php-curl php-gd php-json php-zip

```

This would install php and all the associated libraries along with it.Once php is installed , you would need to restart apache.

To install php myadmin to your ubuntu server, you run the following command

```
sudo apt-get install phpmyadmin
```
&#x26A0;  Note that space-bar needs to be pressed to select the option and tab key is used to move to the Ok button.

![image showing the success installation of phpmyadmin](..\LAB1\images\php-myadmin.png)

## 6. Installing wordpress on the APACHE Server.
The Wordpress blog can be installed on the server by adding it to the host directory of your web server and installing it with your configurations. 

The following resource could be used as a guide for installing wordpress on your server.

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/hosting-wordpress.html

*image showing the successful installation of wordpress on the server*
![image showing the success installation of phpmyadmin](..\LAB1\images\wordpress-working.png)


*image showing the wordpress dashboard*
![image showing the success installation of phpmyadmin](..\LAB1\images\wordpress-dashboard.png)
