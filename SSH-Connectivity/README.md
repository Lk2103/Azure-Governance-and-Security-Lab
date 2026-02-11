I will be demonstrating the use of SSH keys for security.

<img width="1912" height="823" alt="image" src="https://github.com/user-attachments/assets/8bd7eaac-169d-4e4d-a312-71e67080c722" />

Above shows an image of me first producing a virtual machine that I am creating in a dedicated resource group. I will be including tags

<img width="1917" height="808" alt="image" src="https://github.com/user-attachments/assets/621bcc61-e04c-45bf-a87f-f777813d75f7" />

Above shows the implemntation of a public SSH Key, on this page I also have the ability to create two virtual machines in seperate availability zones, to distrubute load OR to produce redundancy within my infratructure.

There are two different options for SSH key types, these being RSA SSH format and ssh ed25519

There are a variety of differences between the two, however ed25519 is more commonly used currently due to its modern take on security while remaining a shorter key. the picture below shows the many differences these key types have.

<img width="497" height="563" alt="image" src="https://github.com/user-attachments/assets/7188aae5-3a97-4cf1-aea2-bbf612eee2d4" />

Image taken from: https://www.geeksforgeeks.org/devops/rsa-vs-ed25519-which-key-pair-is-right-for-your-security-needs/

It is important to remember that RSA still can be used due to its compatibility with older systems.

The public key is stored on the virtual machine, while the private key remains secure on my local machine. When I attempt to connect, my private key is used to prove my identity. The VM checks it against the stored public key. If they match access is granted. Important to know that public keys are stored on the virtual machine and are under authorised keys, you cannot get into a virtual machine solely with a public key

<img width="1356" height="545" alt="image" src="https://github.com/user-attachments/assets/173da2a4-5031-44cd-88a3-1ac5500beb67" />

Vnet and subnets are being produced with the virtual machine

<img width="1919" height="790" alt="image" src="https://github.com/user-attachments/assets/9ac39297-a1dc-4276-8b2b-bb7acaf42846" />

This image shows an example of how resource tags can be used, Resource tags are used to organise the resources so that they can be grouped togther in similar catergories later on or can be searhed for easily.

Using ssh and private key that azure let me download when the deployment of the virutal machine was made i was able to connect via my machines local command line

<img width="1424" height="322" alt="image" src="https://github.com/user-attachments/assets/d43e0a6b-bad7-41f5-b079-a9ddeeecfc8e" />

Azure refers to pairs this means that when this is deployed there is a public and private key which is developed public which stays on the virtual machine and then private keys which are given to the user once developed and downloaded ot their local machine but ARE NOT STORED ON AZURE 


<img width="1919" height="841" alt="image" src="https://github.com/user-attachments/assets/d4b47081-abfc-4454-94e5-737b19d2c241" />

Connection via azure shell
