# ISP Configuration #

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

## Customers ##

In the customer's box you can list, delete and create new customers. To create a new customer fill the form below:

![image](https://user-images.githubusercontent.com/4958202/147887779-9b53689d-6e67-4db2-a8b4-0b38fc52534b.png)

Most of the options are solf-explanatory, however in the end of the form you should specify the service plan explaining how the customer will be charged and the maximum amount of subscribers and concurrent calls are allowed for this specific customer. 

## Carriers ##

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

## Number Inventory ##

The number inventory allows you to add phone numbers assigned to your ISP and make them available for your customers. You can control the phone numbers, also called DIDs (Direct Inward Dial) in your system and have a control of the numbers allocated. You can create, delete and update numbers. 

![image](https://user-images.githubusercontent.com/4958202/147890271-2fdfcfea-2a2c-4a37-ab1f-a946a6bddf80.png)

In this menu you can add new numbers, the main parameters for a number are:

* Number - The number itself in e164 format with the +
* Source - identifies the source of this number, in the example, allocated from AWS Voice Connector account
* Type - Local or Toll Free (Changes the billing)
* Price - The price to be charged from the customer in the end of the month
* Vendor Price - How much you are paying monthly for this number
* SMS/VOICE - If the number supports Voice and SMS

## Dial Plans ##

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

## Service Plans ##

You have to assign a service plan to each customer. It can be as simple as a monthly fee or very complex with rates per prefix. 

![image](https://user-images.githubusercontent.com/4958202/147943803-f886bdde-029b-45be-be51-86a7debea797.png)

In the service plan below, you have to fill:

* Name: A descriptive name of the service plan
* Monthly subscriber price: Fixed monthly price per subscriber
* Monthly DID price: Fixed monthly price per allocated phone number
* Invoice Cut-off date: Informational field of when to consider the end of the month
* Currency: USD or other
* Prepaid or not

![image](https://user-images.githubusercontent.com/4958202/147943999-51f1b250-b686-4f44-8529-f0f07ba0c5e1.png)

If you don't want to charge a fixed fee per subscriber, you can select a fixed price per service. There are services such as PSTN for outgoing calls, DID for incoming calls, Toll-Free for incoming Toll-Free calls and SIP for calls to SIP legs (WebPhone or Softphone).

### Service Decks ###

In the service deck below, there are charges per DID (incoming leg) and PSTN (outgoing leg), the parameters are:

* Rate: per minute rate in the customer's currency
* Date Start and Date End: When this rate should apply
* Min. Duration: Minimum duration in seconds of the call for billing purposes
* Increment: Increment in seconds for the call
* Delay: Start billing after the delay. 

Examples: 

Real Duration: 43 seconds
Min.Duration: 30s
Increment: 6s
Delay 3s
Billing Duration = 30+3x6 = 48 seconds (min duration + 3 increments)

Real Duration: 43 seconds
Min.Duration: 60s
Increment: 60s
Delay 3s
Billing Duration = 60 seconds (min. duration)

Real Duration: 2 seconds
Min.Duration: 60s
Increment: 60s
Delay 3s
Billing Duration = 0 seconds (below delay)

Real Duration: 4 seconds
Min.Duration: 60s
Increment: 60s
Delay 3s
Billing Duration = 60 seconds (min. duration)

![image](https://user-images.githubusercontent.com/4958202/147944591-e306a3f3-2537-4e6e-958e-a961a9381147.png)

### Rate Decks ###

Some times it is not possible to have a flat fee for all destinations. If you are allowing International Destinations you may want to have specific prices per destination. In this case you can create a rate deck. Rate decks have precedence over Service Decks. You can specify now a rate per country such as below:

![image](https://user-images.githubusercontent.com/4958202/147946853-5de7775d-29c1-4fce-809b-5b9d02f302a0.png)

Rate decks can be imported from CSV. Just download the model, fill it and import back in the system. 