# Multi Stage Docker Build

1. A golang based application is taken as example, since it is statically typed and it is cloned from a open-source contributed repository.
2. Docker file is written in a way that both build time packages and runtime dependencies are made seperately.
3. For build dependencies, a rich base image is chosen and for runtime, specific dependencies are chosen from the build.
4. Main purpose of the multi-stage build is to reduce the size of the image.

Steps:
1. Dockerfile is written for the dependencies
![image](https://github.com/user-attachments/assets/942f83c2-d8d1-462f-b0c8-6b9211cdee10)

2. Image is built, ran and pushed to the docker hub
![image](https://github.com/user-attachments/assets/5d1b6c5c-3452-4379-bdb3-7bbad901629c)

![image](https://github.com/user-attachments/assets/bf5ac0b4-883b-4269-97d2-d857b75f2d94)

The main advantage of the distroless image apart from reducing size is providing security to the image.








