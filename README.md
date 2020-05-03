# IIEC RISE 1.0 Docker Training

#### In the month of March 2020 I had training on docker technology where I learnt lots of things under the guidance of Mr. Vimal Daga sir , now we are concluding this training so I have made this project for implementing whatever we have learnt in the 24 hours online class.
### This is a project along with my experience while learning docker whatever problems I faced how I resolved them is provided here. 

## 1. System Requirenments :
  We will require an operating system it may be bare metal or virtual machine I have used RHEL version 8 for the same. Basically I have windows installed on my machine on the top of it I have installed RHEL 8 as a virtual machine.
  
## 2. Docker Installation :
 * First of all copy the path of url from where we are going to install docker `https://download.docker.com/linux/centos/7/x86_64/stable/` I would suggest go through this URL for installation. In the RHEL I have configure yum for installing community eddition of Docker.
 * I faced one problem where my docker container was unable to run as security system was refusing so I have got the solution while qna
`setenforce 0` this will turn of security enforcement. 

## 3. Downloading Images :
 * This is very simple task we just have to pull images of os from `https://hub.docker.com/` I have used centos image for configuring my webserver as well as a client .
 * `https://hub.docker.com/_/centos` this is the official image provided by centos we can pull this image by `docker pull centos` this  command 
 
 ## 4. Network creation :
  * I have created my own network for this project for convinience in development.
  * `docker network create --driver bridge webnet` here driver is network mode I have used bridge as I have to communicate with internet.
  
 ## 5. Server creation  :
  * I have launched one centos image in my  container using `docker run -it centos:latest` command. 
  * for configuration of webserver I have installed some softwares.  First of all I was going to deploy my website on apache webserver so I have downloaded required softwares.
  * for installing apache webserver there are 3 steps 
    *  Software installation using `yum install httpd`
    *  Deploying webpages inside `/var/www/html` folder
    *  Start services using `systemctl start httpd.services` but in docker container systemctl process doesn't initializes so we have 
  using `yum install httpd` I have installed software for webserver.
  
  
