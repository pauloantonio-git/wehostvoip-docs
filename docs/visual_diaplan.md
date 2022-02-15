# Visual Dialplan

The Visual Diaplan is one of the greatest differentiators of the system. It is simple to use and vizualize. The call will go thru node by node doing all the telephony functions such as playback, ivr and others.  

The first screen of the dialplan is to create or open it and to define timezone and timeperiod. 

<img src="https://user-images.githubusercontent.com/4958202/148941326-41d8f50b-f1e7-428f-9f87-ff133658c24c.png" width="480">

If you decide to create a new Visual Dialplan, fill the name, the timezone and the time period. This is very important.  Once you have selected this parameters you can start creating your Visual Dial Plan

![image](https://user-images.githubusercontent.com/4958202/148945818-aa6fe3a2-345d-4503-82a0-24dfcde0bbb2.png)

In the figure above you can see the main commands of the Visual Dial Plan Editor

The first buttons are the simplest

* New
* Open
* Edit Info (Timezone, Time Period,  Name)
* Save
* Undo
* Redo
* Arrange
* Upload JSON (Pro Edition)
* Download JSON (Pro Edition)

In the system you can organize the boxes in a logical way to process your incoming calls. Let's see an example below.

![image](https://user-images.githubusercontent.com/4958202/148946911-c2860fb9-2f20-4209-8d12-498ae46f7858.png)

There are different types of block to build your visual dialplan. I'm going to list them below, by clincking in the link you will have a more detailed view of each block

* [Start](#start)
* Group
* Hangup
* Ivr
* Playback
* Say
* Subscriber
* Timerouting
* Voicemail
* Visual Plan

# Start
The block start is just the starting point of the Visual Dial Plan (VDP). It is automatically positioned in the VDP.

![image](https://user-images.githubusercontent.com/4958202/148984484-dcefe8ed-b0b4-42d0-ba6b-64d6507121af.png)

# Group
Group is similar to a queue. It will ring on all phones at the same time. For serial hunt groups you may use the subscriber block. 

![image](https://user-images.githubusercontent.com/4958202/148984695-ead6e82d-5c46-4362-b197-c6a0fef99939.png)


# Hangup
Disconnect the call.

![image](https://user-images.githubusercontent.com/4958202/148984900-03704c89-71df-4d46-8a95-ac95251bd0e5.png)

# Ivr
Interactive Voice Response or IVR is one of the most sophisticated blocks of the VDP.

![image](https://user-images.githubusercontent.com/4958202/148985005-bc03f981-eaf1-45ec-b8fd-bdfa9fcd1382.png)

The main options of the block:

* Auto-Attendant - If you select auto-attendant, the system will allow you to dial the extension to go directly to the subscriber
* Timeout - Time to wait for a dtmf input
* Type - If _Audio Library_ where you can select a pre-recorded audio or text-to-speech if you prefer to generate the text on the fly.
* Insert Audio - Only if audio library. Select a pre-recorded audio (Formats wav and mp3)
* Text - Text to be played. Once played, the audio will be cached to avoid regeneration. 
* Language - Select the languages supported
* Text-Type - [SSML](https://en.wikipedia.org/wiki/Speech_Synthesis_Markup_Language) Speech Synthesis Markup Language or Text
* Sentence-Type - Sentence, SSML and Word
  * word – Indicates a word element in the text.
  * ssml – Describes a <mark> element from the SSML input text. For more information, see Generating Speech from SSML Documents. 




