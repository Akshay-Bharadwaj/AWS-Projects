
# Containeraizing a docker image

1. A Dockerfile is written, which is a document of all commands a user could call to build an image
2. A docker image has been built and it is pushed to the docker hub

docker build -t <repositoryName:tagName> .
docker run -it -p <hostPort>:<containerPort> <repositoryName:tagName>
docker login
docker push <repositoryName:tagName>

- The built docker image which is mapped on to a host port can be accessed at localhost:<port>

![image](https://github.com/user-attachments/assets/2d1c845b-12d7-4e63-a62c-cc2cb9472143)

![image](https://github.com/user-attachments/assets/1ff1207d-2cf5-4d9c-9485-b57368e83b4c)

2. An public EC2 instance is created with a key pair

![image](https://github.com/user-attachments/assets/8297b5d6-7fce-4429-9162-7f9933b045de)

3. SSH connection is made from host to the instance to interact with it

![image](https://github.com/user-attachments/assets/2999ab68-83de-43e2-8d7e-83e9462549dc)

4. Required dependencies are installed in the instance
5. The docker image is pulled from the docker hub

![image](https://github.com/user-attachments/assets/f779421d-cdbc-443b-a855-ebebba3484fb)

docker pull <repositoryName:tagName>

6. Pulled image is ran and mapped to the port to start the application and access it

docker run -it -p <hostPort>:<containerPort> <repositoryName:tagName>

![image](https://github.com/user-attachments/assets/69a85e8a-5d51-4811-b344-1c47c04bb852)









