# WeHostVoIP documentation! #

**WeHostVoIP** is a Cloud Phone System designed for ISPs to sell cloud Phone Systems. It works as a companion for Google Apps and Microsoft Teams. You may also use WeHostVoIP as a standalone IP PBX System. As a project decision we incentivize our users to use their favorite collaboration tools. What we will provide is the phone system connected to your own SIP trunk or connected directy to the cloud. This avoids effort duplication and multiple conference and chat interfaces. Also it reduces the high costs associated with telephpny offers from Microsoft and Google.  

## Architecture ##

WeHostVoIP is organizaed in a layered arquitecture. The main components of the system are the SIP proxies hosted in the cloud. Then Session and Media Border Controllers (SMBCs) are deployed for every single ISP and even customers. SMBCs can be hosted close to the customer for better latency and voice quality. An SBMC can even be installed in premises for maximum communications privacy.  The architecture of the system may be viewed below:

![WeHostVoIP_Arquitecture](https://user-images.githubusercontent.com/4958202/147883266-19256a68-8730-4d33-aaba-678e07e7c512.png)

Instead of having to install cluster servers, load balancers and manage a huge infrastructure you can simply create your own ISP in the wehostvoip infrastructure. This is a major simplification of the service. WeHostVoIP combines high availability with low latency a rare combination in cloud services. 

## Creating your own ISP ##

To create your own ISP you have to access https://uc.wehostvoip.io, select the option signup

![image](https://user-images.githubusercontent.com/4958202/147883518-d11dbf4d-4c3b-42e3-9d3c-5924f5d501bf.png)

After choosing signup, you have to add your email for confirmation, a link will be sent to your email to complete the process. 

![image](https://user-images.githubusercontent.com/4958202/147883582-e57b7f2e-481d-40e7-a97e-17dbe2019a73.png)

After informing the email, you will receive a screen to fill your ISP data

### Create your account ###

![image](https://user-images.githubusercontent.com/4958202/147883827-7910d715-8f60-4252-9cec-ac436a21ef61.png)

Inform your password and full name and go to the next page. 

### ISP information ###

In the second screen you have to fill some important fields. The first one is namespace. 

![image](https://user-images.githubusercontent.com/4958202/147884011-b1a6da13-013b-4470-90dc-9e65b0ece2e9.png)

#### Namespace Domains ####

The namespace will be the domain where you can create standalone tenants. You may also create tenants with verified domains. So in the example above we have created kages.wehostvoip.io. Now you may create tenants below kages.wehostvoip.io such as customer1.kages.wehostvoip.io. 

#### Verified Domains ####

Sometimes it is more interesting to create the user domain. Mainly if you want to synchronize Google or Microsoft Accounts. If you have access to the DNS of a domain, you can create a verified domain. 

Don't forget to fill your address and also your currency. 

![image](https://user-images.githubusercontent.com/4958202/147884074-8cf8d2df-c88f-4de7-91b3-f2de116aa805.png)

### Contact Details ###

Fill also the contact details. This is very important, sometimes we will need to send you announcements and warnings, please fill these fields with the correct information. 

![image](https://user-images.githubusercontent.com/4958202/147884188-92613847-7f1e-4f64-af61-7cb889649639.png)

### Theming ###

Add your logos and colors for a customized experience. 

![image](https://user-images.githubusercontent.com/4958202/147884234-434f8b0d-95ab-491c-912d-2b5042c3da14.png)

## ISP Configuration ##

Once you have created your ISP you will have a new menu with all the ISP options like the screen below. The screen shows the ISP hobot.wehostvoip.io.

![image](https://user-images.githubusercontent.com/4958202/147887672-4f84f503-c641-4f78-939d-3421b9c64033.png)

There you have the following options:

* Customers
* Carriers
* Tenants
* Numbers
* Dial Plans
* Service Plans
* Administrators

Let's start with customers.

### Customers ###

In the customer's box you can list, delete and create new customers. To create a new customer fill the form below:

![image](https://user-images.githubusercontent.com/4958202/147887779-9b53689d-6e67-4db2-a8b4-0b38fc52534b.png)

Most of the options are solf-explanatory, however in the end of the form you should specify the service plan explaining how the customer will be charged and the maximum amount of subscribers and concurrent calls are allowed for this specific customer. 

### Carriers ###

In the carrier box you can specifiy your SIP trunk data. It is not the function of this platform select the least cost route. We will simply connect a call to a SIP trunk specified. We cannot use trunks with password, only IP authorization. IP authorization is fairly common on wholesale providers. 

![image](https://user-images.githubusercontent.com/4958202/147887884-67cabb3d-0cd3-4d13-9304-a906fa35f363.png)

In the carrier you can select a series of gateways to complete your calls. To create a gateway, please use the option **create gateways**. 

![image](https://user-images.githubusercontent.com/4958202/147887912-770f7857-dfa0-4db0-a6ec-19a80bf9dc68.png)

Fill the following fields:

* Description - Description of the gateway
* Address - The IP address and port of the gateway 
* Strip - Consider any internal number of WeHostVoIP as in the e164 format (country_code+area_code+prefix_number) strip X digits from an internal number before delivering to the gateway
* Prefix - Add the following numbers before the number
* From User - Sometimes you have to edit the From Header to use an specific gateway
* From User Display - Display in the From User
* Add PAI - Add the header P-Asserted-ID with the content of the From User before using this gateway
* Attributes - Custom attributes of a gateway

You can add more than a gateway to the system and it will use the second gateway as a failover to the first one. 

### Number Inventory ###

The number inventory allows you to add phone numbers assigned to your ISP and make them available for your customers. You can control the phone numbers, also called DIDs (Direct Inward Dial) in your system and have a control of the numbers allocated. You can create, delete and update numbers. 

![image](https://user-images.githubusercontent.com/4958202/147890271-2fdfcfea-2a2c-4a37-ab1f-a946a6bddf80.png)

In this menu you can add new numbers, the main parameters for a number are:

* Number - The number itself in e164 format with the +
* Source - identifies the source of this number, in the example, allocated from AWS Voice Connector account
* Type - Local or Toll Free (Changes the billing)
* Price - The price to be charged from the customer in the end of the month
* Vendor Price - How much you are paying monthly for this number
* SMS/VOICE - If the number supports Voice and SMS

### Dial Plans ###

Usually, customers do not dial e164 numbers. They tend to use simplified dialing such as 7 digit dialing or 10 digit dialing. Dial Plans allows us to modify the number dialed and normalize to the e164 format. In the example below we implement the 7 digit dialing.

![image](https://user-images.githubusercontent.com/4958202/147890394-20e40c80-9ed8-4b78-800d-82a1e0b21d04.png)

* Description - A good description of the rule
* Match Expression - Regular Expression Match for the Number. The expression ^[1-9][0-9]{6}$ will match any number starting with a digit from 1 to 9 followed by a digit from 0 to 9 six times. 
* Substitution Expression - ([1-9][0-9]{6}). The substitution expression selects a chunk of the number. As we have only one parenthesis, the chun is the number 1 known as \1
* Replacement Expression - +1_AC\1. Here we add the characters +1 plus the _AC (Area code od the user)_ _(CC is the country code of the user)_ and the chunk \1

Example: 

Suppose the user has country code =+1 and area code 209

If the user dials 2488700, the number will be transformed in +12092488700

The rules will apply sequentially. You can increase the priority of a rule. 

This is probably, one of the most difficult setting in the system, because they require knowledge in regular expressions. 



Creating new Tenants
********************
Tenant Configuration
********************

