SSS  
VPC is Virtual Private Cloud  

**VPC creation steps :**  

**1.Creat VPC**  
Go to AWS Console --> Search for VPC  
Click Creat VPC    
- **Name** : my-vpc  
- **IPV4 CIDR** : 10.0.0.0/16
Click create VPC
  
**2.Create IGW**  
Go to Internet Gateways  
Click Internet Gateways  
- **Name :** my-igw
- Click create IGW
- Select IGW --> Click Attach to vpc  
- Choose VPC
     
**3.Create Subnets**   
Go to subnets  --> click on create subnet  
**Public Subnet**        
- **Name** : my-public-subnet  
- **IPV4 CIDR** : 10.0.0.0/24  
- **Availability Zone** : ap-south-1a     
**Private Subnet**    
- **Name** : my-private-subnet  
- **IPV4 CIDR** : 10.0.1.0/24  
- **Availability Zone** : ap-south-1b
    
**4.Enable Auto Assign Public IP**  
Go to subnets
- Select my-public-subnet
- Edit subnet settings
- Enable:
  auto assign public ipv4 address
    
**5.Create Route Tables**  
  - Go to Route tables
  - Click on create Route table
**Public Route table**  
  - **Name** : Public-RT
  - **Add Route:**
  - **Destination:** 0.0.0.0/0
  - **Target:** my-igw  
  - Click on create Route table  
  **Private Route table** 
  - **Name :** Private-RT
  - **Rules :** No rules to add

**6.Subnet Association**  
  - Go to Route tables  
  **Click Public-RT**  
  - Edit subnet association  
  - Add my-pubic-subnet    
  **Click Private-RT**  
  - Edit subnet association  
  - Add my-private-subnet
<img width="1911" height="542" alt="image" src="https://github.com/user-attachments/assets/04712d8e-5435-489e-bb51-feb367cef766" />
<img width="1750" height="647" alt="image" src="https://github.com/user-attachments/assets/86c1d71e-621d-43ba-bd63-7820b8a14932" />
<img width="1865" height="707" alt="image" src="https://github.com/user-attachments/assets/06655629-2323-4264-b880-19b2e3fa0c46" />
<img width="1918" height="323" alt="image" src="https://github.com/user-attachments/assets/a8847d28-a03a-4e48-aa2f-e5906cc1dea5" />
<img width="1836" height="635" alt="image" src="https://github.com/user-attachments/assets/2b764a4d-64a5-4ce7-ba7d-a325064fb2dc" />
<img width="1900" height="341" alt="image" src="https://github.com/user-attachments/assets/59f1be1c-6bac-44f5-94f8-7782f0fd626d" />
<img width="1776" height="431" alt="image" src="https://github.com/user-attachments/assets/40662d4e-4067-4f08-817a-d059390af404" />
<img width="1907" height="447" alt="image" src="https://github.com/user-attachments/assets/7d6dcdea-52cf-405b-af93-3536d88f5fac" />
<img width="1655" height="418" alt="image" src="https://github.com/user-attachments/assets/7f1f41b9-f375-4bc1-85fe-e378b572d222" />
<img width="1523" height="473" alt="image" src="https://github.com/user-attachments/assets/e94fd789-1543-4249-98ab-1c11878f8fe7" />
<img width="1552" height="472" alt="image" src="https://github.com/user-attachments/assets/5c20aab9-b572-47c8-b5da-7ffce5578416" />
<img width="1907" height="341" alt="image" src="https://github.com/user-attachments/assets/e2864769-d0ed-4ace-a3b4-5e6f8b24ed62" />
<img width="1902" height="696" alt="image" src="https://github.com/user-attachments/assets/70d87f37-bc12-441b-a0b0-90a3b3d85dd5" />
<img width="1552" height="476" alt="image" src="https://github.com/user-attachments/assets/58a35396-0a74-48fd-a306-202585e71fb7" />
<img width="1917" height="376" alt="image" src="https://github.com/user-attachments/assets/ab5b433b-6e73-4b33-a10a-e85daf714731" />
<img width="1908" height="671" alt="image" src="https://github.com/user-attachments/assets/8d348b5a-4595-4baf-b912-7ae4a0a12bad" />
<img width="1906" height="522" alt="image" src="https://github.com/user-attachments/assets/ab2be891-9698-4363-b9a9-658cc82ffd19" />
<img width="1907" height="633" alt="image" src="https://github.com/user-attachments/assets/2c2caf38-3ae7-4ca7-aa83-d35b4894ddda" />
<img width="1902" height="676" alt="image" src="https://github.com/user-attachments/assets/ca234227-6fa9-4ec1-b73f-af7199d28493" />
<img width="1912" height="738" alt="image" src="https://github.com/user-attachments/assets/74c35f01-9f9e-47fe-b85b-dfcb8107a7a1" />
<img width="1906" height="610" alt="image" src="https://github.com/user-attachments/assets/d167fa9b-0ddd-4d99-8957-994914bf8221" />
<img width="1912" height="452" alt="image" src="https://github.com/user-attachments/assets/364565e9-d219-4050-823a-6fecea288894" />





















  
  
  
  
