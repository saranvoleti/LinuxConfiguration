<h2>Project Overview</h2>
In this project, I have taken aa baseline installation of a Linux server and prepared it to host your web applications. l secured my server from a number of attack vectors, install and configure a database server, and deploy one of my existing web applications onto it.<br>
The project is deployed at http://54.236.59.250/ <br>
IP addreess 54.236.59.250 <br>
Port 2200 <br>

<h2>Get started on Lightsail</h2>
 Start a new Ubuntu Linux server instance on Amazon Lightsail.
SSH into your server.

<h2> Create a new user named grader</h2>

1.	Sudo adduser grader
2.	generate keys on local machine usingssh-keygen
3.	Then, execute the following commands:
a.	$ mkdir .ssh
b.	$ touch .ssh/authorized_keys
c.	$ sudo nano .ssh/authorized_keys -- Copy the public key generated on your local machine to this file and save
d.	chmod 700 .ssh
e.	$ chmod 644 .ssh/authorized_keys

<h2> Update packages</h2>
To update all the currently installed packages, execute the following commands:
sudo apt-get update
sudo apt-get upgrade

<h2>Change the SSH port from 22 to 2200</h2>
To change port from 22 to 2200, execute the following commads:

1.	sudo nano /etc/ssh/sshd_config -- change Port 22 to Port 2200 
2.	sudo service ssh restart

<h2>Configuring uncomplicated firewall:</h2>
1.	sudo ufw allow 2200/tcp
2.	sudo ufw allow 80/tcp
3.	sudo ufw allow 123/udp
4.	sudo ufw enable 

<h2> Install Apache </h2>

1.	sudo apt-get install apache2
2.	sudo apt-get install python-setuptools libapache2-mod-wsgi
3.	sudo service apache2 restart

<h2> PostgreSQL</h2>
5.	sudo apt-get install postgresql<br>
6.	sudo su – postgres<br>
7.	create a database and a user. Grant all priveleges to the user.<br>
8.	Exit from PSQL.<br>

<h2> Do not allow remote connections </h2> <br>
 PostgreSQL from the Ubuntu repositories does not allow remote connections by default. You can check this at:<br>

sudo nano /etc/postgresql/9.1/main/pg_hba.conf<br>
<h2>Cloning Udacity Item Catalog Project:</h2><br>
9.	sudo apt-get install git<br>
10.	cd /var/www<br>
11.	sudo mkdir FlaskApp<br>
12.	cd FlaskApp<br>
13.	sudo git clone https://github.com/saranvoleti/ItemCatalog_Linux.git<br>
14.	Rename the project's name to Flaskapp<br>
15.	Rename item_catalog.py to __init__.py using sudo mv item_catalog.py __init__.py<br>
<h2> To Configure and Enable a New Virtual Host and to create a .wsgi file</h2><br>
To Configure and Enable a New Virtual Host and to create a .wsgi file follow the instructions given in https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps<br><br>

<h2>References:</h2>
https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
https://www.digitalocean.com/community/tutorials/how-to-secure-postgresql-on-an-ubuntu-vps

