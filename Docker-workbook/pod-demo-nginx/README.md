# Create a simple pod using Kubernetes

1. The main dependencies in kubernetes are kubectl and minikube. Kubectl is the command line interface to interact with the kubernetes. Minikube is a tool to setup a lightweight kubernetes cluster to deploy and test applications.
2. The minimal level of deployment in kubernetes is pod. It is a single container or a group of containers.
3. K8s as orchestrator creates the pod using the specifications given in pod.yaml file and containarize it within the cluster.


Commands used are:

- minikube start
- kubectl create -f pod.yml
- kubectl get pods -o wide
- kubectl describe pods <podname>

![image](https://github.com/user-attachments/assets/de338dc0-ee77-4658-9d24-f2bcd34dc0d1)

![image](https://github.com/user-attachments/assets/9d2a7ae0-acf0-4611-8ebc-f7e8ae3a419b)








