## Handling Incoming Call Transfers and Call Pickup

Call transfers and call pickup alson known as call interception are simple features of the Cloud PBX. To maximize compatibility between devices we strongly suggest that you use the dtmf codes rather than the method REFER.

### Unattended Transfer

To process an Unattended transfer, after receiving the call dial \*1 , you will hear music on hold. Dial the number you want to transfer and press #. The call will be transferred imediately. 

### Attended Transfer

To process Attended transfer, after receiving the call dial \*2. You will hear a dial tone, dial the destination and talk to the destination while the first user is on hold. Put your phone on hook to complete the transfer, or simply disconnect. 

### Group Pickup

For group pickup, you will need to set the Call Group and Pickup Group for your users. The default call group and pickup group is 1. If a call is ringing in pne phone in the same pickup group as yours, you can pickup this call using the code \*8.

### Direct Pickup

For direct pickup, you have to dial \*86 plus the number of the extension you want to pickup (intercept). Example \*8660000. 

### Global Pickup

To intercept calls from any phone independent of the group you can use \*87. 

