This is a basic demonstration showing the function of kubernetes. This specfic demonstration will use kurbentes microservices with autoscaling to provide an application that can automatically adjust resource performance based on demand.

Kurbentes is designed to automate the deployment, scaling, and management of applications , it is put in place as another important characterstic of what makes a relaible high availability and relaible application.

**Prerequisites:**

- Docker - Used to containerise the application to make it portable and reuseable for other environments

- Kubectl - A command line tool whihc allows you to manage resources and apply configurations

- Azure CLI - To login to azure and manage cloud resources from local machine

- Creating a cluster on Azure - Used to run the service within azure

- Git Bash installed on local machine

Once these were all installed we could move on to the next step


Before starting anything azure it is important that I create a small application that can then be deployed and managed I chose to use AI(as this was not the purpose of this demo) to assist me in prodcuing this Time management app. I used Javascript to create the app, I also required a "package" in JSON format to specify the required tools so the application can run correctly.


Using "az login" I can then login via git bash

<img width="1070" height="432" alt="image" src="https://github.com/user-attachments/assets/56fddbe1-1182-4989-b57a-23e2ce5d5c92" />

I then proceeded with the login prompt through microsoft (needed to specify using --tenant and include myu tenant ID)

Next was to create a resource group that the AKS cluster can then go into

<img width="744" height="92" alt="image" src="https://github.com/user-attachments/assets/632ec221-b72d-48e0-b268-7aac8ff2b277" />

I can then create an aks(Azure Kurbernetes service) cluster assigned within the resource group

<img width="410" height="144" alt="image" src="https://github.com/user-attachments/assets/3f9f0907-345b-4bac-ad86-1af328a7c9f4" />

I then needed to connect kubectl to AKS, this is done by requesting credentials and simply specifying where the AKS is located(what resource group) and then specifiy the name of the cluster

I then checked the connection via the following command

kubectl get nodes

The next step was to the create an Azure container registry this was done by using the following command:

az acr create 
--resource-group kubernetes1 
--name k8acr 
--sku Basic

Assigning console to the folder that locally contained my app file, package file and my docker file allowed me to then build the docker image within the current directory one thing to ntoe that I did not know before was the "." at the end of this command specifies that the file is within the current directory.

Below shows the building of the Docker image, now this is built I will now push it to the Azure Container Registry.

<img width="1108" height="480" alt="image" src="https://github.com/user-attachments/assets/b4062cc8-45f4-423b-8d51-1caa201d71e3" />

<img width="1051" height="291" alt="image" src="https://github.com/user-attachments/assets/bb45335c-5138-407e-a7c9-b4dcbc765039" />

it was important that I also created a deployment.yaml file, in this file it specifies all required data and gathers data suhc as the docker image to run the app. Below shows an image of the file which was created with the help of AI. the section where the command is "kind" specifies deployment which manages the pods included.

Pods are the smallest form of deployment. They can contain one or more containers. A deployment ensures that the correct up to date pods are used.

it is important ot note that K8 is an abbreviation for kubernetes.

<img width="931" height="800" alt="image" src="https://github.com/user-attachments/assets/a020d8f1-37a5-4a55-8710-5e2423cc8b05" />

*Screenshot of kuberenetes deployment.yaml file*

To better understand Kuberentes now that the service has been produced within azure I will now be using the Azure GUI to show good representation. In typically industry standards Azure CLI would be used as this allows for repeatitve deployments to be reliable and quick.

the next step was to upload the deployment YAML file to kubernetes cluster

<img width="1084" height="446" alt="image" src="https://github.com/user-attachments/assets/b65ea132-9838-4875-8f6a-f125fed2e2ba" />

when inputting my deployment code into the service, it is important to note that kubernetes is exteremly strict and does not allow for underscores spaces or capital letters(other than for the ACR section), this means that some of the names needed to be changed due to underscores being used.

The next stage is to give this access to the inernet essentially, this is typically done via  a yaml file but can alos be done via the azure portal via services and ingresses

<img width="506" height="116" alt="image" src="https://github.com/user-attachments/assets/8c810c8e-358d-4330-a54f-45bb6da14e13" />

This service essentially assigns a Public Ip address to expose this to the internet

Some issues occured which needed to be adjusted for example below shows cannot GET /

<img width="1753" height="483" alt="image" src="https://github.com/user-attachments/assets/e7e4c7dc-cc82-47a1-a558-a8b52ed9c85d" />

I used the following command to update the AKS 

<img width="859" height="68" alt="image" src="https://github.com/user-attachments/assets/c0a2a29e-f936-401a-8a72-a58480d1e5c3" />

Updating the Javascript file to show specifcally adds a post to the /task section which can then be shown below

Now the app is correctly running as shown by the image below

<img width="673" height="425" alt="image" src="https://github.com/user-attachments/assets/68d1b1a1-50b4-4e5f-bda2-3a008112d91c" />
Now I will provide some tasks to show that this works correctly

This is done by using the following command

<img width="496" height="88" alt="image" src="https://github.com/user-attachments/assets/48ae3c6f-e289-4273-9bc0-d66f282adf5a" />

As you can see i provided two tasks

<img width="574" height="244" alt="image" src="https://github.com/user-attachments/assets/f78d2abf-e83c-491d-8ea4-7549aebe9690" />

As you can see this is exteremly basic as strings are used instead of objects but, the concept is correct and this now means I am easily able to update the AKS cluster

Like all other project I deleted all resources after use


**Issues encountered**

When prodcuing the AKS on Azure CLI an error was dsiplayed showing that there was a resource provider that had not be registered, going into azure and then into the subscription section allowed me to regsiter this to allow this service to be created


<img width="940" height="51" alt="image" src="https://github.com/user-attachments/assets/ef86804a-a8a3-431a-a573-779d7e8eab78" />

another error which occured was that the standard size was not acessible in resource groups located within UKsouth, I recreated the resource group to be Westeurope
