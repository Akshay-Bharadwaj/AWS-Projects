# Hosting a static website on S3 bucket and much more!

1. Logged in to AWS management console as root user
2. Created a S3 (Simple Storage Service) bucket by enabling ACL (Access Control List) for making the objects publicly visible

![image](https://github.com/user-attachments/assets/5a44fd5e-f892-4226-84cc-8e067afd3523)

3. Uploaded the HTML and CSS files as objects into the bucket

![image](https://github.com/user-attachments/assets/7751b5ee-26be-4110-a536-5a31cbb9dd07)

4. Configured the static website hosting on the bucket by enabling it

![image](https://github.com/user-attachments/assets/5b7555a3-a257-4754-a093-e60c6c77fca8)

5. Error occurred because, only the bucket is made public and not objects. So, objects are made publicly accessible too

![image](https://github.com/user-attachments/assets/fa2065bf-aaf0-4d7a-acf8-c97629056b0b)

![image](https://github.com/user-attachments/assets/1ed85ae4-ac98-4c41-8a0f-08996d0114a0)

6. Assigned a pre-signed URL for the objects to share them for particular users for a particular time. This removes the task of changing the overall access settings of the bucket and objects

![image](https://github.com/user-attachments/assets/106c7f59-317d-4c67-99b3-1c7faf9825a1)

After the allocated time, the site will be inaccessible

![image](https://github.com/user-attachments/assets/59b5deec-6880-47d0-9973-4847902ac474)

7. Added a bucket policy to secure the bucket and its objects from deletion

![image](https://github.com/user-attachments/assets/eaee5130-f688-4214-856c-8eb5b5e08660)

![image](https://github.com/user-attachments/assets/9922c073-fc61-42cb-b824-6559c27a6aeb)

8. Enabled bucket versioning. This helps in creating versions of buckets when the objects inside it are changed

![image](https://github.com/user-attachments/assets/6cba6833-f817-426e-bc66-2b3232f9caa4)

9. Using Route53 to host the website on own domain. Route53 helps in creating a DNS for the user and host the website on it. It also routes the traffic from outside into our domain. Since, I'm on free tier, I didn't create one 😅
