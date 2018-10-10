####Get the software
In order to run simtrace, we need the necessary software.
Follow the instructions in https://osmocom.org/projects/simtrace2/wiki to install the software. 

######simtrace2-list
```
./simtrace2-list
USB matches: 1
    1d50:60e3 Addr=4, Path=2-2.3, Cfg=1, Intf=0, Alt=0: 255/1/0 (SIMtrace Sniffer)
```

######simtrace2-sniff
```
sudo ./simtrace2-sniff 
[sudo] password for priya: 
simtrace2-sniff - Phone-SIM card communication sniffer 
(C) 2010-2017 by Harald Welte <laforge@gnumonks.org>
(C) 2018 by Kevin Redon <kredon@sysmocom.de>

Using USB device 1d50:60e3 Addr=12, Path=1-1, Cfg=1, Intf=0, Alt=0: 255/1/0 (SIMtrace Sniffer)
Entering main loop
Card state change: reset asserted
Card state change: reset de-asserted
ATR: 
PPS: ff 10 96 79 
PPS: ff 10 96 79 
Fi/Di switched to 512/32
TPDU: 00 a4 00 04 02 3f 00 61 56 
TPDU: 00 c0 00 00 56 62 54 82 02 78 21 83 02 3f 00 a5 19 80 01 71 83 02 7f ff cb 0d 00 00 00 00 00 00 00 00 00 00 00 00 00 ca 01 82 8a 01 05 ab 1b 84 01 2e 90 00 84 01 88 a4 06 83 01 01 95 01 08 84 01 fc a4 06 83 01 0a 95 01 08 c6 0f 90 01 70 83 01 01 83 01 0a 83 01 0b 83 01 81 90 00 
TPDU: 00 a4 08 04 02 2f e2 61 20 
TPDU: 00 c0 00 00 20 62 1e 82 02 41 21 83 02 2f e2 a5 06 c0 01 00 ca 01 80 8a 01 05 8b 03 2f 06 04 80 02 00 0a 88 00 90 00 
TPDU: 00 b0 00 00 0a 98 88 12 01 00 00 00 17 58 f5 90 00 
TPDU: 00 a4 00 04 02 2f 05 61 25 
TPDU: 00 c0 00 00 25 62 23 82 02 41 21 83 02 2f 05 a5 0a c0 01 00 cd 02 ff 01 ca 01 84 8a 01 05 8b 03 2f 06 05 80 02 00 0a 88 01 28 90 00 
TPDU: 00 b0 00 00 0a ff ff ff ff ff ff ff ff ff ff 90 00 
TPDU: 80 10 00 00 1e ff ff ff ff 7f 9c 00 df 9f 00 00 1f e2 00 00 00 c3 f9 00 07 00 01 e0 00 50 00 00 00 00 18 90 00 
TPDU: 00 a4 00 04 02 2f 00 61 24 
TPDU: 00 c0 00 00 24 62 22 82 05 42 21 00 26 02 83 02 2f 00 a5 06 c0 01 00 ca 01 80 8a 01 05 8b 03 2f 06 04 80 02 00 4c 88 01 f0 90 00 
TPDU: 00 b2 01 04 26 61 19 4f 10 a0 00 00 00 87 10 02 ff ff ff ff 89 07 09 00 00 50 05 55 53 69 6d 31 ff ff ff ff ff ff ff ff ff ff ff 90 00 
TPDU: 00 b2 02 04 26 ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff 90 00 
```

###### Wireshark capture
Open wireshark and start listening on localhost.
The packets are seen as UDP packets with GSM_SIM dissector
