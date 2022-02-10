# Getting Started to WeHostVoIP

WeHostVoIP or WeVoIP as we like to call ourselves, is a Multi-ISP, Multi-Tenant Cloud PBX create specially for Communication Service Providers. 

Following this guide, you will be able to start a Cloud PBX operation in a few hours. There are several steps to prepare for an operation.

There are several steps to start an operation:

* WeHostVoIP Concepts
* Step 1 - Creating a new ISP
* Step 2 - Create a service plan
* Step 3 - Creating a customer
* Step 4 - Configuring a carrier to complete your calls
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

![wehostvoip-subscribers](https://user-images.githubusercontent.com/4958202/153419253-5f00900a-9c67-4615-994c-d8b091ced713.png)

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

## Step 3 - Creating a customer

After creating a service plan, you can now create a customer. Just press the customer menu in the right side and press create to create a new customer Customer is one of your customers who will buy a PBX service. Before you can create a tenant, you have to create a customer.  

![wehostvoip-customer-01](https://user-images.githubusercontent.com/4958202/153402853-53436e6e-0d48-4e10-a6c8-e13993d0be3b.png)

There are important things in this menu. The maximum number of subscribers and the maximum number of concurrent calls. You can control how many licenses each user is using from you. You have to select the service plan and all the other fields are self explanatory. 

## Step 4 - Creating a carrier

Now it is time to specify were will you terminate your calls. For this getting started we are going to terminate calls using a test gateway called sipa.flagonc.com. You may test incoming calls registering a phone in the same server. I will provide instructions at the right point. For now let's create a gateway and a carrier. A carrier can have more than one gateway for redundancy, but the system does no route per prefix. This is the function of the ISP softswitch or gateway terminating the calls. We didn't want to have redundancy on these functions. 

When creating a carrier, the first step is to create the gateway

![image](https://user-images.githubusercontent.com/4958202/153416460-90f10b2b-5adf-4121-afb3-324f10d3a225.png)

It really depends on carrier terminating your calls. You may have to strip some numbers or prefix numbers before you deliver to your carrier. The gateway configuration allows you to do it. The authentication has to be per IP, we do not send digest credentials based on username and password. 

After creating the gateway associate it to the carrier and save. 

![image](https://user-images.githubusercontent.com/4958202/153416615-365c5086-f762-48a5-8de5-66a15547cbe9.png)

See, very quick, carrier is created

## Step 5 - Dialplan

Internally, WeHostVoIP handles all numbers in the [E.164](https://en.wikipedia.org/wiki/E.164) format with "+" in front of the number. There are different ways to dial on each country. Sometimes you need to prefix the number you want to dial with 9 or 0. However everything has to be normalized to E164. We have created some presets for Brazil and US. The dialplan has three very important fields. If you want to create a dialplan you need to understand [regular expressions](https://en.wikipedia.org/wiki/Regular_expression). There is the match expression to match the number, the subs expression to separate the number in chunks using parenthesis and the replacement expression to rebuid the number. You may use two variables _CC (Country Code of the User) and _AC (Area Code of the User)_. If you are in a different country, please let me know and I can create a preset for your country to simplify. For the getting started I'm going to use a preset for US without 9 as a prefix. 

![wehostvoip-dialplan](https://user-images.githubusercontent.com/4958202/153420608-15c30d48-8547-4067-a6dc-68281a784796.png)

## Step 6 - Number Inventory (Optional)

If you have DID numbers or ranges to sell you have to specify them in your ISP. Your users will be able to allocate DIDs for their own users. 

![image](https://user-images.githubusercontent.com/4958202/153417573-58a74558-add1-4e62-8fc1-7b520cf6466b.png)

## Step 7 - Creating Domains (Optional)

You may create directly domain below your namespace such as customer1.gettingstarted.com. For this you don't need to create a domain. However if your customer already uses Google Apps or Azure AD with an specific domain you can add their domains here. You have to verify the ownership of the domain by adding a TXT in a domain server. 

![image](https://user-images.githubusercontent.com/4958202/153421332-cc46251c-d353-4ee6-8576-e02af0372a49.png)










