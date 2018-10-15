pySim-prog is a small command line utility written in python, which is used for programming various programmable SIM/USIM cards.

Lets play first with pysim wiki.
pySim-prog is a small command line utility written in python, which is used for programming various programmable SIM/USIM cards.

###### Main concepts:

1. Programmable SIM cards
2. Security in SIM - PIN, PUK, ADM
3. ki 

###### Scan and figure out the type of SIM you got

```
$ pcsc_scan
 PC/SC device scanner
 V 1.4.25 (c) 2001-2011, Ludovic Rousseau ludovic.rousseau@free.fr
 Compiled with PC/SC lite version: 1.8.14
 Using reader plug'n play mechanism
 Scanning present readers...
 0: SCM Microsystems Inc. SCR 3310 [CCID Interface] 00 00 
 Tue Oct 18 11:48:08 2016
 Reader 0: SCM Microsystems Inc. SCR 3310 [CCID Interface] 00 00
 Card state: Card inserted, 
 ATR: 3B 99 18 00 11 88 22 33 44 55 66 77 60
 + TS = 3B --> Direct Convention
 + T0 = 99, Y(1): 1001, K: 9 (historical bytes)
  TA(1) = 18 --> Fi=372, Di=12, 31 cycles/ETU
  129032 bits/s at 4 MHz, fMax for Fi = 5 MHz => 161290 bits/s
  TD(1) = 00 --> Y(i+1) = 0000, Protocol T = 0 
 -----
 + Historical bytes: 11 88 22 33 44 55 66 77 60
 Category indicator byte: 11 (proprietary format)
 Possibly identified card (using /usr/share/pcsc/smartcard_list.txt):
 3B 99 18 00 11 88 22 33 44 55 66 77 60
 sysmocom sysmoSIM-GR1
```

###### Read from your SIM

```
./pySim-read.py -p0
```
