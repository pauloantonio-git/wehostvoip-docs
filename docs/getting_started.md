# Getting Started to WeHostVoIP

WeHostVoIP or WeVoIP as we like to call ourselves, is a Multi-ISP, Multi-Tenant Cloud PBX create specially for Communication Service Providers. 

Following this guide, you will be able to start a Cloud PBX operation in a few hours. There are several steps to prepare for an operation.

There are several steps to start an operation:

* WeHostVoIP Concepts
* Creating a new ISP
* Configuring a carrier to complete your calls
* Create a service plan
* Create Direct Inward Dial Numbers for your customers
* Create domains for your users
* Using existing domains
 
## WeHostVoIP Concepts

There are three different consoles for WeVoIP.

ISP Console - https://uc.wehostvoip.io
Tenant Console - https://uc.wehostvoip.io/tenants
Phone Console - https://phone.wehostvoip.io

In the ISP console (https://uc.wehostvoip.io) you will configure the master plans for the Cloud PBX provider. You are going to attach carriers, create service plans, adjust normalization rules for numbers and many tasks you will have to do only once. 

![wehostvoip-isp](https://user-images.githubusercontent.com/4958202/153396697-236b7908-6c70-4fe8-8357-c304e5be5841.png)

The tenant console is really the PBX interface, you will create one or many Tenants per customer. There are no limits on the number of tenants created. 

![image](https://user-images.githubusercontent.com/4958202/153306442-ad897de4-3755-4ad5-bf1e-c88bbf83468d.png)

Finally the phone interface is an WebRTC where you can make or receive calls. The system also supports almost any SIP phone or device.

![image](https://user-images.githubusercontent.com/4958202/153306639-b3a04b17-c07e-49af-bb0d-7898f25b1499.png)

## Step 1 - Creating a new ISP (Internet Service Provider)

To create a new ISP, you have to start the signup process in the portal uc.wehostvoip.io

![wehostvoip-signup-page](https://user-images.githubusercontent.com/4958202/153394573-98053c2c-de18-4f68-bb54-8a3854d751b8.png)

Once you press signup, the system will ask you to provide an email for confirmation

![wehostvoip-email-confirmation](https://user-images.githubusercontent.com/4958202/153394860-fc61c76d-fe05-475b-9d4f-898d3a478770.png)

Now you have to go to your e-mail and click in the e-mail confirmation link. Once you have pressed the link you will see the ISP configuration link. 

![wehostvoip-1st-onbording](https://user-images.githubusercontent.com/4958202/153395980-67dcd005-d5c5-4acb-a1ff-256649f46613.png)

Provide a Full Name and password for the username and press next

![wehostvoip-2nd-onboarding](https://user-images.githubusercontent.com/4958202/153396350-df093e03-9dbd-45a9-b795-f84bdf99c170.png)

Now, there are important parameters here. The most important parameter is the namespace. When you start using wehostvoip, to login in the system you will need your own namespace. Please choose a namespace and write down the name you will need this parameter in the future. Also important is the currency. Fill the rest of the information and press next.

![wehostvoip-3rd-onboarding](https://user-images.githubusercontent.com/4958202/153397395-95d4c7e1-645b-4c67-a409-0db6f95fd563.png)

Just fill your contact data and press next

![wehostvoip-4th-onboarding](https://user-images.githubusercontent.com/4958202/153398003-c74bfb17-f734-445d-ad53-459d3525d466.png)

Now you can customize your logos and colors. Afeter doing it, press validate to check if you have filled all the required data. 

Once you have finished you will be able to see the ISP interface

![isf-after-onboarding](https://user-images.githubusercontent.com/4958202/153399595-0cd0dd4a-94a8-4167-8aa7-e2ab0adcd66c.png)

## Step 2 - Creating a service plan

The service plan is the heart of the system. You will be able to chage your customers using a prepaid or postpaid system. You can start with something as simple as charge per month and later create more sophisticated plans to charge per leg or per prefix. I the getting started we are going to create simple plan to charge only a monthly fee. 

Press, create service plan to start creating a plan. 

Name your first service plan Default. 

![wehostvoip-service-plan-1](https://user-images.githubusercontent.com/4958202/153400844-7030dc71-5e6b-4dc4-ad17-34096eb36f41.png)

For the next two menus below, check the box "No Service Deck", "No Rate Deck"

![service-plan-2](https://user-images.githubusercontent.com/4958202/153401140-0272f11b-7129-42e2-917a-b4545615d1b3.png)

Then press Create Service Plan, do not leave the page without creating the service plan. 









