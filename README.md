# RDNODUDE

[![Build Status](https://github.com/dineshannayya/rdnodude/actions/workflows/build.yml/badge.svg)](https://github.com/dineshannayya/rdnodude/actions/workflows/build.yml)

RDNODUDE - Riscduino SOC Downloader Uploader - is a program for downloading and uploading
the on-chip memories of Riscduino’s [Riscduino SOC](https://github.com/dineshannayya/riscduino).
It can program the Flash, and where supported by the programming protocol, it can program fuse and lock bits.

## Documentation


## Getting RDNODUDE for Windows

Windows Driver is not yet planned

## Getting RDNODUDE for Linux

To install rdnodude for Linux, install the package `rdnodude` by running the following commands:

```console
./build.sh
sudo cmake --build build_linux --target install
```

Standalone run command assuming hello_world.hex file

```console
rdnodude -c riscduino -U flash:w:hello_world.hex:i -b 9600 -P /dev/ttyUSB0 -p rd32d100 -v -v
```


## Getting RDNODUDE for MacOS

MacOS Driver is not yet planned

## Fixing the access issue in ubuntu


```console
#find the ftdi ttyUSB* port
dmesg | grep tty 

#On Linux to access the serial port the user must be part of 2 groups dialout/tty
sudo gpasswd --add <your user name>  dialout
sudo gpasswd --add <your user name>  tty
sudo chown $USER: /dev/ttyUSB2

```

## Using rdnodude

rdnodude is a command-line application. Run the command `rdnodude` without any arguments for a list of options.

A typical command to program your HEX file into your Riscduino microcontroller looks like this:

```console
rdnodude -c <programmer> -p <part> -U flash:w:<file>:i
```

For instance, to program an **Riscduino Score** connected to the serial port **COM1** with a HEX file called `blink.hex`,
you would run the following command:

```console
rdnodude -c riscduino -P COM1 -b 115200 -p score -D -U flash:w:objs/blink.hex:i
```

## Reference
This developement is forked from orginal code of [AVRDUDE](https://github.com/avrdudes/avrdude)
