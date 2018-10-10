
The usermanual for the software used is here: Osmo-nitb : http://ftp.osmocom.org/docs/latest/osmonitb-usermanual.pdf
Osmo-nitb (https://osmocom.org/projects/osmonitb/wiki/OsmoNITB) is the legacy version. However, this is the perfect way to get started as it is  

In this section, the goal is to get familiarised with the configuration of the setup. Below are some interesting parameters/concepts to get familiarised with. 

1. Does the configuration has encryption?

hint: Check osmo-bsc.cfg in /cfg folder. Under network configuration, there is an encryption field. You can enable encryption values with this. Figure out what encryption is used.  

2. What is the country code within the configuration?

hint: Check osmo-bsc.cfg in /cfg folder. Might be interesting to figure out what is the country code of your coutry. Reference: http://www.mcc-mnc.com/

3. What is the network code?

This is the code that is defined for each provider for each country. When you build your own base station, you can pick a value which is unique. Find the mnc value of your personal SIM card provider from here: http://www.mcc-mnc.com/

4. What is the ARFCN value used in the BTS?

The Absolute Radio Frequency Channel Number (ARFCN) is a unique number given to each radio channel in GSM. The ARFCN can be used to calculate the exact frequency of the radio channel. http://www.telecomabc.com/a/arfcn.html

5. Which band is the BTS configured to work on?

Also try to figure out what are the regular GSM bands based on different countries. https://en.wikipedia.org/wiki/GSM_frequency_bands

6. What type of bts are we using ?

Take a look at the hardware ;) You will also find it configured in the configs. 

7. What is the authentication policy that is used? 

For pentesting of a device the best authentication option is to accept all connections trying to authentication against our network. However, there is a chance that this could accidently IMSI catch your friends near by. 


