# Docker

## 1. Install Docker in CentOS
   sudo yum -y install docker
   
   
    sudo -i                           ==>   Enter root user using this option.
    groupadd docker                   ==>  And setup Docker group.
    usermod -aG docker cloud_user     ==>  And setup Docker group.
    systemctl enable  --now docker    ==>  Enable and start docker
    logout                            ==>  Log out of root     
   
  

## 2. Check Version:
  docker --version

## 3. Run first container:
  docker pull docker.io/hello-world
  docker run hello-world

## 4. List all image:
  docker image ls

## 5. Run the image and open the command prompt into bash.. on the container
  docker run -it ubuntu bash
    
    -i ==> --interactive.
    -t ==> --tty (Allocate a pseudo-TTY).

## 6. Run a docker in detached mode and with a specific name
   docker run <-d -- detached mode> <--name treatseekers (is the name of the container> <-p port forwarding > image-name
   docker run -d                     --name treatseekers                                  -p80:80              spacebones/doge
   docker run -d --name treatseekers -p80:80 spacebones/doge
   
## 
  docker run -it --rm -p 8888:8080 tomcat
  
    -i ==> --interactive.
    -t ==> --tty (Allocate a pseudo-TTY).
    --rm ==> This will remove the container when it is stopped.
    -p ==> is Port forwarding.

# 7. Build container images:
   ## 7.1 Pull centos docker image:
       docker pull centos:6 ==> This pulls a new docker image with centos 6

   ## 7.2 Launch docker in bash and interactive mode...
       option -it ==> Launches centos 6 into bash and loads up /bin/bash
       docker run -it centos:6 /bin/bash

       yum -y update ==> always run this initially to update the package manager..

   ## 7.3 Install apache webserve in CentOS :
       yum -y install httpd git  ==> This command will install httpd (apache server) and git..

   ## 7.4 Pull source code from git..
         git clone https://github.com/linuxacademy/content-dockerquest-spacebones
   
   ## 7.5 copy the files to /var/www/html
         cp content-dockerquest-spacebones/doge/* var/www/html  ==> This will copy all the files into the Apache html folder 
   
   ## rename to welcome.conf so that the default welcome page doesnot load
         mv <source file > <destination file>

   ## 7.6 Commit the docker image
      docker commit 85e896f4bb16 spacebones:thewebsite
      
      
## Pull other version docker images..
    docker pull openjdk:8
 
 ## List all containers
    
     docker ps -a
     
## Remove all open containers
    docker rm -f $(docker ps -aq)
    
## ...
