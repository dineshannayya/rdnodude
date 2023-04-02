# Riscduino_Dude

[![Build Status](https://github.com/dineshannayya/riscduino_dude/actions/workflows/build.yml/badge.svg)](https://github.com/dineshannayya/riscduino_dude/actions/workflows/build.yml)

Riscduino_Dude - Riscduino SOC Downloader Uploader - is a program for downloading and uploading
the on-chip memories of Riscduino’s [Riscduino SOC](https://github.com/dineshannayya/riscduino).
It can program the Flash and EEPROM, and where supported by the programming protocol, it can program fuse and lock bits.

## Documentation


## Getting Riscduino_Dude for Windows

Windows Driver is not yet planned

## Getting Riscduino_Dude for Linux

To install Riscduino_Dude for Linux, install the package `riscduino_dude` by running the following commands:

```console
sudo apt-get install riscduino_dude
```

## Getting AVRDUDE for MacOS

MacOS Driver is not yet planned


## Using riscduino_dude

riscduino_dude is a command-line application. Run the command `riscduino_dude` without any arguments for a list of options.

A typical command to program your HEX file into your AVR microcontroller looks like this:

```console
riscduino_dude -c <programmer> -p <part> -U flash:w:<file>:i
```

For instance, to program an **Riscduino Score** connected to the serial port **COM1** with a HEX file called `blink.hex`,
you would run the following command:

```console
riscduino_dude -c riscduino_score -P COM1 -b 115200 -p score -D -U flash:w:objs/blink.hex:i
```

## Reference
This developement is forked from orginal code of [AVRDUDE](https://github.com/avrdudes/avrdude)
