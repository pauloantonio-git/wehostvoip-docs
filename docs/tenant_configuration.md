# Tenant Configuration #

Now we will start to configure the Tenant. The Tenant is the actual Virtual PBX. There we will create our extensions also known as subscribers. It was created to be as simple asn possible. Below you can see a view of the Tenant Interface.

![image](https://user-images.githubusercontent.com/4958202/148843917-d17d34dc-7e12-4757-a3c1-ac82a7342cd1.png)

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

![image](https://user-images.githubusercontent.com/4958202/148846028-05bae38c-a5e0-4a28-86db-a08367b4145a.png)

The first three fields are self explanatory. 

* Username - The username without the email
* Email - User's email 
* Password - SIP password
* Facility Pin - This pin number may be used in the future to authenticate some features
* Country Code - The code of the country. The dialplan uses this code (_CC_) in the dialplan prefixed by an underscore _
* Area Code - The area code where this applies. The dialplan uses this code (_AC_) for normalization prefixed by an underscore
* Voicemail to Email - Following our mantra of simplicity, the voicemail to email is simply to get the caller's message and send thru email to the subscriber

## Advanced Parameters

![image](https://user-images.githubusercontent.com/4958202/148846974-2123d80d-2c6f-475d-8df3-fcb92c7938e6.png)

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

# Phone Numbers

# Time Periods

# Security Groups

# Reports

# Visual Dialplan

# Audios
