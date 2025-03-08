This repository contains the resources for a hands-on lab from the course Introduction to Containers with Docker, Kubernetes & OpenShift, part of the ***IBM DevOps and Software Engineering Professional Certificate.*** The lab demonstrates how to create and deploy a Kubernetes Service using the nginx image. 

***Overview***

This hands-on lab guides users through the process of deploying a Kubernetes Service that uses an nginx image as its containerized application. It is designed to build fundamental skills in Kubernetes, enabling learners to:
    1. Deploy a simple application container in Kubernetes.
    2. Expose the application using a Kubernetes Service for external access.
    3. Understand key Kubernetes concepts like Deployments, Services, and YAML configurations.

***Learning Objectives**

***By completing this lab, you will:**
    • Understand how to create a Kubernetes Deployment using the nginx image.
    • Learn how to expose a Deployment through a Kubernetes Service.
    • Gain hands-on experience with kubectl commands and YAML files.

***Technologies Used***
    • Kubernetes
    • Docker
    • NGINX
    • YAML
    • kubectl (Kubernetes CLI)

***Prerequisites***

Before starting this lab, ensure you have:
    • A working Kubernetes cluster (e.g., Minikube, MicroK8s, or a cloud provider's Kubernetes service).
    • kubectl installed and configured to communicate with your cluster.
    • Basic knowledge of Kubernetes concepts (Pods, Deployments, and Services).

***Steps to Run the Lab***

***1.Clone the repository***

git clone https://github.com/marioscloud/kubernetes_service_using_nginx

***2. Create a Deployment named my-deployment1 using the nginx image***

 kubectl create deployment my-deployment1 –image=nginx

kubectl: The command-line tool for interacting with the Kubernetes API.
create deployment: Tells Kubernetes that you want to create a new Deployment. A Deployment is a Kubernetes object that manages a set of replicated Pods, ensuring that the specified number of replicas are running and updated.
my-deployment1: It is the name of the Deployment being created. In this case, the Deployment is named my-deployment1.
--image=nginx: It specifies the container image used for the Pods managed by this Deployment. The nginx image is a popular web server and reverse proxy server.
It creates a Deployment named my-deployment1 that uses the nginx image. Deployments manage the rollout and scaling of applications.

***3. Expose the deployment as a service***

 kubectl expose deployment my-deployment1 --port=80 --type=NodePort –name=my-service1

It exposes the my-deployment1 Deployment as a Service named my-service1, making it accessible on port 80 through a NodePort. NodePort services allow external traffic to access the service. 

***4. Lists all services in the default namespace. Services provide a stable IP address and DNS name for accessing a set of pods.***

 kubectl get services

This command lists all the services in the default namespace, including nginx-service, and provides details such as the ClusterIP, NodePort, and target port.
By following these steps, you create a Kubernetes Service named nginx, which routes traffic to the nginx pods running in your cluster, making them accessible internally and externally via the assigned NodePort.

***Contributing***
Contributions are welcome! Feel free to submit issues or pull requests to improve the lab or documentation.

***License***
Distributed under the MIT License. See LICENSE for more details.

***Acknowledgements***
Thanks to the contributors IBM DevOps and Software Engineering Team.
