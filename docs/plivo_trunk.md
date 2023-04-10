This document describes how to connect your ISP to Plivo. The interconnection to a SIP trunk needs you full attention in all of its nuances. 

# 1. Planning

![image](https://user-images.githubusercontent.com/4958202/230954433-c29afe00-bbba-47bb-ad59-786bb04a8d61.png)

## 1.1 Codecs

The system will use PCMU to connecto to PLIVO at this point. There are no specific settings on PLIVO to change this. 

## 1.2 Caller ID for outgoing calls

Fortunately, PLIVO accepts caller ids in +e164 format, so no conversion is required.

## 1.3 - Normalization of the destination number

Again PLIVO accepts everything in +e164 format, so no conversion required

## 1.4 - Firewall rules

You should add the address of your SBC to the PLIVO ACL. 

## 1.5 - Authentication

We are going to use the IP ACL from PLIVO

# 2. Configuring an inbound trunk on PLIVO

## 2.1 Create an Outbound Trunk on Plivo

![image](https://user-images.githubusercontent.com/4958202/230955958-996ab39c-3995-418f-979a-2548ae530068.png)

## 2.2 Create an IP Access List

Create an IP address for your SBC. The shared SBCs have the follogin addresses. (Ping the addresses by the name, they may change with time)

sbc-us.wehostvoip.io -> Located in United States ->   172.174.24.204\
sbc-br.wehostvoip.io -> Located in Brazil ->          20.226.38.150\
sbc-in.wehostvoip.io -> Located in India  ->          20.204.231.235

## 2.3 Credentials list 

Leave empty

# 3. Configure a carrier on WeHostVoIP

## 3.1 Add a carrier and gateways at wehostvoip

It is very simple to add a carrier and a PLIVO gateway.

![image](https://user-images.githubusercontent.com/4958202/230957225-dfc2e7ca-d717-416c-b415-fe0c647c7500.png)

Add the first gateway as the FQDN provided by PLIVO. 

**There is an important trick here**

Add a second gateway using the address **18.214.109.129**, this is an alias to all PLIVO address ranges. It will authorize inbound calls from PLIVO. Usually for normal trunks you could have simply added the SIP trunk gateways, but in this cases there are entire ranges of addresses. 

## 3.2 Add the Caller ID, I haighly recommend you to assigna a number on PLIVO and use here its Caller_ID.

## 3.3 Normalization - Not required

## 3.4 Firewall Rules and Authentication - Not required

## 3.5 Don't forget to add the country in the security group of the tenant (https://console.wehostvoip.io)

## 3.6 Test the call to any 800 number

# 4 Inbound Calls

## 4.1 Create an Inbound Trunk on PLIVO

For inbound calls you have to configure an inbound trunk

![image](https://user-images.githubusercontent.com/4958202/230961343-c24c6741-631c-4125-b2f6-a2035f220654.png)

## 4.2 Add the number acquired on PLIVO in the number inventory on ISP (https://isp.wehostvoip.io)

![image](https://user-images.githubusercontent.com/4958202/230961786-69576c05-ab21-43b2-b07e-1abf26ae6676.png)

## 4.3 Assign a number from inventory to an extension on the customer console (https://console.wehostvoip.io)

## 4.4 Test an inbound call, verify the Caller ID




