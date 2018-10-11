We are going to use S6 SAMSUNG phones and O2 simcards for the testing. 
If you have your own phones and VoLTE enabled SIM cards, that is ok too. But things might differ based on the provider. 

###### Voice over LTE (VoLTE) interface
Get a shell in the android phone with adb. 

```
   $ adb shell 
   # su
   # ifconfig
```

The VoLTE interface is either named rmnet1 or rmnet0. The other one is the regular mobile data interface. 
The easiest way to figure out the right VoLTE interface is to turn of the VoLTE option on and off in phone. 
In Samsung phone, the VoLTE option can be found in the Mobile Network settings. 

###### SIP
Session initiation protocol generally used in Voice over IP (VoIP).
There are various interesting SIP messages such as REGISTER, INVITE, OPTIONS, BYE etc. This are describing the registering of SIM to the provider, inviting for a call session, terminating a call and so on. 


   

