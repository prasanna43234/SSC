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
**Jenkins Installation Steps (Ubuntu or Debian)**  
1. Update system
   sudo apt update
2. Install java  
   sudo apt install openjdk-17-jdk -y
   java -version
3. Add jennkins key
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null  
4. Add jenkins repository
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
5.Install Jenkins
  sudo apt update
  sudo apt install jenkins -y
6.Start jenkins
  sudo systemctl start jenkins
7.Enable Jenkins
  sudo systemctl enble jenkins
8.Check status of jenkins
  sudo systemctl status jenkins
9.Get Admin password
  sudo cat /var/lib/jenkins/secrets/initialAdminPassword
10.Access Jenkins
   http://<your-server-ip>:8080

