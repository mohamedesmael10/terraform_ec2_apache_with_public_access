# Public EC2 with Apache and Internet Gateway

## Project Overview
This project provisions an AWS EC2 instance running Apache in a public subnet, allowing internet access through an Internet Gateway. The security group is configured to permit HTTP traffic.

## Architecture Diagram
![Architecture](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(1).png)  

## Infrastructure Components
- **VPC**: `10.0.0.0/16`
- **Public Subnet**: `10.0.1.0/24`
- **EC2 Instance**: Runs Apache web server
- **Security Group**: Allows HTTP (`80`) and SSH (`22`) access
- **Route Table**: Directs `0.0.0.0/0` traffic to the Internet Gateway
- **Internet Gateway**: Provides internet access to the public subnet

## Prerequisites
- AWS CLI configured
- Terraform installed

### Deployment Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access.git
   cd terraform_ec2_apache_with_public_access
   ```

2. **Initialize Terraform**
   ```bash
   terraform init
   ```

3. **Apply the Terraform Configuration**
   ```bash
   terraform apply -auto-approve
   ```
   This command provisions the following resources:
   - VPC with CIDR block `10.0.0.0/16`
   - Public subnet with auto-assigned public IPs
   - Internet Gateway and Route Table to allow internet traffic
   - Security Group with inbound rules for SSH (22), HTTP (80), and HTTPS (443)
   - EC2 instance with a user data script to install and start Apache

4. **Access the EC2 Instance**
   - Retrieve the public IP of your EC2 instance:
     ```bash
     terraform output public_ip
     ```
   - Open a browser and navigate to `http://<public-ip>` to see the Apache default page.
  

## Troubleshooting
If the public IP is not accessible:
- Ensure the security group allows inbound traffic on port 80.
- Verify that the route table is correctly configured with an Internet Gateway.
- Check that Apache is running on the EC2 instance:
  ```sh
  systemctl status apache2
  ```

## Cleanup
To destroy the infrastructure:
```sh
terraform destroy -auto-approve
```

## Screenshots

Here are some screenshots of the script in action:

![Screenshot 1](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(1).png) 
![Screenshot 2](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(2).png) 
![Screenshot 3](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(3).png) 
![Screenshot 4](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(4).png) 
![Screenshot 5](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(5).png) 
![Screenshot 6](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(6).png) 
![Screenshot 7](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(7).png) 
![Screenshot 8](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(8).png) 
![Screenshot 9](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(9).png) 
![Screenshot 10](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(10).png) 
![Screenshot 11](https://github.com/mohamedesmael10/terraform_ec2_apache_with_public_access/blob/main/Shots/(11).png) 


- **Mohamed Mostafa Esmael**  
  Email: [mohamed.mostafa.esmael10@outlook.com](mailto:mohamed.mostafa.esmael10@outlook.com)  
  LinkedIn: [linkedin.com/in/mohamedesmael](https://linkedin.com/in/mohamedesmael)

---
