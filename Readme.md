# ansible-to-deploy-mysql-nodejs-app

## Description:
	 
	The project in this repository launches 2 Vagrant machines. A webserver machine to launch the 
    Nodejs app on. The other, to be used for database (using MySQL engine) to be configured upon.

## Important files

### 1. VagrantFile
	The Vagrantfile launches machines on the hypervisor (VMWare etc).
    The  IP, hostname, RAM and CPU can be given as per resources and requirements. The number of 
    machines also depends upon the user.

### 2. inventory.ini
    Contains the configuration for the ansible hosts. Machines can be classified into groups as per 
    requirements. 
    Variables can also be assigned.
	
### 3. Roles
    Contains the ansible roles for database and webservers. Configures the instances to deploy 
    Node.js and MySQL instances smoothly.

### 4. database.yaml
    Configures the database instance by connecting to the database role. Installs MySQL and other 
    dependencies required. THIS HAS TO BE DEPLOYED BEFORE THE WEBSERVERS. The IP of the instance 
    is to be input in the vars file inside the webserver role.

### 5. webservers.yaml
    Configures the webserver instance by connecting to the webservers role. Installs nodejs and other 
    dependencies required for the webserver to function. IP of the database instance is to be input 
    inside var file for it to connect to the database.
