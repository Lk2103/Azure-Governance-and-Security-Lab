This is a basic demonstration showing the function of kubernetes. This specfic demonstration will use kurbentes microservices with autoscaling to provide an application that can automatically adjust resource performance based on demand.

Kurbentes is designed to automate the deployment, scaling, and management of applications , it is put in place as another important characterstic of what makes a relaible high availability and relaible application.

**Prerequisites:**

- Docker - Used to containerise the application to make it portable and reuseable for other environments

- Kubectl - A command line tool whihc allows you to manage resources and apply configurations

- Azure CLI - To login to azure and manage cloud resources from local machine

- Creating a cluster on Azure - Used to run the service within azure

- Git Bash installed on local machine


I firsted needed to login on Git Bash


Before starting anything azure it is important that I create a small application that can then be deployed and managed

I then installed azure CLI

<img width="939" height="625" alt="image" src="https://github.com/user-attachments/assets/e0889057-421e-407c-a3c5-c870e19e2867" />

Using "az login" I can then login via git bash

<img width="1070" height="432" alt="image" src="https://github.com/user-attachments/assets/56fddbe1-1182-4989-b57a-23e2ce5d5c92" />

I then proceeded with the login prompt through microsoft (needed to specify using --tenant and include myu tenant ID)

next was to create a resource group that the AKS cluster can then go into

<img width="744" height="92" alt="image" src="https://github.com/user-attachments/assets/632ec221-b72d-48e0-b268-7aac8ff2b277" />

I can then create an aks(Azure Kurbernetes service) cluster assigned within the resource group

<img width="410" height="144" alt="image" src="https://github.com/user-attachments/assets/3f9f0907-345b-4bac-ad86-1af328a7c9f4" />



**Issues encountered**

When prodcuing the AKS on Azure CLI an error was dsiplayed showing that there was a resource provider that had not be registered, going into azure and then into the subscription section allowed me to regsiter this to allow this service to be created


<img width="940" height="51" alt="image" src="https://github.com/user-attachments/assets/ef86804a-a8a3-431a-a573-779d7e8eab78" />

another error which occured was that the standard size was not acessible in resource groups located within UKsouth, I recreated the resource group to be Westeurope
