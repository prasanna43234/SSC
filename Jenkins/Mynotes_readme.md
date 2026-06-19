SAIRAM  

**Jenkins** is an open source automation tool that helps build ,test and deploy the application automatically.    
**Continuous Integration**   
Developers frequently merge their code in to a shared repository.Jenkins automatically builds the code and runs the test.This process is called CI.     
**Continuous Delivery** After build and test ,keeping the application in central repositories like artifactory ,nexus for deployment .This process is called CD.     
**Continuous Deployment** Means process of automatically deploying the application in desired environments like dev/test or prod.  

**How jenkins works step by step flow**   
1.Developer writes code and pushes it to github  
2.Jenkins detects the changes automatically pulls the code  
3.Jenkins builds the application using (Maven/Gradle) mvn clean install    
4.Jenkins runs test to check if code is correct or not  
5.Jenkins package the application (jar/war/Dockerimage)  
6.Jenkins deploys it to server (Dev/Test/production)  

**Why Jenkins ?**   
Automates the repetitive tasks  
Reduces manual work  
no human errors  
Detects errors early through automated testing  
speed up release process  
**Jenkins Installation**  
Jenkins can be installed in multiple ways depending on environment ,infrastructure and usecases.These are main types of jenkins installation.  
**1.Standalone Installation of Jenkins (WAR)**   
Run jenkins using a war file without installing it as a system service.
1.Download jenkins war file  
2.java -jar jenkins.war  
3.Accesss in browser using http:localhost:8080 port  
Usecase : Testing,learning jenkins ,quick setup,very simple ,no os level configuration needed and not suitable for production.Needs manual start/stop  

**2.Package Installation Of Jenkins (Ubuntu or Debian)**  
Install jenkins as a service using os packages.  
RHEL/CENTOS -->.rpm   
Ubuntu / Debian -->.deb    
Install via package manager     
centos/rhel --> yum  
ubuntu /debian -->apt  
Usecase : Production environmetn ,stable deployments  
Advantages: Auto start on boot,runs as a service (systemctl start jenkins)
1. Update system  
   sudo apt update  
2. Install java    
   sudo apt install openjdk-17-jdk -y  
   java -version  
3. Add jennkins key  
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null    
4. Add jenkins repository  
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null  
5. Install Jenkins  
   sudo apt update  
   sudo apt install jenkins -y  
6. Start jenkins  
   sudo systemctl start jenkins  
7. Enable Jenkins  
   sudo systemctl enble jenkins  
8. Check status of jenkins  
   sudo systemctl status jenkins  
9. Get Admin password  
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword  
10. Access Jenkins  
    http://<your-server-ip>:8080  
**3.Docker Installtion of Jenkins**
    1.Pull docker image of jenkins  
      docker pull jenkins/jenkins:lts (jenkins/jenkins-->official image & lts->long term suport(stable version))  
    2.Run docker image  
      docker run -d -p 8080:8080 --name jenkins-container jenkins/jenkins:lts   
    Usecases: Cloud environments ,micro services architecture,devops pipeline  
    Advantage : Portable,east to replicate,isolated environments  
**4.Kubernetes Installation of Jenkins**  
    Deploy jenkins in kubernetes using helm charts or yaml files.  
    Usecase: Large scale deployments,cloud native environments  
    Advantage :Highly scalable,supports dynamic agents,good for enterprise setups  
    Disadvantage :Complex setup  
**5.Jenkins on cloud platforms**  
    Install jenkins on cloud VMs.  
    EX: AWS EC2,Azure VM,GCP compute engine  
    Usecase: Remote CI/CD,scalable infrastructure  
    Advantage : Highly availability,easy scaling,accesseble from anywhere  
    Disadvantage :Cost involved  
**6.Jenkins managed service**  
    Use managed services of jenkins provided by cloud or third party tools.  
    EX: cloudbees jenkins,jenkins on aws (prebuilt-amis)  
    Usecase: Enterprise,teams doesnt want to manage infrastructure  
    Advantages: No maintenance,built in scalability,support available.  
    Disadvantages: Expensive ,less control  
    

