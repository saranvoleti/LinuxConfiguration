<h2>Project Overview</h2>
In this project, I have taken aa baseline installation of a Linux server and prepared it to host your web applications. l secured my server from a number of attack vectors, install and configure a database server, and deploy one of my existing web applications onto it.

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
sudo apt-get install postgresql
sudo su – postgres
create a database and a user. Grant all priveleges to the user.
Exit from PSQL.
Coning Udacity Item Catalog Project:
sudo apt-get install git
cd /var/www
sudo mkdir FlaskApp
cd FlaskApp
sudo git clone https://github.com/saranvoleti/ItemCatalog_Linux.git
Rename the project's name to Flaskapp
Rename item_catalog.py to __init__.py using sudo mv item_catalog.py __init__.py
<h2> To Configure and Enable a New Virtual Host and to create a .wsgi file</h2>
To Configure and Enable a New Virtual Host and to create a .wsgi file follow the instructions given in https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
