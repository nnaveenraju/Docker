# Docker

## Install Docker in CentOS
   sudo yum -y install docker

   -------------------------------------------------------------------------------------
   | sudo -i                              |  Enter root user using this option.         |
   | groupadd docker                      |  And setup Docker group.                    |
   | usermod -aG docker cloud_user        |  And setup Docker group.                    |
   | systemctl enable  --now docker       |  Enable and start docker                    |
   | logout                               |  Log out of root                            |
   --------------------------------------------------------------------------------------
  

## Check Version:
  docker --version

## Run an image:
  docker run hello-world

## List all image:
  docker image ls

## Run the image and open the command prompt into bash.. on the container
  docker run -it ubuntu bash
    
    -i ==> --interactive.
    -t ==> --tty (Allocate a pseudo-TTY).

## 
  docker run -it --rm -p 8888:8080 tomcat
  
    -i ==> --interactive.
    -t ==> --tty (Allocate a pseudo-TTY).
    --rm ==> This will remove the container when it is stopped.
    -p ==> is Port forwarding.
    
## Pull other version docker images..
    docker pull openjdk:8
 
 ## List all containers
    
     docker ps -a
     
## Remove all open containers
    docker rm -f $(docker ps -aq)
    
## ...
