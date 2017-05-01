# BSC1Jproject1
Name- shiva kc 
id no - 17724
Table of contents

S.No.                       Topic                                                                           page
1.                 Introduction……………………………………………………2
2.                Steps outlined for Virtual machine…………………………….2
3.                Installation of Apache web server and MySQL………………..5
4.                Installation of PHP and Modules……………………………....5
5.                Conclusion……………………………………………………..6
6.                References……………………………………………………..6
























1.	Introduction:
The purpose of this report is to give a description of virtualisation and virtual box and outlining the steps involved in configuration and deployment of virtual machine by further explaining the settings and configuration selected. In addition, it will explain what of what an web server and apache is including the steps outlined. Upon Completion of the project it will look into reflection, recommendation and conclusion. All the steps are in a random order.

Virtualisation:

It refers to the term which is used to create a virtual version of a device such as a server, network, storage where framework divides resource into one or more environment. Partitioning of one hard drive into two is considered as virtualisation. 
Virtual box is a cross-platform virtualisation application which install an existing Intel or AMD-based computers, whether they are running windows, mac or Linux operating systems. For example:- We can run windows and Linux on Mac, run Linux on windows PC and vice versa along existing applications. It is very important to run multiple operating systems simultaneously which means virtual box allows us to run more than one operating system at a time. We can run software written for one or more operating system on another without having to reboot to use it. Also, VM makes easier to install software, testing and disaster recovery, infrastructure consolidation. There are different important terminology such as Host operating system, Guest operating system (guest OS), virtual machine (VM).

2.	Steps Outlined:

Once we installed the VirtualBox we can now create our first virtual machine but before we create we should make sure of what type of operating system we are going to install on it. We are doing the Ubuntu which is most popular version of Linux. Once you installed this then we can start running the application.

Click on the “New” button

Screen will ask for Name and operating system

Enter:
Name: any name you like
 Type: Linux
Version: Ubuntu (32 Bit)

Click Next

Accept the default of 512 MB, it can be changed. Now Select “Create a virtual hard drive now” and click “Create”.

Select the default VDI (VirtualBox Disk Image) and click next.

Choose “dynamically allocated” click next, then change the size to 10GB and click create.

Now we can see the VM created bus in state “Powered off”

Inserting a virtual Cd

Before starting the VM, click on “settings” button

Click on storage, you should see
Controller: IDE
….Empty ( with a CD icon)
Controller: SATA
….ubuntu-1.vdi

Click on the CD icon by “Empty”. To the right we see:
Attributes:
CD/DVD Drive: IDE secondary Master, and another CD icon
We will now see:
Controller: IDE
…..ubuntu-12.04-3-server-i386
Controller: SATA
….ubuntu-1.vdi

Click Ok

Simply double click the VM and it will start Now you might get some warnings like” you have auto capture keyboard option turned on….you can press the host key at anytime to uncaptured the keyboard and mouse and return them to normal operation…the host key is currently defined as Right Ctrl”

Select language and press F3. Then press F4 and select “Install a minimal virtual machine”.

Use your hostname, username and password you like.
-	Encrypt your home directory? No
-	Partitioning method: Guided-use entire disk

It will say that It eill use 8.6GB data allow it.
-	Select none for HTTP proxy
-	No automatic updates
-	When you get to “choose software to install” leave others unselected
-	Install GRUB boot loader to the master boot record ? Yes

Restart

Once the installation is complete, you will be prompted to restart

If the machine starts with the CD-ROM attached then remove it. Go to settings>storage as before click CD icon under controller IDE, click the second CD icon, select “Remove disk from virtual drive”. Then restart the VM

Now login with the username and password you created.

Try the console
If you want mouse cursor in Ubuntu server, you need to install the package “gpm”. These should be run with “root” so we prefix them with “sudo”.

$ sudo apt-get update packages                       # update the index of downloadable
$ sudo apt-get install gpm                               # install the package
 
Once this is done , using left and right buttons to select and middle button to paste we can copy and paste within the VM .

Now, try selecting Machine>ACPI shutdown from VirtualBox and you should see that triggers the virtual machine shut itself. We can restart virtual machine after couple of minutes.

We can install the acpi daemon as well
$ sudo apt-get install acpid



Apache
Apache is the most widely used web server software which is developed and maintained by apache software foundation. It is an open source software which is available for free and is also fast reliable and secure. It can be highly customized to meet the needs of many different environments by using extensions and modules. Most Wordpress hosting providers use apache as their web server software. However, wordpress can run on other web server software.
A webserver is a software that receives request to access a web page. It runs security checks for HTTP and takes to the web page.

MySQL is a database management system that is used by Wordpress to store and retrieve all your blog information. MySQL is an open source relational database management system. It runs as a server and allows multiple users to manage and create numerous database. It is a central component in the LAMP stack of open source web application  software that is used to create websites. Lamp stands for Linux, Apache, MySQL and PHP.
Most wordpress installations use the LAMP stack because it is an open source and works with wordpress. Wordpress requires MySQL to store and retrieve all data including the post content, custom types and profiles.


3.	Installation of Apache webserver and MySQL
If you have your ubuntu up to date then can open the command sudo apt-get upgrade
 Now you have opened your previous step and for apache, you will type 
Sudo apt-get install apache2apache2-utils
Sudo systemctl enable apache2
Sudo systemctl start apache2

Now, you can check either your Apache server is running or not. You need to note that network adapter settings make VM visible from host. We need to shut down VM and change the settings on our virtual network adapter. These settings can be accessed by settings>network>advanced>port forwarding

Now you have done with the apache server.
To install MySQL database server run the command
Sudo apt-get install mysql-client mysql-server
Database has not been secured. To see the security configured run the command
Sudo mysql-secure-installation

A very strong password is important. Now we will select settings which makes us easier to run. Select No in testing environment. Click yes to reload privilege tables to take effect on changes.

4.	Installation of PHP and Modules
PHP is an open source language particularly used for web development. It allows developers to create interactive and dynamic websites. Following command should be followed to install PHP and Modules.
Sudo apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd
Test whether the PHP is working or not after finishing the command. Check this by creating a info.php file in /var/www/html directory. Create that file and open it in text editor vi to insert basic PHP code  to test.
Sudo vi/var/www/html/info.php
It will open a new file info.php. ‘I’ key should be pressed to enter insert mode and type the code
<?php
Phpinfo();
?>

Once you finish entering text press ESC then enter command :wq to save file and vi to close.

When the address local host/info.php in host computer is opened we will see a page configuration information if our work is correct. 

5.	Conclusion
Overall, we can install all Apache wordpress and  mySQL under ubuntu perform what kind of system we want. We use PHP to open a page and browse to the page. PHP is an open source language particularly used for web development. It allows developers to create interactive and dynamic website. MySQL can be used to manage files and directories in database.
When I was writing a report I tried to run these software in my laptop as well then terrible problem was  it deletes all the applications in my laptop. I restore again it took me long time and everything comes all right.

6.	References
Moodle notes
Class notes
https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-16-04
https://help.ubuntu.com/lts/serverguide/httpd.html
