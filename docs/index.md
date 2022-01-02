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



*********************
ISP Configuration
*****************
Creating new Tenants
********************
Tenant Configuration
********************

