pySim-prog is a small command line utility written in python, which is used for programming various programmable SIM/USIM cards.

Most of the content here is mainly from [1]. Take a look at thw wiki for more info.

pySim-prog is a small command line utility written in python, which is used for programming various programmable SIM/USIM cards.

Main concepts:

######pySim-read

Trying to read a regular operator SIM with PIN protection
```
 ./pySim-read.py -p0
Reading ...
ICCID: 8949228183706791977
IMSI: Can't read, response code = 9804
SMSP: Can't read, response code = 9804
ACC: Can't read, response code = 9804
MSISDN: Can't read, response code = 9804
Done !

```

Trying to read programmable SIM - the Troopers SIM in our case

```
$ ./pySim-read.py -p0
Reading ...
ICCID: 8901262230000902145
IMSI: 262230000090214
SMSP: ffffffffffffffffffffffffe1ffffffffffffffffffffffff0581005155f5ffffffffffff000000
ACC: ffff
MSISDN: Not available
Done !

```

###### Check the status of connection by entering the following command:

 ```
pcsc_scan
```


###### Programmable SIM cards
These are SIM/USIM cards which - unlike those issued by regular commercial operators - come with the kind of keys that allow you to write the files/fields that normally only an operator can program.
If you are running your own cellular network, then you will need a SIM card provisioning tool such as pysim for programming the SIM card with your own keys. 

Checkout [1] and follow the example to program your SIM card. Understand the various parameters used while programming. 

Reference:

[1] pysim wiki: https://osmocom.org/projects/pysim/wiki
