SSS  
VPC is Virtual Private Cloud  
**VPC creation steps :**  
**1.Creat VPC**  
- Go to AWS Console --> Search for VPC
- Click Creat VPC
- **Name** : my-vpc  
- **IPV4 CIDR** : 10.0.0.0/16
- Click create VPC
**2.Create IGW**
- Go to Internet Gateways
- Click Internet Gateways
- Name : my-igw
- Click create IGW
- Select IGW --> Click Attach to vpc
- Choose VPC 
**3.Create Subnets** 
- Go to subnets  --> click on create subnet
  **Public Subnet**    
- Name : my-public-subnet
- IPV4 CIDR : 10.0.0.0/24
- Availability Zone : ap-south-1a   
  **Private Subnet**  
- Name : my-private-subnet
- IPV4 CIDR : 10.0.1.0/24
- Availability Zone : ap-south-1b
**4.Enable Auto Assign Public IP**
- Go to subnets
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
  
  
  
