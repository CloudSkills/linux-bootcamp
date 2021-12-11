# Lab 2: Install a LAMP stack on an Azure Linux VM

1. Prepare the LAMP server
2. Test your Lamp server
3. Secure the database server
4. (Optional) Install phpMyAdmin

### Notes:

Tutorial: Install a LAMP web server on the Amazon Linux AMI
* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/install-LAMP.html

Tutorial: Host a WordPress blog on Amazon Linux 2
* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/hosting-wordpress.html

Sample Gist
* https://gist.github.com/mikepfeiffer/c079608703e604224e58a3d40d0fa043#file-lamp-linux-aws-sh

# Things learnt from completing Lab 2

## 1. Preparing the LAMP server.
The LAMP server refers to a Linux, APACHE MYSQL and PHP server. This is a standard application stack for building most fullstack applications.

The LAMP server was set up using an EC2 instance, running on an Amazon Linux 2.

First of all, after the instance was created, updates were installed on the server using the following code:

```
sudo yum update -y
```


To prepare the LAMP server, the following code was run to check install the updated version of the required applications on the EC2 instance.

```
sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
```

## 2. Testing the LAMP server
Once APACHE is intalled on the server, you can be sure that the server is up and running, by copying and pasting the public IP address of your EC2 instance into your browser.

This should show you the APACHE test page as shown below:

![Apache Test Page shown to confirm that the instance has the apache server running](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/apache_test_page_al2_2.4.png)

## 3. Securing the database server.
The database server which was installed is the mysql server. to secure the server means to place additional authentication requirements before someone can make connections to the database. A package can help you to establish a secure connection with your MY SQL server.

```
sudo mysql_secure_installation
```

## 4. Installing PHP myAdmin
PHP myAdmin helps in the database administration. It helps you to visually view the files stored in your database server all from a browers based program.

To install php myadmin, you can run hte following lines of code:

```
sudo yum install php-mbstring php-xml -y
```
This installs PHP myAdmin and its required dependencies.

*here is a screenshot showing the successful installation of php my admin*

![image showing the final installation screen for phpmyAdmin](..\LAB1\images\php-myadmin.png)