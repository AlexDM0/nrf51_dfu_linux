Python nrf51822 DFU uploader
============================

Wrapper for bluez gatttool using pexpect to achive DFU 
uploads to the nrf51822 (SDK 5.1.0 and S110 SoftDevice 6.0.0). 

The script does not handle any notifications given by the 
peer as it is strictly not needed for simple uploads.

Inspired by the gatttool wrapping solution by Michael 
Saunby (https://github.com/msaunby/ble-sensor-pi).

## System:

* Linux Mint 16 - kernel 3.11.0-12-generic (Ubuntu works as well)
* bluez - 4.101-0ubuntu8b1

## Prerequisite:

Prior to running, install:
 
    sudo pip install pexpect
    sudo pip install intelhex --allow-unverified intelhex

## Usage:

You'll need the .hex file (not the .bin file) to upload. Use objcopy to create it if you don't have it. Then run:

    python dfu.py -f <hex_file> -a <address>

To figure out the address of DfuTarg do a hcitool lescan:

    $ sudo hcitool -i hci0 lescan
    LE Scan ... 
    CD:E3:4A:47:1C:E4 DfuTarg
    CD:E3:4A:47:1C:E4 (unknown)

Copyrights:

Fork from: https://bitbucket.org/glennrub/nrf51_dfu_linux


