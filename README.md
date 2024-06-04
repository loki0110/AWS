For installing Docker-Compose:
sudo curl -L "https://github.com/docker/compose/releases/download/v2.24.7/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
For TestNG:
wget https://repo1.maven.org/maven2/junit/junit/4.13.2/junit-4.13.2.jar
wget https://repo1.maven.org/maven2/org/hamcrest/hamcrest-core/1.3/hamcrest-core-1.3.jar
javac -cp .:junit-4.13.2.jar:hamcrest-core-1.3.jar src/Calculator.java test/CalculatorTest.java
java -cp .:src:test:junit-4.13.2.jar:hamcrest-core-1.3.jar org.junit.runner.JUnitCore CalculatorTest

commands for execution of container in 6th exp :
sudo su
yum install docker -y
systemctl start docker
docker --version
docker volume create myvol
docker run -d --name myrvol_nginx -v myrevvol:/usr/share/nginx/html -p 80:80 nginx
docker inspect myvol

commands for exp 7 :
sudo su 
yum install docker -y
systemctl start docker
sudo curl -L "https://github.com/docker/compose/releases/download/v2.24.7/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
mkdir dockerproject 
cd dockerproject 
nano docker-compose.yml

yml file :

version: '3.8'

services:
  ubuntu:
    image: ununtu:latest
    container_name: mycontainer1
    command: sleep infinity

  alpine:
    image: alpine:latest
    container_name: mycontainer2
    command: sleep infinity 

networks:
  default:
    driver: bridge



docker-compose up -d

if error stating mapping not allowed then check the colon and spaces of yml file.


exp 10 user data :

#!bin/bash

yum update -y

yum install httpd -y

echo "<h1>This is from $(hostname -f)</h1>" > /var/www/html/index.html

systemctl enable httpd  

systemctl start httpd
