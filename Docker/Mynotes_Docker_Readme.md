Sairam

Docker is a containerization platform that allows us to build,package and run applications in isolated environments called containers.

Docker file  --> Build --> Docker image --> run --->Docker container

**Docker architecure**  

Container shared Host os  
App1 App2 App3   
Docker Engine  
Host OS  
Host Hardware  

**VM Ware**    

VM1      VM2      VM3   
App1     App2      App3  
Guest Os Guest Os  Guest Os    
Hyperviser(vmware)  
Host OS   
Host Hardware  

**Docker Commands:**     
docker build -t imagename .--->Docker image will be build using docker file with the mentioned name,if docker file is in same locaiton    
docker build -t imagename:v1 . --->Docker image will be build using docker file with the tag and mentioned name    
docker build -f app/Dockerfile -t imagename -->Docker image will be build using docker file with the mentioned name,if docker file is in different locaiton  
docker build -f app/Dockerfile -t imagename:version -->Docker image will be build using docker file with the mentioned name with version,if docker file is in different locaiton  
docker images  --> It lists all the images    
docker rmi imagename --> It removes the docker image    
docker ps -->shows running containers  
docker ps -a --> shows all containers ,stopped   
docker ps -a |grep keyword --> filters the container  
docker -exec -it containername /bin/bash ---> To access container shell   
docker run -dit --name containername imagename --->To run container in detached mode  
docker cp containername:/opt/app/ . -->copyinng docker container data to the local server  

**Sample Dockerfile for java application (Ubuntu /Debian OS)**  

FROM openjdk:17-jdk-slim   
WORKDIR /opt/app  
RUN apt-get update && \   
    apt-get install -y vim curl net-tools && \    
    apt-get clean && \  
    rm -rf /var/lib/apt/lists/*
    
COPY target/my-app.jar app.jar  
EXPOSE 8080  
ENTRYPOINT ["java","-jar","app.jar"]  

**Sample Dockerfile for Alpine image**
FROM Openjdk:17-jdk-alpine  
WORKDIR /opt/app  
RUN apk update && \  
    apk add --no-cache vim curl net-tools bash   
COPY target/my-app.jar app.jar  
EXPOSE 8080  
ENTRYPOINT ["java","-jar","app.jar"]  

**Sample java Dockerfile for Centos OR RHEL base**    

FROM openjdk:17  
WORKDIR /opt/app  
RUN yum update -y && \  
    yum install -y vim curl net-tools && \  
    yum clean all  
COPY target/my-app.jar app.jar  
EXPOSE 8080  
ENTRYPOINT ["java","-jar","app.java"]  

**Sample Dockerfile for python based application**  
FROM python:3.11-slim  
WORKDIR /opt/app  
COPY requirements.txt .  
RUN pip install --no-cache-dir -r requirements.txt  
COPY my-app.py app.py  
EXPOSE 5000  
ENTRYPOINT ["python","app.py"]




**Note** : 
apt-get clean # We download setup files for installation ,those will be removed after clean    
rm -rf /var/lib/apt/lists/* # index files will be deleted  
Use Alpine and slim are docker lightweight images .These are small size and helps in faster deployments.   
Update : Downloads the latest list of available package in the website and it doesnt change anything .  
apt-get curl -y # intalls latest available version through the link in the index.   
--no-cache # installs packages without storing cache  
CMD ["python",'app.py'] # It can be changed during execution  
Ex. docker run image python test.py can be override easily  
ENTRYPOINT is fixed 
upgrade # is usually avoided unless its required .Prefer stable base image instead  
    




