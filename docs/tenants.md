# Creating new Tenants #

Tenants are the building blocks of the Cloud PBX service provider. From the ISP interface you can simply create a new tenant. It is important before creating a tenant to create all the other components:

* Customers
* Dial plans
* Service Plans
* Carriers
* Number Inventory

![image](https://user-images.githubusercontent.com/4958202/148833500-d63114cd-ddb8-474d-a9a8-8bce7b4bad8c.png)

In the right side press create tenant:

![image](https://user-images.githubusercontent.com/4958202/148833864-a6bad52c-901d-4248-99fa-6e9d0d1116ac.png)

* Domain - The first field is the most important **Domain**. You can create a domain in your wehostvoip namespace or you can create a verified domain in the domain menu. For Single Sign On and synchronization with Google Apps and Azure AD you will need to have a verified domain. 

* Customer - One customer can have more than one Tenant, so please associate the Customer to the Tenant. 

* Carrier - Select the gateway set to complete the calls for this tenant. The gateway should allow access restricted to the IP od the ISP's SBC. 

* Admins - Administrators of the Tenant, capable to add and remove users

* Dialplan - The dial plan associated with this tenant

* SBCs - The Session Border Controllers associated to this tenant. You will use these SBCs for phone provisioning

* Provisioning - The username and password for the SIP softphone provisioning
