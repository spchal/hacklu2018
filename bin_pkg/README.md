###### Installing tcpdump/socat on android

On your laptop:
```
$ adb push <path to tcpdump binary> /sdcard/
$ adb shell 

Inside adb shell 
# su 
# mount -o rw,remount /
# cp /sdcard/tcpdump /sbin/
# mount -o ro,remount /
# tcpdump -i rmnet0 -A
```

Repeat the same for socat if needed with socat binary instead of tcpdump


###### Installing simtrace2
Before you start, check the hardware you got for the version of the simtrace. If it is simtrace1, get the respective package from the wiki and follow the instruction. Below information is if the simtrace is version 2. (simtrace-v2)

Wiki link: https://osmocom.org/projects/simtrace2/wiki

Needed package install :
```
sudo apt-get install libusb-1.0-0-dev libosmocore-dev 
``` 

Compiling it :
```
git clone git://git.osmocom.org/simtrace2.git
cd simtrace2/host/
make
```

Once you have the binary, simply run ./simtrace2-sniff 

###### Installing pysim

All information is available in detail in the wiki. Please follow it accordingly:

https://osmocom.org/projects/pysim/wiki
