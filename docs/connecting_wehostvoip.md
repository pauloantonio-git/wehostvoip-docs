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

Set calls per second to 1, calling plan, authorize only your own country. 
