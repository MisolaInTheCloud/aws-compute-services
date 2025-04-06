# aws-compute-services

## Step 1: Launch EC2 Instance

- Amazon Linux 2 AMI
- Instance type: t2.micro
- Created & Configured a customized Security Group named 'm4ace SG':
  - Inbound:
    - HTTP (80) — 0.0.0.0/0
    - SSH (443) — My IP
    - 
![image](https://github.com/user-attachments/assets/b4f95266-9956-48a5-84ef-6fecbfa26882)
![image](https://github.com/user-attachments/assets/75575ba5-1016-4973-9c5a-112d397e5422)

## Step 2: Install a web server Nginx on the instance.

![image](https://github.com/user-attachments/assets/3dcac988-01f5-4382-856a-7c6933b0d920)
![image](https://github.com/user-attachments/assets/df399ade-ceab-453a-9f20-c4b111bc6023)


## Step 3: Create an Auto Scaling Group with a Load Balancer.
 ### Load Balancer Configuration

- Type: Application Load Balancer (ALB)
- Listener: HTTP on port 80
- Attached to a Target Groupb
- Health Check Path: `/`
- DNS Name: `web-alb-123456.us-east-1.elb.amazonaws.com`

### Auto Scaling Group Configuration

- Launch Template
- Min Size: 1
- Max Size: 2
- Desired Capacity: 1
- Scaling Policy: CPU Utilization > 70%
- Attached to ALB Target Group




## Challenges: 

##Challenge 1: After creating my EC2, I could not 'Instance Connect".

![image](https://github.com/user-attachments/assets/b3a79ab3-fe4e-41af-8ac2-5b7723e4d739)

I had to troubleshoot & did the following: 
1. Created an Internet Gateway & attached it to my VPC
2. I modified my Route Table & selected the new Internet gateyway as the target
3. Ensured that my Auto-Assign Public IP is Enabled
4.  The troubleshooting was successful & allowed me to 'Instance connect'. Here:
 
 ![image](https://github.com/user-attachments/assets/14d449a8-f5bd-4754-83c6-b5f86acedd3c)

## Challenge 2: After downloading and enabling Ngix on my EC2, my IP was not not loading. Here:

 ![image](https://github.com/user-attachments/assets/2ab65685-354a-44bf-9b63-001ab8612925)
   
 I had to reconfigure my Security groups to allow HTTP Traffic on port 80. Here:
 
 ![image](https://github.com/user-attachments/assets/de84bfa7-c4c5-4947-a96b-b87b51d3193c)

 After the reconfiguration, I received a successful welcome page from Nginx. Here: 

 
 ![image](https://github.com/user-attachments/assets/183e44af-4e2b-44ec-bf7c-e0c71defc177)


### Challange 3
 Test to see my Load Balancer & Auto scaling groups in Action. This was done with "curl IP address of elastic load balancer". Here: 
 
 ![image](https://github.com/user-attachments/assets/713c67f9-308d-414d-a699-8bd34f281f1b)



## The success of the Project: Here: 

![image](https://github.com/user-attachments/assets/fbec3361-7a93-444e-9997-1bb539251a62)

Auto Scaling group Set-up. Here; 

 ![image](https://github.com/user-attachments/assets/ee74a2f3-ac9b-446d-864a-9d7e5da0ae1c)
 
Target group: Healthy Check. Here:

![image](https://github.com/user-attachments/assets/bb0a5aa9-caaa-40eb-a831-3a1f0a233412)


ELB PAGE RESPONSE:
![image](https://github.com/user-attachments/assets/94ad727e-c823-4815-8e1c-34b82b132ce0)

## Summary
This project successfully demonstrates the use of:

- EC2 instances with Nginx web servers

- Secure networking via custom security groups

- Load balancing with ALB

- Resilient scaling via Auto Scaling Groups


