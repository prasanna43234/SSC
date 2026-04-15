Docker Commands
1. Download images from dockerhub
   docker pull imagename         --> Pulls Latest (Default tag)
   docker pull imagename:version  --> Particular version will be downloaded
2.Docker Image commands
  docker images ---->It lists all local docker images
  docker rmi imagename --->Removes Image
3.Docker build commands for custom image
  (i) If Dockerfile is in same location
      docker build -t imagename . ----> Image creates with the latest tag
      docker build -t my-app:v1.0 .   --->Image creates with the v1.0 tag
 (ii) If Dockerfile is in differnt lcoation
      docker build -f app/Dockerfile -t my-app:latest .
      docker build -f app/Dockerfile -t my-app:v1.0 .
4.Running docker containers
   (i) To run in detached mode .Means containers runs in background
       docker run -d imagename
   (ii) To run container in interactive mode .Means terminal access of container
       docker run -it imagename /bin/bash
   (iii) To run with name of our choice for contianer .
        docker run -d --name my-container imagename
   (iv) To run with port mapping
        docker run -d -p 8080:80 imagename
    (v) To run with environment variables
        docker run -d -e ENV=dev imagename
   (vi) To remvoe container
        docker rm contianerid
        
5. Container Monitoring
    docker ps ---> To list all running container
    docker ps -a ---> To list all containers
    docker ps -a | grep "reverse"  --> shows reverse proxy container 
6.  Container Life cycle commands
    docker start containerid    ---> To start docker container
    docker stop containerid     ---> To stop docker container
    docker restart containerid  ---> To restart docker container
7.Docker log commands
   docker l
   
