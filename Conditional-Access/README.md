Before starting I needed to setup user accounts so I was able to control what users had access to what services/resources.
<img width="1919" height="829" alt="image" src="https://github.com/user-attachments/assets/4a1106f1-19a0-419b-adce-039381f7d146" />
<img width="1864" height="74" alt="image" src="https://github.com/user-attachments/assets/d23a174a-8e85-49e4-9cf7-a5bf079cf600" />
I then added role asisgnment via IAM/Access control this meant Lee would be able to only read that it is there and not change anything on the virutal machine and John wouldnt be able to see it at all
<img width="1919" height="779" alt="image" src="https://github.com/user-attachments/assets/7583e002-6498-487e-b611-df21f94f025f" />

I then logged in as Lee using the credentials I had setup for them 

<img width="1249" height="827" alt="image" src="https://github.com/user-attachments/assets/0b7fb677-c9be-46fd-8a5b-1d96b98a54bd" />

<img width="1919" height="834" alt="image" src="https://github.com/user-attachments/assets/be51f792-c06e-438a-b17e-84fcc8c20069" />

The image above shows that Lee can see the VM1 but has no permissions to even access the vm as show by the image below.

<img width="1913" height="822" alt="image" src="https://github.com/user-attachments/assets/25db2091-6f3f-4eed-ad89-f6911be0fcd5" />


I could further improve this and give a conditional access policy, this would mean I would be able to control the lcoation in which the user logged in from or block thme completely from accessing Azure portal or Insist on MFA. Unfortunately I was unable to do this due to my current subscription limitations with azure.
