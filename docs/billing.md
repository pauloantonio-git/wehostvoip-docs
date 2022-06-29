# Billing

One of the greatest differentiators of this system is the billing system. You will be capable of rate calls in real time in pre and post paid modes. The system was created to be simple and at the same time flexible. 

We can split the billing in two groups. Resources billing and call billing

## Resource billing

You can charge your customers by subscribers and by phone number AKA did (direct inward dial). The resources are billed everyday at 00:00 GMT. The monthly price is divided by the number of days in the month and it is charged everyday the proportional fraction of the month. 

## Call Billing 

The billing of calls is hierarchical, you can simply charge per subscriber per month. However there are cases where your monthly base rate does not cover all the costs. In this case you may want to add charges per minute of specific services or by prefix. On the other hand you may want to charge a fixed rate per minute for outgoing and even incoming calls. In this case the service-decks are handy. The system charges in the following way:

1 - Rate Deck charges if found
2 - Service Deck charges if found
3 - Monthly Charges

## Service Plans ##

You have to assign a service plan to each customer. It can be as simple as a monthly fee or very complex with rates per prefix. 

![image](https://user-images.githubusercontent.com/4958202/176325854-4d542629-5a5d-47c4-9bd6-30d14f9622ef.png)

In the service plan below, you have to fill:

* Name: A descriptive name of the service plan
* Monthly subscriber price: Fixed monthly price per subscriber
* Invoice Cut-off date: Informational field of when to consider the end of the month
* Currency: USD or other
* Prepaid or not

![image](https://user-images.githubusercontent.com/4958202/176325934-3e6c7370-0bf0-49c4-9746-ffbc833be7fe.png)

If you don't want to charge a fixed fee per subscriber, you can select a fixed price per service. There are services such as PSTN for fixed outgoing calls, mobile for mobile outgoing calls, DID for incoming calls, Toll-Free for incoming Toll-Free calls and SIP for calls to SIP legs (WebPhone or Softphone).

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

Sometimes it is not possible to have a flat fee for all destinations. If you are allowing International Destinations you may want to have specific prices per destination. In this case you can create a rate deck. Rate decks have precedence over Service Decks. You can specify now a rate per country such as below:

![image](https://user-images.githubusercontent.com/4958202/147946853-5de7775d-29c1-4fce-809b-5b9d02f302a0.png)

Rate decks can be imported from CSV. Just download the model, fill it and import it back in the system. 

### How to access the billing records

Billing records are exported daily to the S3 bucket associated with your ISP.  The billing records details the daily fees for subscriber, dids, fixed and mobile calls. The export is done using a standard CSV format. Consult us for more details in the file format. 
