# WeHostVoIP documentation! #

**WeHostVoIP** is a Cloud Phone System designed for ISPs to sell cloud Phone Systems. It works as a companion for Google Apps and Microsoft Teams. You may also use WeHostVoIP as a standalone IP PBX System. As a project decision we incentivize our users to use their favorite collaboration tools. What we will provide is the phone system connected to your own SIP trunk or connected directy to the cloud. This avoids effort duplication and multiple conference and chat interfaces. Also it reduces the high costs associated with telephpny offers from Microsoft and Google.  

## Architecture ##

WeHostVoIP is organizaed in a layered arquitecture. The main components of the system are the SIP proxies hosted in the cloud. Then Session and Media Border Controllers (SMBCs) are deployed for every single ISP and even customers. SMBCs can be hosted close to the customer for better latency and voice quality. An SBMC can even be installed in premises for maximum communications privacy.  The architecture of the system may be viewed below:

![WeHostVoIP_Arquitecture](https://user-images.githubusercontent.com/4958202/147883266-19256a68-8730-4d33-aaba-678e07e7c512.png)

Instead of having to install cluster servers, load balancers and manage a huge infrastructure you can simply create your own ISP in the wehostvoip infrastructure. This is a major simplification of the service. WeHostVoIP combines high availability with low latency a rare combination in cloud services. 

## Creating your own ISP ##

To create your own ISP you have to access https://uc.wehostvoip.io, select the option signup

![image](https://user-images.githubusercontent.com/4958202/147883518-d11dbf4d-4c3b-42e3-9d3c-5924f5d501bf.png)


*********************
ISP Configuration
*****************
Creating new Tenants
********************
Tenant Configuration
********************

