# Synchroning Accounts with GSUITE

To synchronize an account with GSUITE you need to create and verify the same domain as the one used on GSUITE. 

Step #1 In the ISP interface, create the domain.

![image](https://user-images.githubusercontent.com/4958202/154160552-78ae940a-9998-4505-8e04-6aa9661ffb2e.png)

Step #2 Add the TXT record to your DNS server, ask your domain administrator (webmaster) if you don't know how to do it

![image](https://user-images.githubusercontent.com/4958202/154160604-ba986da2-4b6f-4616-8236-1215b3d23028.png)

Example in Cloudflare, each domain service has a different way to add the TXT record.

![image](https://user-images.githubusercontent.com/4958202/154160810-98f2d0e1-1884-42a5-b783-3bc6249fb953.png)

Step #3 Verify the domain

It may take up to 1 hour to verify the domain. Please, be patient. 

Step #4  Change the domain of your tenant.

![image](https://user-images.githubusercontent.com/4958202/154161592-d7f3e886-261d-42f1-add8-d43a89fe4e18.png)

Step #5 In the tenant's interface on subscribers, click on _synch_

![image](https://user-images.githubusercontent.com/4958202/154161631-9d39aa1c-efe4-4d2b-8f5c-c380537dfdd3.png)

Choose Google and discover subscribers. You need to consent logged in with a user with admin rights to the domain on GSUITE. 

![image](https://user-images.githubusercontent.com/4958202/154161681-35c10df4-c4da-48b8-8026-1ba24757809b.png)

After discovering the users the system will allow you to set the defaults and even to edit account by account

![image](https://user-images.githubusercontent.com/4958202/154161958-bec1b9c7-31c4-44f6-a9f2-f39dc7a3d03a.png)

Pay special attention to the sequential start. It creates an Alias (extension) for each user sequentially starting with this number

You can change any detail for any user in the next screen. 

![image](https://user-images.githubusercontent.com/4958202/154162313-62f8bff8-d56a-41d4-8a69-e2681e4980aa.png)

Now you can add any detail or delete the users you don't want in your system. 

In the bottom of screen press _confirm_ to start importing users.  
