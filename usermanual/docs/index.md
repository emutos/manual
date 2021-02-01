# The EmuTOS User Manual

Welcome!

This is a work in progress, as is EmuTOS itself. Please bear with us as we improve it. Contributions are welcome.

## License

Erm, what is our license here? Gnu FDL? Creative Commons License?

## Audience

This manual is for EmuTOS users. For more on EmuTOS, see the [web site](https://emutos.sourceforge.io).

### What This Manual Covers

### What This Manual Doesn't Cover

Specific hardware. EmuTOS expects certain hardware, for example a 680x0 processor. It runs on Atari ST hardware, and a variety of other machines that roughly emulate the Atari ST. It also runs on a number of emulators, such as Hatari. Since this is a wide variety of hardware, we refer you to the documentation for that hardware.

Current releases give a detailed compatibility list in the file ``doc/status.txt``.

## Installation

In many cases, installation of a new operating system is covered by the hardware documentation.

### Getting EmuTOS

You can get the current release from the [EmuTOS web site](https://emutos.sourceforge.io/download.html). There are many files available for each version. Which one you want depends on the hardware you are using. For example, emutos-aranym-*.zip files are for the aranym emulator.

We highly recommend testing the zip file after you pull it in, especially if you aren't going to use it immediately. E.g. on Linux:

```
unzip -t file-name
```


### Atari

No-one at Atari anticipated that thirty years on people would still be hacking Atari computers, so they made little provision for upgrading their operating systems. But you can! Downloads are available at the [EmuTOS download](https://emutos.sourceforge.io/download.html) web site.

#### Hard or Floppy Drive

Installation on Atari hardware can be as simple as putting the right file in the right place. The existing operating system, typically TOS, boots, and as part of its boot process, executes whatever it finds in ``c:\auto``. The prg version of EmuTOS provides an executable, ``emutos*.prg``, which you can copy into ``c:\auto``. The floppy version of EmuTOS provides a floppy disk image with a hidden ``.sys`` file in its root directory.

This is slower than booting from ROM and uses main memory, so use it to try EmuTOS (or a new version of EmuTOS).

Get the emutos-prg-\*.zip or emutos-floppy-\* zip file. See the readme.txt file in the archive for more information.

#### Read Only Memory

Almost all Atari STs came with TOS in read only memory (ROM). Only a few very early ones expected to boot the operating system from mass storage, meaning, in those days, floppy disk. EmuTOS is not specific to any particular version of Atari hardware, except for the ROM space available. You will have to select the size of the EmuTOS image to download and burn to ROM (or, more likely, EPROM). If you are using an emulator, see the emulator's documentation for installing a new ROM image.

Get the emutos-XXXk*.zip file, where XXX is the size ROM of your hardware. For emulators, consult the emulator's documentation.

#### Cartridge

There is also a cartridge version, which goes in the game cartridge on Atari hardware. Due to the limited space available, it is English only and has no AES or desktop. It is [EmuCON](#emucon) only. For these reasons we suggest it only for very tight memory situations.

Get the emutos-cartridge*.zip file. See the readme.txt file in the archive for further instructions.

## EmuCON

## Glossary

* EPROM: Erasable Programmable Read Only Memory, reprogrammable ROM. Generally more useful in experimental situations.

* ROM: Read Only Memory, usually not reprogrammable. See also EPROM.


## Resources

Also see the [EmuTOS links page](https://emutos.sourceforge.io/links.html).

* The [EmuTOS web site](https://emutos.sourceforge.io/).
