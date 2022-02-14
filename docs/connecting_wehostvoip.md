# Connecting your ISP to a Carrier

To complete this tutorial you should have a valid account on AWS. 

In this chapter we are going to integrate WeHostVoIP with signalwire and AWS voice connector. 

You can connect virtually any SIP service provider. In this section we will show you how to connect to AWS voice connector. The reason we are using AWS is because it is simple and largely available. We do not endorse or recommend AWS Voice connector, we are just using it as an example. If you are a service provider and wants to be featured at WeHostVoIP, get in contact. 

## Step 1 Creating the SIP trunk on AWS

Access the CHIME console on AWS

https://console.chime.aws.amazon.com/

## Step 2 Create a new voice connector on AWS

Calling=>Voice Connector

* Name: gettingstarted
* Region (east-se - N.Virginia)
* Encryption: Disabled.

![image](https://user-images.githubusercontent.com/4958202/153879892-fb23e423-ecce-42d5-ac72-6d9a482f9548.png)

## Step 3 Create a termination on AWS

Click in getting started

Select the tab **Termination** 

Set enabled and suthorize the address demo.wehostvoip.io. When recording the instructions the host was 44.196.134.37. Use ping to demo.wehostvoip.io and confir this address pelase. It may change in the future. 

![image](https://user-images.githubusercontent.com/4958202/153880399-2980628f-b5f8-4939-96f1-e869482a8ff1.png)

![image](https://user-images.githubusercontent.com/4958202/153880754-4883710f-32e1-4309-9ea7-36a4e6ef719d.png)

Set calls per second to 1, calling plan, authorize only your own country. No credentials required the IP is authorized. 

## Step 4 Create a new carrier on WHV

Now you will need to create a carrier and gateway in the WeHostVoIP side. When creating a gateway add the outbound host name as the address and from domain. 

![image](https://user-images.githubusercontent.com/4958202/153885655-f3177ec0-57b1-48b6-9f21-ad1ff8babc96.png)

After adding the gateway associate to the carrier. In the description set AWS-CHIME

![image](https://user-images.githubusercontent.com/4958202/153885698-6088271c-b336-4bd2-828d-db32c99f18e1.png)

Once the termination is created you should be able to call other numbers in US. 

## Step 5 Assign a phone number on AWS

AWS does not support receiving calls without a Caller ID in the E164 format. So let's assing a new nember. Allocate a phone number on AWS-CHIME on

calling=>phone number management. 

Allocate one number and associate it with your connector. 

![image](https://user-images.githubusercontent.com/4958202/153887696-6bd46880-d549-4a6d-b2a5-0cf6247f926e.png)

## Step 6 Change the carrier in the Tenant on WHV

To use this carrier, you have to change it in the tenant configuration (ISP interface)

![image](https://user-images.githubusercontent.com/4958202/153886446-6ed243e5-34f3-4f08-abf9-2ef5a0168025.png)

## Step 7 Add the prefixes to the security group

Go to the security groups, add the prefixes for USA by selecting the country. Add also the prefix for toll free calls, add 18 as a prefix, it covers all variations of toll free calls.  

## Step 8 Try to make an external call

Call a toll free number such as 8004337300

## Step 9 Add the AWS number to the inventory

In the ISP interface go to number inventory and insert the number record. 

![image](https://user-images.githubusercontent.com/4958202/153927472-3781c1d5-7e23-45a9-82ed-bcdf452cb739.png)

The data to be inserted depends on the number allocated on AWS

After adding the number should appear in the system

![image](https://user-images.githubusercontent.com/4958202/153927704-dfce1b66-8ccf-471c-8cb6-3dffa82cfbe2.png)

## Step 10 - Associate the number to a user in WHV

In the tenant interface in phone number, create the number and associate to Alice. 

![image](https://user-images.githubusercontent.com/4958202/153927979-5bd640aa-21e4-46a7-b579-2915b9837fe3.png)

## Step 11 - Dial the number from an external phone

Check if the call has arrived ok. 




