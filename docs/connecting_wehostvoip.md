# Connecting your ISP to a Carrier

In this chapter we are going to integrate WeHostVoIP with signalwire and AWS voice connector. 

You can connect to any virtually any SIP service provider. In this section we will show you how to connect to AWS voice connector. The reason we are using AWS is because it is simple and largely available. We do not endorse or recommend AWS Voice connector, we are just using it as an example. If you are a service provider and wants to be features at WeHostVoIP, get in contact. 

Step 1 - Creating the SIP trunk

Access the CHIME console on AWS

https://console.chime.aws.amazon.com/

Step 2 - Create a new voice connector

Calling=>Voice Connector

* Name: gettingstarted
* Region (east-se - N.Virginia)
* Encryption: Disabled.

![image](https://user-images.githubusercontent.com/4958202/153879892-fb23e423-ecce-42d5-ac72-6d9a482f9548.png)

Step 3 - Create a termination

Click in getting started

Select the tab **Termination** 

Set enabled and suthorize the address demo.wehostvoip.io. When recording the instructions the host was 44.196.134.37. Use ping to demo.wehostvoip.io and confir this address pelase. It may change in the future. 

![image](https://user-images.githubusercontent.com/4958202/153880399-2980628f-b5f8-4939-96f1-e869482a8ff1.png)

![image](https://user-images.githubusercontent.com/4958202/153880754-4883710f-32e1-4309-9ea7-36a4e6ef719d.png)

Set calls per second to 1, calling plan, authorize only your own country. No credentials required the IP is authorized. 

Step 4 - Create a new carrier

Now you will need to create a carrier and gateway in the WeHostVoIP side. When creating a gateway add the outbound host name as the address and from domain. 

![image](https://user-images.githubusercontent.com/4958202/153885655-f3177ec0-57b1-48b6-9f21-ad1ff8babc96.png)

After adding the gateway associate to the carrier. In the description set AWS-CHIME

![image](https://user-images.githubusercontent.com/4958202/153885698-6088271c-b336-4bd2-828d-db32c99f18e1.png)

Once the termination is created you should be able to call other numbers in US. 

Step 5 - Assign a phone number

AWS does not support receiving calls without a Caller ID in the E164 format. So let's assing a new nember. Allocate a phone number on AWS-CHIME on

calling=>phone number management. 

Allocate one number and associate it with your connector. 

![image](https://user-images.githubusercontent.com/4958202/153887696-6bd46880-d549-4a6d-b2a5-0cf6247f926e.png)



Step 5 - Change the carrier in the Tenant

To use this carrier, you have to change it in the tenant configuration (ISP interface)

![image](https://user-images.githubusercontent.com/4958202/153886446-6ed243e5-34f3-4f08-abf9-2ef5a0168025.png)


Step 6 - Try to make an external call 


