# Tenant Configuration #

Now we will start to configure the Tenant. The Tenant is the actual Virtual PBX. There we will create our extensions also known as subscribers. It was created to be as simple asn possible. Below you can see a view of the Tenant Interface.

<img src="https://user-images.githubusercontent.com/4958202/148843917-d17d34dc-7e12-4757-a3c1-ac82a7342cd1.png" width="640">

It is a beautiful interface with the objective to make the system easy and intutitive to use. PBXs are not very simple, but we tried hard to make this the simplest possible. In this interface you can create:

* [Subscribers](#subscribers)
* [Groups](#groups)
* [Phone Numbers](#phone-numbers)
* [Time Period](#time-periods)
* [Security Groups](#security-groups)
* [Reports](#reports)
* [Visual Dialplan](#visual-dialplan)
* [Audios](#audios)

Lets cover one by one of the items above

# Subscribers

Subscribers are the users if the system. In this PBX the username is usually the email of the user. The extension is set in the alias field. There are many fields in the system so let's print the screen and describe all the fields. 

<img src="https://user-images.githubusercontent.com/4958202/148846028-05bae38c-a5e0-4a28-86db-a08367b4145a.png" width="640">

The first three fields are self explanatory. 

* Username - The username without the email
* Email - User's email 
* Password - SIP password
* Facility Pin - This pin number may be used in the future to authenticate some features
* Country Code - The code of the country. The dialplan uses this code (_CC_) in the dialplan prefixed by an underscore _
* Area Code - The area code where this applies. The dialplan uses this code (_AC_) for normalization prefixed by an underscore
* Voicemail to Email - Following our mantra of simplicity, the voicemail to email is simply to get the caller's message and send thru email to the subscriber

## Advanced Parameters

<img src="https://user-images.githubusercontent.com/4958202/148846974-2123d80d-2c6f-475d-8df3-fcb92c7938e6.png" width="640">

* CallerID - Overwrite the current Caller ID, Ex. 12093456789
* Alias - The extension number to be associated to this user. Useful if you are using hard phones (Ex. 8580)
* Visual Plan - Visual Plan associated with this user, if you want to handle incoming calls in a special way (special)
* Security Group - What International destinations are allowed for this user. Very important to prevent fraud (Ex. UK, Canada...)
* Concurrent Calls - Maximum concurrent calls per user. Please allow at least two for 3-Way Conference and Transfers (ex. 2)
* Timeout - Timeout for call (ex. 20)
* Call Group  - Call group in use for call pickup (ex. 1)
* Pickup Group - Usually the same as the call group (ex. 1)
* Call Forward - Number to forward unconditionally, use the same format as you dial in the phone (ex. 2345678)
* Forward on Busy - Forward if busy (ex. 12092345678)
* Forward on No Answer - Forward if the other side do not attend before the timeout (ex. 12092345678)
* Softphone Password - Password for SIP softphone provisioning

# Groups
You can dial a group by the group name. Also you can add a group to the Visual Dialplan. In the Visual Dialplan you can select if you prefer to dial sequentially or in paralell. groups are similar to queues but much simpler. 

<img src="https://user-images.githubusercontent.com/4958202/148850672-b6d78c0c-91cd-4b40-adcb-b39d29afb883.png" width="640">

It is very easy to create a group and add users to it. 

# Phone Numbers
In the phone numbers menu, you can assign numbers from the number inventory to a user or to a Visual Dialplan. 

<img src="https://user-images.githubusercontent.com/4958202/148850814-e73a47f5-79d2-46cd-9fb2-d3aec742a8a0.png" width="640">

You can use the request form to ask for an specific number or you can assign a number to an user. 

To request a number, simply fill the form below with the information required. 

<img src="https://user-images.githubusercontent.com/4958202/148850942-e510f50d-00c5-486c-a16d-38ecc4378584.png" width="480">

To select an existing number from hte inventory, please choose **Create Number**. There you can select one of the numbers assigned to your tenant. 

<img src="https://user-images.githubusercontent.com/4958202/148851316-6614c481-a6de-49f2-b822-e02021b0b5e4.png" width="480">

# Time Periods
Time periods are very useful to handle calls on and off business hours. You can define the different time periods. These time periods can be used in the Visual Dialplan. 

<img src="https://user-images.githubusercontent.com/4958202/148851494-79458418-8957-4eab-a4a6-e7ef08c42b31.png" width="640">

Set a name to your time period and select the ranges you want to support. 

# Security Groups
One of the biggest problems when using an IP PBX is toll fraud. To avoid Toll Fraud, all international destinations are disabled by default. To enable an international destination, you have to include the country or the prefixes in the Security Groups. You can create several different security groups and associate them to a subscriber. 

<img src="https://user-images.githubusercontent.com/4958202/148851919-662c65e4-0663-4669-9030-e2079ce5eb5c.png" width="640">

To associate to a subscriber, simply select one for the user in the Subscriber tab. 

# Reports

<img src="https://user-images.githubusercontent.com/4958202/148853956-f9cb5383-a17c-46af-89f3-4adf6ac8f075.png" width="800">

All calls generate a Call Detail Record. This reporting systema always have two legs. The incoming and the outgoing leg (A and B). The advantage of the dual leg reporting os the possibility to charge even for incoming legs. In the picture above you can see all the fields and filter. 

* Time - Internally all the CDRs are generated using the UTC. In the display the Time will be presented in the Browsers's time zone
* Caller ID - The Caller ID of the call as describer in the SIP From URI
* Callee ID - The destination or Callee ID of the call after normalization to the E164 format
* Leg-Type - Type of the leg SIP (VoIP Leg), DID (Incoming DID number), Toll-Free (Incoming 1-800 number), PSTN (Outgoing number to the PSTN)
* Direction - Inbound or Outbound
* Duration - Real Duration of the Call
* Setup Time - Time to setup a call from the start to the answered state
* SIP Code - Final code of the call
* SIP Reason - Final reason of the call
* Price - Computed Price of the call

Advanced data

Clicking in the "eye" icon in the right side of the report line, you can see the details of the call 

<img src="https://user-images.githubusercontent.com/4958202/148854757-6be90503-bfa5-4ac5-b12e-20138d647d8a.png" width="640">

There you can see the details on how the call was rated to get to the final price

* Price - Price of the call
* Credit Taken - Credit removed in this call
* Billing Duration - Duration for the purposes of billing (Considers the minimum duration, increment and delay)
* Increment (Increment of the call in seconds)
* Delay (Start charging after this delay time in seconds)
* Rate (The rate of a call per minute)
* Minimum Duration (Minimum duration in seconds)
* Prepaid (If the call was prepaid)
* Currency (The currency of the customer)

It is important to understand the concept of minimum duration, increment and delay and hot it affects the billing duration

We are going to express the parameters as Minimum Duration/Increment/Delay, see the examples below:

Real Duration 47s - Billing Duration in 30/6/3 = 48s (30+6+6+6)
Real Duration 2s - Billing Duration in 30/6/3 = 0s (Below delay)
Real Duration 10s - Billing Duration in 30/6/3 = 30s (Below minimum duration but above delay)
Real Duration 10s - Billing Duration in 1/1/0 = 10s (1+9x1)

There are some additional data such as call-id, from-tag and to-tag identifying the SIP dialog. This information can be useful for troubleshooting

# Audios

In the Audios Menu, you can upload new Audios. The Default audio is very important. The system uses the Default audio as the Music On Hold and it should not be deleted. The interface is simple and intuitive. The audios generated in the audio menu may be used in the Visual Dial Plan. 

![image](https://user-images.githubusercontent.com/4958202/148940330-e973c785-8671-42f0-a4e5-aca1224cdad1.png)


# Visual Dialplan
The visual dial plan is so sophisticated that we decided to create an specific page for the feature

[visual dialplan](visual_dialplan.md)

