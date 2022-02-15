## Handling Incoming Calls with the Visual Dial Plan

For now, you have handled incoming calls directly to a subscriber. That's ok, however we have something much more sophisticated to receive incoming calls called the Visual Dial Plan. Follow the step by step instructions below to receive calls to an IVR.

For this getting started guide, we are going to handle incoming calls in this way:

1. Check if business hours. If on business hours, play the IVR else play a message telling the user what are our business hours. 
2. In the IVR, let's create a menu 1 for sales, 2 for finance, 3 for technical support. 
3. If the user does not type anything, or type an invalid number, retry 3 times
4. For sales, create a list of subscribers to rung sumultaneously
5. For technical support send the call to bob
6. For finance send call to alice

## Step 1 Create the business hours

Create a time period named default and set the time monday to friday from 9AM to 5PM like shown below. 

![image](https://user-images.githubusercontent.com/4958202/154132378-9d6729ff-5ef2-4c45-b66f-375e99d585b2.png)

## Step 2 Create a Visual Plan 

You will receive a screen like below

![image](https://user-images.githubusercontent.com/4958202/154132687-01e6fac2-0d88-4fa4-ae01-60afa695a8c4.png)

Add the timerouting block, create a playback if non business hours and an ivr if in business hours. 

![image](https://user-images.githubusercontent.com/4958202/154132917-e5acbffb-b66f-4a99-beba-2f7fbc4e1e96.png)

Now let's customize the message for off hours. Select text to speech, use Joanna as voice. 

![image](https://user-images.githubusercontent.com/4958202/154133123-82135458-37c6-48a0-b2ca-91833d2af4fd.png)

Then let's customize the IVR. The final visual plan should look like below. 

![image](https://user-images.githubusercontent.com/4958202/154133613-0f2384f8-09c9-4935-963f-ad17058dea0c.png)

**Don't forget to save your plan**

## Step 3 Associate a phone number to a Visual Plan

Create a subscriber called vdp (Visual Dial Plan)

![image](https://user-images.githubusercontent.com/4958202/154134154-9fa813c8-ab44-4534-8c20-439ee16f40d0.png)

Now in the phone number, change the user associated from Alice to vdp

## Step 4 Test an incoming call 



