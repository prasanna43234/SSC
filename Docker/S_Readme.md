Sairam

Docker is a containerization platform that allows us to build,package and run applications in isolated environments called containers.

Docker file  --> Build --> Docker image --> run --->Docker container

Docker architecure

Container shared Host os  
App1 App2 App3   
Docker Engine  
Host OS  
Host Hardware  

VM Ware  

VM1      VM2      VM3   
App1     App2      App3  
Guest Os Guest Os  Guest Os    
Hyperviser(vmware)  
Host OS   
Host Hardware  

Docker Commands:    
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




