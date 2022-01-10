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

* CallerID
* Alias
* Daterange
* Visual Plan
* Security Group
* Concurrent Calls
* Timeout
* Call Group 
* Pickup Group
* Call Forward
* Forward on Busy
* Forward on No Answer
* Softphone Password

# Groups

# Phone Numbers

# Time Periods

# Security Groups

# Reports

# Visual Dialplan

# Audios
