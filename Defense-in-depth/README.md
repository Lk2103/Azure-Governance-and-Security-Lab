Defense in depth is essentially the process of where multiple layers of security are put into place to ensure that if one fails there are still other defense mechanisms remaining to protect users from malicious entities

## Demonstration
In my demonstration I will be setting up two Linux virtual machines one will acted as the **attacker** and the other as the **target**.

I created two simple VM using spot discount, this is only to be used lab environments, as it will be deleted or unallocated if azure needs this vm storage for other clients.

when creating the the 2 virtual machine's I then produced to virtual networks as well as two resource groups. I learnt when producing the second virtual machine that a separate subscription also had to be created due to the limitations set onto a single subscription

I named the attacker vm Lkvm1 and the target vm Lkvm2

Bastion was used to connect to these virtual machine which displayed the console as shown below

<img width="1916" height="769" alt="image" src="https://github.com/user-attachments/assets/d3c817da-6637-4807-b937-537ecafe464c" />

using commands like ifconfig it can present the ip address details, showing the private and public ip.

this command however did not work due to more needing to be installed and so i used a separate command ip addr show as shown below.(privateip address highlighted)

<img width="1582" height="487" alt="image" src="https://github.com/user-attachments/assets/52c3eb06-8e69-4a69-8a60-3b8517dbda93" />

To connect to the lkvm2 also known as the **target** virtual machine I would need the public ip address. There are various ways of gaining this public IP address i chose to the following command on the target Virtul machine console:

curl -s https://icahnazip.com

Obviously if I was to do this without accessing the other computer this would require other networking tools.

<img width="932" height="245" alt="image" src="https://github.com/user-attachments/assets/398f6c6d-f685-4e90-9c05-66b0936f8238" />

using ssh protocol
