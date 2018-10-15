We are going to use S6 SAMSUNG phones and O2 simcards for the testing. 
If you have your own phones and VoLTE enabled SIM cards, that is ok too. But things might differ based on the provider. 

Note: BASED ON RECENT TESTS AFTER COMING TO LUXEMBOURG, LOOKS LIKE THE SIMS DONT WANT TO DO VOLTE ANYMORE. SO IF YOU DONT SEE IT WORKING, IT IS NORMAL. 

###### Voice over LTE (VoLTE) interface
Get a shell in the android phone with adb. 

```
Sniffing VoLTE interface :

$ adb shell
$ tcpdump -i rmnet0 -n -s 0 -w - | nc -l 127.0.0.1 -p 11233
$ adb forward tcp:11233 tcp:11233 && nc 127.0.0.1 11233 | wireshark -k -S -i -

```

If you have issues with piping and stuff breaking, just try to save the tcpdump as a pcap and then pull that from the host machine. 
```
$ adb shell 
# tcpdump -i rmnet0 -w /sdcard/test.pcap 
# exit
$ adb pull /sdcard/test.pcap /working/directory/
```

The VoLTE interface is either named rmnet1 or rmnet0. The other one is the regular mobile data interface. 
The easiest way to figure out the right VoLTE interface is to turn of the VoLTE option on and off in phone. 
In Samsung phone, the VoLTE option can be found in the Mobile Network settings. 

###### SIP
Session initiation protocol generally used in Voice over IP (VoIP).
There are various interesting SIP messages such as REGISTER, INVITE, OPTIONS, BYE etc. These are describing the registering of SIM to the provider, inviting for a call session, terminating a call and so on. 

###### Capture the REGISTER packet
This is the first packet that is sent via the interface where the SIM card is actually registering with the LTE backend. 

An easy way to capture this packet is to turn the phone into flight mode and then switch off the flight mode. At this point, the phone tries to register with a SIP register request.
The capture should start immediately after the device is turned. There is a high chance to miss this packet if the capture doesnt start on time. 


###### Capture an VoLTE outgoing call
Make an outgoing call to any number with the Samsung phone. 
Keep listening with tcpdump on the VoLTE interface rmnet1. You should see the SIP INVITE messages, and SIP TRYING messages. 
Note that this would appear as ESP packets. 
ESP is part of IPSec. Encapsulation Security Protocol. 


###### Capture incoming call/ messages/ 
   
###### Interesting parameters
Try to observe the below parameters. 


i. What is the security header say ?

hint: Security-Verify

2. Client name ?

3. In case of incoming and outgoing calls, where do we find the caller and the callee address?

4. Which is the location info? 

hint: utran-cell-id-3gpp

5. IMEI number?

6. IMSI seen anywhere?


