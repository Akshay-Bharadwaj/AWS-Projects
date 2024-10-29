#Enhancing cloud security using IAM (Identity Access Management)

Objectives of the project:
1.	Boost computing power to match the increasing traffic
2.	Ensure other peer from team have necessary permission settings to contribute by keeping the company’s resources secure

Steps:
1. Create an EC2 instance for the production environment

- Tags are given in the form of key value pair for the instance because, when there are multiple resources, they can be identified only using these tags. Here, tag is given with "Env" as key and "production" as value

![image](https://github.com/user-attachments/assets/1babe2eb-453a-4c6b-b195-9657ddae1d48)

- A free tier eligible AMI (Amazon Machine Image) is selected for the instance. AMI is a template which contains pre-built OS, application server etc. to compute

![image](https://github.com/user-attachments/assets/6d73c92d-b05e-4fe0-818c-a1d1ef5b8e84)

- Instance type is selected which is the set of configurations. Here, t2.micro (again free tier 😅) is selected, which provides 1xCPU, 1 GiB memory with less pricing per hour
- A security key pair can be created for the instance which can be used to make a SSH with it. It can be a .pem file while directly connecting using the terminal or, a .ppk file while connecting using PuTTy

![image](https://github.com/user-attachments/assets/ba90a5c1-57b4-49f1-b50d-0da6544250f2)

- A default VPC network will be created for the instance. Security group which acts as a firewall, is created to allow SSH traffic from outside to the instance.

![image](https://github.com/user-attachments/assets/d3bd1b19-e19d-46ad-aee4-e248c22a01da)

2. Repeat the steps and create another server for Development environment. For this, tag is given with "Env" as key and "development" as value

![image](https://github.com/user-attachments/assets/eb432aec-a8f8-486c-a6ea-dc59673aca00)

3. Create IAM policy

- Policies are set of rules which grant permissions to perform actions on the resources. Here, a policy is created to allow all EC2 actions, describe EC2 action for all resources with condition of having the tag of "development. But, those resources are denied to perform ec2 delete actions.

![image](https://github.com/user-attachments/assets/ed968aae-b4e5-44a7-a24d-8058ec9d0519)

4. Create account alias. It is a unique URL for the users using which they can access the account.

![image](https://github.com/user-attachments/assets/a41c5ae0-5de6-4c7f-83da-3b9aa0849762)

5. Create IAM user group. Here, a IAM user group is created and the user is added to it. In case of multiple users, this reduces the work of attaching policies to each user. Attaching policy to the group will have the effect on the the group users too.

![image](https://github.com/user-attachments/assets/9638d3fa-c6e8-4dd4-9985-cc26ee8762b3)

IAM users have the limited access to the management console and resources unlike the root user.

![image](https://github.com/user-attachments/assets/bfe471e6-7bb9-4f0f-b9ac-5a3aa290d5f2)

6. Test the IAM user access by signing in

![image](https://github.com/user-attachments/assets/311ca450-4bed-4778-9965-07fc2577b2a4)

IAM user does not have access to the entire features of the console

![image](https://github.com/user-attachments/assets/1ff029ae-16b8-4518-b73c-906ad740db68)

7. Tried stopping the production instance using the IAM user. It failed. (Success for me 😁). This is because, the policy attached says, only on instances with the tag value "development", all EC2 actions can be performed. Since I tried to delete, production instance, it failed. But, development instance is stopped successfully.

![image](https://github.com/user-attachments/assets/b85feae4-e545-4a0f-bbf4-9e8739e44cde)

![image](https://github.com/user-attachments/assets/bd9efd5f-d210-486d-a87c-2be133bdb24e)

8. Auto-Scaling can be enabled on the instances when there is more traffic to be handled. Horizontal scaling is adding more number of instances of same type to handle the traffic. Vertical scaling is increasing the capacity of the instance to handle the traffic.

