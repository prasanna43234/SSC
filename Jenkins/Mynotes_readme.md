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


