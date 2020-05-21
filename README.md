# My_Docker-Project
# INTRODUCTION
I have completed my Docker Training under IIEC RISE 1.0 under the guidance of Vimal Daga Sir. 
Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and deploy it as one package. By doing so, thanks to the container, the developer can rest assured that the application will run on any other Linux machine regardless of any customized settings that machine might have that could differ from the machine used for writing and testing the code.

# REQUIREMENTS:
1.Redhat 8

2.Oracle Virtual Box

3.Docker

4.MySQL

5.MariaDB

6.Wordpress

# SETUP INSTALLATION
# 1.INSTALLING AND RUNNING DOCKER:
For this we have to first configure our yum by writing these commands:
 - cd /etc/yum.repos.d
 - gedit docker.repo
In docker.repo file,we have to write:
 - baseurl=https://download.docker.com/linux/centos/7/x86_64/stable/
 - gpgcheck=0
Then:
 - yum install docker-ce --nobest -y
 - firewall-cmd --zone=public --add-masquerade --permanent
 - firewall-cmd --zone=public --add-port=80/tcp --permanent
 - firewall-cmd --zone=public --add-port=443/tcp --permanent
 - firewall-cmd --reload
 - systemctl start docker
 - systemctl enable docker
 - systemctl status docker
 # 2.INSTALLING AND RUNNING MYSQL & MariaDB:
  - docker pull mysql:5.7
  - docker pull mariadb:latest
  - docker volume create mysql_store
  - docker run -d -it -e MYSQL_ROOT_PASSWORD=mydata -e MYSQL_USER=meera1108 -e MYSQL_PASSWORD=vaayu -e MYSQL_DATABASE=INDIANS -v    mysql_store: /var/lib/mysql --name mysql mariadb:latest
  - mysql -h 172.17.0.2 -u meera1108 -pmydata
 # 3.INSTALLING WORDPRESS:
  - docker pull wordpress:latest
  - docker volume create mywebsite_store
  - docker run -dit -e WORDPRESS_DB_HOST=mysql -e WORDPRESS_DB_USER=meera1108 -e WORDPRESS_DB_PASSWORD=vaayu -e  WORDPRESS_DB_NAME=INDIANS -v mywebsite_store:/var/www/html --name web11 -p 2000:80 --link mysql wordpress:latest 
 # STEP 4:
 Now, make a directory in which we have to make a file named "docker-compose.yml".Now, write the commands inside it and then save & exit.After that, run this command on terminal:
  - docker-compose up
 This will create and run that environment.Now, go to the browser and browse: "IPaddress:PortNumber"

# PROJECT TITLE:
"StayHome_StaySafe"

# PROJECT DESCRIPTION
I have tried to built a webpage using Docker which shows the list of cities where test centres are available in Rajasthan which are testing the pandemic disease COVID-19.

# SCOPE OF IMPROVEMENT
There are many more features that can be added in my webpage,currently working on it.Currently it is also not accessible by the public IP address. 

# ACKNOWLEDGEMENT
I would like to thank Sir Vimal Daga for teaching all the concepts of Docker from very basics.He has explained everything so well, without his guidance it was not possible for me to build a project.
