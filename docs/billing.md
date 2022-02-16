# Billing

One of the greatest differentiators of this system is the billing system. You will be capable to rate calls in real time in pre and post paid modes. The system was created to be simple and at the same time flexible. 

The system is hierarchical, you can simply charge per month. However there are cases where your monthly base rate does not cover all the costs. In this case you may want to add charges per prefix. In the other hand you may want to charge a fixed rate per minute for outgoing and even incoming calls. In this case the service-decks are handy. The system charges in the following way:

1 - Rate Deck charges if found
2 - Service Deck charges if found
3 - Monthly Charges

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
