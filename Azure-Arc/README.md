Azure Arc lab demonstration
This lab demonstrates the use of azure Arc to attach a local non Azure machine into azure. Azure Arc's purpose is to extend Azure's management and governance capabilities to on premises he following material shows how this can be done.

**My Objective** of the lab session was to connect a local Machine(My current laptop) to azure using Azure Arc, with validation of it being centrally managed through the Azure portal.

Navigation to Azure Arc was achievable by searching via the portal(As shown by the image below)
<img width="1919" height="845" alt="image" src="https://github.com/user-attachments/assets/7b990110-3ce8-49cc-bc5e-5b75e9d2fe37" />

Clicked adding a machine (the term Onboarding is used frequently) Azure is very helpful with variety of assisting links if required. 
<img width="522" height="471" alt="image" src="https://github.com/user-attachments/assets/237bc846-2db4-43cc-a391-ef6c6363ea2b" />

Below is a brief look into some of the different connectivity methods available private and public endpoints. The use of express route and VPN gateways is used in conjunction with Arc in some cases to achieve the related endpoint
<img width="1265" height="378" alt="image" src="https://github.com/user-attachments/assets/1c7f9cc4-aa0e-4bf8-8a70-e3704c0c5b11" />

**Important Clarification** 
During this lab, I initially misunderstood the difference between Azure Arc and ExpressRoute, its important to state that Azure Arc DOES NOT provide connectivity between environments like Express Route.

Expressroutes and VPNGateways are solutions used to establish a private connection between on premises environments and Azure Virutal Networks.

Below is the Onboard scripting that is produced by azure to use on the Local machine via  the powershell, this installs an azure agent and allows for the connection between the on premise device and Azure.
<img width="1919" height="822" alt="image" src="https://github.com/user-attachments/assets/38354949-6226-4e2d-99be-d6fcd579275d" />

Once used on Local Machine the following result occurs

<img width="1303" height="214" alt="image" src="https://github.com/user-attachments/assets/478944b4-d9ac-437d-888c-79092a7b1206" />

Below shows the Local machine info accessible on Azure

<img width="1919" height="737" alt="image" src="https://github.com/user-attachments/assets/9dd48157-b83b-4e30-ab46-169a175b0527" />

This is something that could be used in enterprises to ensure that there is consistency of policies and security implementations over all devices associated to the company.

