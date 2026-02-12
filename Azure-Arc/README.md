Azure Arc lab demonstration
This lab demonstrates the use of azure Arc to attach a local non Azure machine into azure. Azure Arc's purpose is to extend Azure's management and governance capabilities to on premises he following material shows how this can be done.

Azure Arc can be looked up on azure portal shown below
<img width="1919" height="845" alt="image" src="https://github.com/user-attachments/assets/7b990110-3ce8-49cc-bc5e-5b75e9d2fe37" />

<img width="522" height="471" alt="image" src="https://github.com/user-attachments/assets/237bc846-2db4-43cc-a391-ef6c6363ea2b" />

above shows the machine option there are various different options to help if unsure of what to do.

<img width="1265" height="378" alt="image" src="https://github.com/user-attachments/assets/1c7f9cc4-aa0e-4bf8-8a70-e3704c0c5b11" />

Above shows the connectivity methods available it mentions that for private endpoints you would need a VPN with expressroute. express route is another feature that allows on premise networks to connect to virtual networks via VPN gateway. 

A misundestanding I had when producing this was that these services were similar but, they are not as one of these services introduces external devices to azure so that governance and managment can be controlled viaa universal location. This is vastly different to ExpressRoute and VPN gateways.

<img width="1919" height="822" alt="image" src="https://github.com/user-attachments/assets/38354949-6226-4e2d-99be-d6fcd579275d" />

Above shows the script that can now be used on local machine using powershell. I will be learning how to manually code this eventually as this would be a more realstic scenario of cloud roles.

<img width="1303" height="214" alt="image" src="https://github.com/user-attachments/assets/478944b4-d9ac-437d-888c-79092a7b1206" />

Pasting this powershell script shows the above result

<img width="1919" height="737" alt="image" src="https://github.com/user-attachments/assets/9dd48157-b83b-4e30-ab46-169a175b0527" />

Above shows the local machine being presented in azure. demonstrates the simple application of azure arc which will eventually be carried out using infrastructure as code

