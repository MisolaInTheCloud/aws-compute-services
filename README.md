# aws-compute-services

## Step 1: Launch EC2 Instance

- Chose Amazon Linux 2 AMI
- Instance type: t2.micro
- Created & Configured a customized Security Group named 'm4ace SG':
  - Inbound:
    - HTTP (80) — 0.0.0.0/0
    - SSH (443) — My IP
![image](https://github.com/user-attachments/assets/b4f95266-9956-48a5-84ef-6fecbfa26882)
![image](https://github.com/user-attachments/assets/75575ba5-1016-4973-9c5a-112d397e5422)

## Step 2: 
![image](https://github.com/user-attachments/assets/df399ade-ceab-453a-9f20-c4b111bc6023)
![image](https://github.com/user-attachments/assets/3dcac988-01f5-4382-856a-7c6933b0d920)





## Challenges: 
After creating my EC2, I could not 'Instance Connect". 
![image](https://github.com/user-attachments/assets/b3a79ab3-fe4e-41af-8ac2-5b7723e4d739)

I hade to trouble & did the following: 
1. Create an Internet Gateway & attached it to my VPC
2. I odified my Route-Table & selecte the new Internet gateyway as the target
3. Ensured that my Auto-Assign Public IP is Enabled

4. The trouble shooting was succeful & allolowed me to 'Instance connect'. Here:
5. ![image](https://github.com/user-attachments/assets/14d449a8-f5bd-4754-83c6-b5f86acedd3c)

6. After downloading and enabling Ngix on my EC2, my IP was not
7. ![image](https://github.com/user-attachments/assets/2ab65685-354a-44bf-9b63-001ab8612925)
8. I had to reconfigure my Security groups to allows HTTP Traffic
9. ![image](https://github.com/user-attachments/assets/de84bfa7-c4c5-4947-a96b-b87b51d3193c)

10. The success was a welcome page of Ngix
11. ![image](https://github.com/user-attachments/assets/183e44af-4e2b-44ec-bf7c-e0c71defc177)
12. ![image](https://github.com/user-attachments/assets/ee74a2f3-ac9b-446d-864a-9d7e5da0ae1c)

13. Did some test with curl:
14. ![image](https://github.com/user-attachments/assets/713c67f9-308d-414d-a699-8bd34f281f1b)



Successful: 
![image](https://github.com/user-attachments/assets/fbec3361-7a93-444e-9997-1bb539251a62)


Target group: healthy
![image](https://github.com/user-attachments/assets/bb0a5aa9-caaa-40eb-a831-3a1f0a233412)



