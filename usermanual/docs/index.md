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

## Compatibility

A list of programs that are known to be [incompatible with EmuTOS](https://github.com/emutos/emutos/blob/master/doc/incompatible.txt) is in the source tree. Often, these programs take advantage of undocumented aspects of TOS. These often break on different versions of TOS, sometimes on different languages in the same version of TOS, as well as on EmuTOS. Please check this list before reporting an EmuTOS bug.

Hatari users will find the [Hatari and EmuTOS](https://hatari.tuxfamily.org/doc/emutos.txt) document useful. However, check for the most [recent versions of EmuTOS](https://emutos.sourceforge.io/download.html).

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

This is slower than booting from [ROM](#rom) and uses main memory, so use it to try EmuTOS (or a new version of EmuTOS).

Get the emutos-prg-\*.zip or emutos-floppy-\* zip file. See the readme.txt file in the archive for more information.

#### Read Only Memory

Almost all Atari STs came with TOS in [read only memory (ROM)](#rom). Only a few very early ones expected to boot the operating system from mass storage, meaning, in those days, floppy disk. EmuTOS is not specific to any particular version of Atari hardware, except for the ROM space available. You will have to select the size of the EmuTOS image to download and burn to ROM (or, more likely, [EPROM](#eprom)). If you are using an emulator, see the emulator's documentation for installing a new ROM image.

Get the emutos-XXXk*.zip file, where XXX is the size ROM of your hardware. For emulators, consult the emulator's documentation.

#### Cartridge

There is also a cartridge version, which goes in the game cartridge on Atari hardware. Due to the limited space available, it is English only and has no AES or desktop. It is [EmuCON](#emucon) only. For these reasons we suggest it only for very tight memory situations.

Get the emutos-cartridge*.zip file. See the readme.txt file in the archive for further instructions.

### Other Hardware here....

## Booting

Sucessful initialization will produce a screen similar to this one.

![Screenshot](images/boot.screen.png)

*Above: EmuTOS boot screen*

The normal boot sequence is to initialize the hardware, then the operating system in ROM. If there is a game cartridge present, control passes to it. Otherwise the OS looks for a hard drive. If it finds one, it runs programs in ``c:\auto`` and loads accessories in ``c:\``. If there is no hard drive, the operating system looks for a floppy drive at A:. If it finds A:, the OS executes programs in ``a:\auto`` and loads accessories in ``a:``. However, you can bypass portions of that sequence as noted below.

There are a number of features to note about the boot screen.

- Probably the most important is that if you want more time to study the boot screen, you can hold a shift key down.

- The version of EmuTOS that is booting. This shows only major and minor revision numbers (e.g. 1.3) but not patch numbers (e.g. 1.3.2).

- The type of CPU found.

- The hardware found (or, as in this case, emulated).

- How much main memory was found.

- An enumeration of the floppy drives (A and B) and hard drives found.

- The time and date of the boot.

- Some useful functions:

    - Hold a control key down to bypass the ``c:\auto`` directory and installing accessories accessories. This is useful for debugging complicated boot sequences.

    - Hold down an Alternate key to bypass booting from a hard drive. This would allow booting from a floppy drive if one is present, or from ROM.

    - To boot from any drive, hold down its letter. For example, to boot from I: hold down the i key. This allows for different custom setups.

    - Hold the escape key down to bypass the desktop and go directly to [EmuCON](#emucon). This might also be useful for recovering from a boot sequence gone wrong.

The rest of that screen shot is from the Hatari emulator, so it is not documented here.

## EmuCON


## Reporting Bugs

Before you report a bug, you should probably search the EmuTOS [development mailing list's archives](https://sourceforge.net/p/emutos/mailman/emutos-devel/) to see if anyone else has reported your problem or something similar, and a possible solution.

To report bugs, or for other discussion about EmuTOS, please join the EmuTOS [development mailing list](https://sourceforge.net/projects/emutos/lists/emutos-devel). There are other, deprecated, ways to file bugs, but this allows anyone to join the discussion, and will usually get a faster response.

## Glossary

* <a id="eprom"></a>EPROM: Erasable Programmable Read Only Memory, reprogrammable [ROM](#rom). Generally more useful in experimental situations.

* <a id="rom" ></a>ROM: Read Only Memory, usually not reprogrammable. See also EPROM.


## Resources

Also see the [EmuTOS links page](https://emutos.sourceforge.io/links.html).

* The [EmuTOS web site](https://emutos.sourceforge.io/).
