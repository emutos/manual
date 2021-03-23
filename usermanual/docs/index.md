# The EmuTOS User Manual

Welcome!

This is a work in progress, as is EmuTOS itself. Please bear with us as we improve it. Contributions are welcome.

## Table of Contents

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Table of Contents**

- [The EmuTOS User Manual](#the-emutos-user-manual)
    - [Table of Contents](#table-of-contents)
    - [License](#license)
    - [Audience](#audience)
        - [What This Manual Covers](#what-this-manual-covers)
        - [What This Manual Doesn't Cover](#what-this-manual-doesnt-cover)
        - [Typography](#typography)
    - [Compatibility](#compatibility)
        - [Available Archives](#available-archives)
    - [Installation](#installation)
        - [Getting EmuTOS](#getting-emutos)
        - [Atari](#atari)
            - [Hard or Floppy Drive](#hard-or-floppy-drive)
            - [Read Only Memory](#read-only-memory)
            - [Cartridge](#cartridge)
        - [Amiga](#amiga)
        - [Other Hardware](#other-hardware)
    - [Booting](#booting)
    - [Rebooting](#rebooting)
    - [The Desktop](#the-desktop)
        - [Minimal Desktop](#minimal-desktop)
        - [Floppy Disk Only Desktop](#floppy-disk-only-desktop)
        - [Hard Drive](#hard-drive)
        - [Using the Desktop](#using-the-desktop)
            - [Saving the Desktop](#saving-the-desktop)
            - [Opening a Disk Drive or Directory](#opening-a-disk-drive-or-directory)
            - [File Selection](#file-selection)
            - [Copying and Moving Files](#copying-and-moving-files)
            - [File Information](#file-information)
            - [File Mask](#file-mask)
        - [Desktop Accessories](#desktop-accessories)
        - [Control Panel eXtensions](#control-panel-extensions)
    - [EmuCON](#emucon)
    - [Reporting Bugs](#reporting-bugs)
    - [Glossary](#glossary)
    - [Resources](#resources)

<!-- markdown-toc end -->

## License

Erm, what is our license here? Gnu FDL? Creative Commons License?

## Audience

This manual is for EmuTOS users. For more on EmuTOS, see the [web site](https://emutos.sourceforge.io).

### What This Manual Covers

### What This Manual Doesn't Cover

Specific hardware. EmuTOS expects certain hardware, for example a 680x0 or ColdFire processor. It runs on Atari ST hardware, and a variety of other machines that roughly emulate the Atari ST. It also runs on a number of emulators, such as Hatari. Since this is a wide variety of hardware, we refer you to the documentation for that hardware.

Current releases give a detailed compatibility list in the file ``doc/status.txt``.

Getting the current current git repository, or compiling the source.

### Typography ###

In this manual, a caret (^) indicates a control character. For example, ^I means hold down a control key and press the i key. The shift key is optional.

## Compatibility

A list of programs that are known to be [incompatible with EmuTOS](https://github.com/emutos/emutos/blob/master/doc/incompatible.txt) is in the source tree. Often, these programs take advantage of undocumented aspects of TOS. These often break on different versions of TOS, sometimes on different languages in the same version of TOS, as well as on EmuTOS. Please check this list before reporting an EmuTOS bug.

Hatari users will find the [Hatari and EmuTOS](https://hatari.tuxfamily.org/doc/emutos.txt) document useful. However, check for the most [recent versions of EmuTOS](https://emutos.sourceforge.io/download.html).

### Available Archives

These are the zip archive files available for download, where X.Y indicates the current release version. See below for how to use some of them. The source is also available from a git repository, which is beyond the scope of this document.

Multi-lingual versions will have multiple files. There are two differences: the language, Czech, French, etc., and the television format (NTSC or PAL) your hardware supports, if any. See the `readme.txt` file in the root directory of the zip file.

| File name | Use |
|-----------|-----|
| emucon-X.Y.zip              | EmuCON only as a .prg executable |
| emutos-192k-X.Y.zip         | 192 kilobyte [Atari ROM](#read-only-memory) image |
| emutos-256k-X.Y.zip         | 256 kilobyte [Atari ROM](#read-only-memory) image |
| emutos-512k-X.Y.zip         | 512 kilobyte [Atari ROM](#read-only-memory) image |
| emutos-amiga-floppy-X.Y.zip | [Amiga floppy diskette](#amiga) image |
| emutos-amiga-rom-X.Y.zip    | [Amiga ROM](#amiga) image |
| emutos-aranym-X.Y.zip       | Aranym (emulator) image |
| emutos-cartridge-X.Y.zip    | [Atari cartridge image](#cartridge) (EmuCON only) |
| emutos-firebee-X.Y.zip      | Firebee executable |
| emutos-floppy-X.Y.zip       | Emutos in an [Atari floppy diskette image](#hard-or-floppy-drive) |
| emutos-m548x-bas-X.Y.zip    |
| emutos-m548x-dbug-X.Y.zip   |
| emutos-pak3-X.Y.zip         |
| emutos-prg-X.Y.zip          | EmuTOS as an [Atari executable](#hard-or-floppy-drive) |
| emutos-src-X.Y.tar.gz       | Source code for this version, including some documentation not found elsewhere |

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

Installation on Atari hardware can be as simple as putting the right file in the right place. The existing operating system, typically TOS, boots, and as part of its boot process, executes whatever it finds in ``C:\AUTO``. The prg version of EmuTOS provides an executable, ``EMUTOS*.PRG``, which you can copy into ``C:\AUTO``. Or you can put it any place convenient, and launch it at will.

The floppy version of EmuTOS provides a floppy disk image with a hidden ``.SYS`` file in its root directory.

This is slower than booting from [ROM](#rom) and uses main memory, so use it to try EmuTOS (or a new version of EmuTOS).

Get the emutos-prg-\*.zip or emutos-floppy-\* zip file. See the readme.txt file in the archive for more information.

#### Read Only Memory

Almost all Atari STs came with TOS in [read only memory (ROM)](#rom). Only a few very early ones expected to boot the operating system from mass storage, meaning, in those days, floppy disk. EmuTOS is not specific to any particular version of Atari hardware, except for the ROM space available. You will have to select the size of the EmuTOS image to download and burn to ROM (or, more likely, [EPROM](#eprom)). If you are using an emulator, see the emulator's documentation for installing a new ROM image.

Get the emutos-XXXk*.zip file, where XXX is the size ROM of your hardware. For emulators, consult the emulator's documentation. Note that the 192K ROMs do not provide [EmuCON](#emucon), so you may prefer the 256K or 512K ROMs if your hardware will support them. However, you can add it to a disk with the ``emucon-X.Y.zip`` archive.

#### Cartridge

There is also a cartridge version, which goes in the game cartridge on Atari hardware. Due to the limited space available, it is English only and has no AES or desktop. It is [EmuCON](#emucon) only. For these reasons we suggest it only for very tight memory situations, or in the unusual case of bringing up new hardware.

Get the emutos-cartridge*.zip file. See the readme.txt file in the archive for further instructions.

### Amiga ###

### Other Hardware

## Booting

Successful initialization after power up or a hard reset will produce a screen similar to this one.

![EmuTOS boot screen](images/boot.screen.png "EmuTOS boot screen")

*Above: EmuTOS boot screen on an RGB screen*

The normal boot sequence is to initialize the hardware, then the operating system in ROM. If there is a game cartridge present, control passes to it. Otherwise the OS looks for a hard drive. If it finds one, it runs programs in ``C:\AUTO`` and loads accessories in ``C:\``. If there is no hard drive, the operating system looks for a floppy drive at A:. If it finds A:, the OS executes programs in ``A:\AUTO`` and loads accessories in ``A:``. However, you can bypass portions of that sequence as noted below.

There are a number of features to note about the boot screen.

- Probably the most important is that if you want more time to study the boot screen, you can hold a shift key down.

- The version of EmuTOS that is booting. This shows major and minor revision numbers (e.g. 1.3) and the patch number if one is present (e.g. 1.3.2).

- The type of CPU found.

- The hardware found (or, as in this case, emulated).

- How much main memory was found.

- An enumeration of the floppy drives (A and B) and hard drive partitions found. The boot drive is in reverse video.

- The time and date of the boot if EmuTOS finds a real-time clock. If no real-time clock is found, a bogus time and date will be shown in reverse video.

- Some useful functions:

    - Hold a control key down to bypass the ``C:\AUTO`` directory and installing accessories. This is useful for debugging complicated boot sequences.

    - Hold down an Alternate key to bypass booting from a hard drive. This would allow booting from a floppy drive if one is present, or from ROM.

    - To boot from any drive, press its letter. For example, to boot from I: press the i key. This allows for different custom setups.

    - Press the escape key to bypass the desktop and go directly to [EmuCON](#emucon). This might also be useful for recovering from a boot sequence gone wrong.

## Rebooting ##

There are two ways to reboot EmuTOS. Consult your hardware or emulator documentation for how to achieve them.

A hard reboot clears everything that has been done since power up. This is achieved with the reset button on most hardware. It is comparable to powering down and up again. A [boot screen](#booting) is shown.

A soft reboot stops the current program and returns control to EmuDESK. It may be achieved with Control-Alt-Delete keys. No [boot screen](#booting) is shown, and EmuTOS goes directly to EmuDESK.

## The Desktop

![Minimal EmuTOS desktop](images/minimal.atari.desktop.mono.png "Minimal EmuTOS desktop")

*Above: EmuTOS minimal desktop screen on a monochrome screen*

> I note the printer icon even though I configured Hatari not to have a printer. Is that correct? Should EmuTOS show a ghost printer?

### Minimal Desktop

If you have a minimal Atari system, this screen shot is what you will see: a plain desktop. It's not very interesting. Still, a few things to note.

You can bring the mouse pointer up to the Desk entry in the navigation bar. That will show you the Desk menu, with one entry: "Desktop info...". Click on that to see information about Emutos, including the version number.

The File menu will let you format a floppy, which isn't very useful without a floppy drive. It will also let you enter [EmuCON](#emucon). If [NatFeats](#natfeats) are enabled, you can use the last entry to power off your computer (or exit your emulator).

The View menu lets you select how you seen directories. You can also set the background and you can set a number of other preferences. You can also read a ``*.INF`` file, which is a desktop information file, similar to the Atari TOS ``DESKTOP.INF`` file. EmuTOS uses ``EMUDESK.INF``.

### Floppy Disk Only Desktop

![Floppy Desktop](images/floppy.atari.desktop.mono.png "Floppy Desktop")

*Above: EmuTOS minimal desktop screen with a floppy disk icon visible.*

If we add one floppy disk drive to the system, we get two floppy disk icons on the desktop. EmuTOS supports emulating floppy drive B: in physical floppy drive A:. This lets you copy floppies. It can be a bit awkward unless you have enough memory to accommodate an entire floppy disk in one go. E.g.: An Atari double sided double density floppy drive, like the Atari SF314 external floppy drive, has 720 kilobytes, so you would need at least 1 megabyte of memory. You can see how much free memory you have by going to Options -> Desktop configuration.

>> We recommend you consider mass storage other than floppy drives. You can now buy add-ons for Atari STs that emulate floppy drives and hard drives using solid state memory.

Now the File menu is more interesting. You can do a lot of typical file manipulations.

> One thing I don't see is the ability to move a file. I see it in EmuCon.

### Hard Drive


### Using the Desktop

Using a new (to you) computer is a bit like moving into a new home. "Where did we put that..." This section will walk you through some typical operations and some things that may make life a bit easier.

Many options also have shortcut keys, e.g. ^S to save the desktop. You can note these to the right of the menu entries.

Unlike TOS, EmuTOS recognizes hard drives attached to the system, so you don't have to install them. It will recognize ASCI (Atari's version of SCSI), SCSI and IDE drives if present and if EmuTOS supports the hardware. EmuTOS also recognizes some partitioning schemes, such as that of the IDC SCSI Host adapter.

#### Saving the Desktop

As you move in to EmuTOS, you will change how the desktop works, such as how you want to sort directories. You can preserve those choices across boots by saving the desktop. Hit ^S or go to Options -> Save Desktop. EmuDesk will ask you to confirm. Click on OK, and you are done.

#### Opening a Disk Drive or Directory

To open a window on a disk drive, double click on its icon. Or hit an Alt key and the drive letter, e.g. Alt g to open G:. To view any directory (folder), double click on its entry. Note that in text view mode, directories are identified by a small icon to the left of the name of the directory. In icon view mode, they have a manila folder icon, rather than the piece of paper icon files get.

If you save the desktop with windows open to directories, you will preserve those open windows across boots. This is handy for directories you use a lot.

Folder windows have several widgets of interest.

* Scroll bars on the right and bottom allow scrolling. Click on the scroll bar for gross movement, or on the arrows at the ends of the scroll bar for fine movement.

* The title bar, across the top, has the path to the current directory, e.g. `C:\AUTO\*.*` or `C:\*.*`. You can specify which files will show up in the window by [setting the file mask](#file-mask). The title bar shows the selected file mask.

    To move the window around on the desktop, click and drag the title bar.

* In the upper left-hand corner is the folder button. Clicking on this goes up a folder in the hierarchy. At the top folder of a partition, it will close the window. You can also go up a folder with File -> Close folder (^H). You can close a window regardless of where in the file hierarchy it is with File -> Close top window (^U).

* To toggle full screen mode, click on the upper right full screen button.

* To manually re-size, click on the lower right and drag as needed.

* To execute a program, double click on it. If it has the TTP (TOS Takes Parameters) extensions, EmuTOS will ask for parameters. Clicking on the OK button or hitting the Return or Enter key will execute the program with whatever parameters you have given it. If the program is of type PRG, EmuTOS will simply execute it.

* To display any non-program file, double click on it. You can send it to your printer. Or you can show it. EmuTOS will display it one screen at a time. Use the space bar to see the next screen. Use the Return or Enter key to advance one line. Q bails out of showing the file.

To create a new folder, File -> New Folder (^N).

#### File Selection ####

You can select one file by clicking on it. Select multiple files within the same window by selecting the first, then hold the shift key down while you click on other files (Shift Click). There is no way to select a range of files. You can narrow the visible files by [setting the file mask](#file-mask). You can select all the files in the current window with File -> Select All Items (^A). Having done that, you can then use Shift Click to deselect items.

If you then select an operation, the dialog you then select will walk through the ones you have selected. For example, select several files and directories. Then look at the information on them with ^I. The Skip button at the bottom lets you skip a file or directory, whereas the OK button accepts your changes, and the Cancel button lets you end the sequence.

#### Copying and Moving Files ####

Once you have selected one or more files, you can copy them to another window by dragging them to the new window. You can move them by holding down the control key while you drag.

#### File Information

EmuTOS, like Atari TOS, uses the FAT file system, common on MS-DOS and Windows systems of the day. Thus file attributes are a bit different from those of modern operating systems. There is only one date, the date the file was last modified. Files may be marked h, for hidden; s, for system; and r, for read-only.

There is also an archive flag. When set, this file has been changed since the last archive was made. Backup software can use this bit to archive only changed files, and then reset the flag. But neither EmuDESK nor EmuCON will allow you to edit this flag.

The File Information dialog (File -> Info/Rename, ^I) will show you its name (with the option to change it), size, date and time, and whether a file is read-write or read only.

If you are looking at a folder (directory), the dialog will show you the number of files and folders within it, as well as the time and date.

For partitions or floppy diskettes, you will see the drive identifier (e.g. A for a floppy drive), the disk label, the numbers of files and folders, and the space used by files (not directories, or metadata), and the available space (in bytes).

#### File Mask

You can set the mask for displaying files in the folder windows: File -> Set file mask... . For example, if you set the file mask to *.PRG, you will only see executable program files with the extension .PRG. (You won't see other executables such as TTP.) The traditional wild cards, * (many characters) and ? (one character), work. The title bar shows the file mask.

### Desktop Accessories

### Control Panel eXtensions

Control Panel eXtensions (CPXs) are short programs that extend the control panel. They terminate and stay resident, much like [desktop accessories](#desktop-accessories).They are available in some versions of TOS, and in EmuTOS.


## EmuCON

EmuCON2 is a basic but useful command-line interpreter, written from scratch by Roger Burrows in 2013 to replace the original EmuTOS CLI.

It requires approximately 30 kilobytes, and works with Atari TOS as well as EmuTOS. Command line re-direction works for standard out, but not for standard in or standard error. MS-DOS style wild cards also work. EmuCON is not case sensitive, but the FAT file system does not preserve case. For example:

```
C:\>echo foo > bar.txt
C:\>ls bar*.*
BAR.TXT
C:\>cat bar.txt
foo
C:\>
```
Given part of a file name or path, EmuCON will do a C Shell or DOS style tab completion. That is, enter part of a path, and hit tab. The shell will cycle through one or more possible completions. Any other character adds that character to the path. You can use this repeatedly to build up a long path fairly easily.

EmuTOS's built-in VT-52 emulator respects the RS-232 flow control characters, ^S to stop, and ^Q to resume. ^C will (usually) stop a program.

The built-in commands are:

| Command   | Usage |
|-----------|-------|
| cat/type  | Show a file. Like ``cat`` and  ``TYPE``. They simply send all of the file to the screen. See ``more`` below.|
| cd        | Change directory. If you begin with a drive letter, e.g. ``D:``, you can change to a different partition. |
| chmod     | Change the permissions on a file. These are the FAT permissions: h, for hidden; s, for system; and r, for read-only. Use MS-DOS syntax for the permissions, not Unix. |
| cls/clear | Clear the screen and home the cursor. |
| cp/copy   | Copy a file. See ``mv``/``move`` below. |
| echo      | Sends everything after it on the line to the display. |
| exit      | Leave EmuCON. |
| help      | Show a list of built in commands (this table). Given a command as an argument, show a brief summary of that command's usage. |
| ls/dir    | Show a directory listing. Given a path, display that file or directory. Unlike EmuDESK, EmuCON's ls will show hidden files. |
| mkdir/md  | Make a directory. |
| mode      | Set characteristics of the "terminal", e.g. screen resolution. |
| more      | Display a file one screen at a time. Use the space bar to see the next screen. Use the Return or Enter key to advance one line. Q or ^C bails out of showing the file. |
| mv/move   | Move a file. See also ``cp``/``copy`` above. |
| path      | Set a search path, analogous to the PATH environment string in DOS or Unix. You may specify multiple folders separated by a semicolon (;). |
| pwd       | Print the working (current) directory. |
| ren       | Rename (move within the working directory). It will not rename directories on versions of GEMDOS less than 0.15 due to a bug in those versions of GEMDOS. |
| rm/del    | Remove or delete the given file(s), but not directories. |
| rmdir/rd  | Remove or delete the given empty directories. |
| show      | Show information about the given drive. |
| version   | Show the current version of GEMDOS (not the same as the current version of EmuTOS). |
| wrap      | Turn screen wrapping on or off, or show its current state. |

The `help` command shows the (above) list of commands, or individual help for a specific command, like this:

```
C:>help show
show [<drive>]
    Show info for <drive> or current drive
```

EmuCON is not provided in 192K ROMS. However, you can add it to a disk with the ``emucon-X.Y.zip`` archive.

## Reporting Bugs

Before you report a bug, you should probably search the EmuTOS [development mailing list's archives](https://sourceforge.net/p/emutos/mailman/emutos-devel/) to see if anyone else has reported your problem or something similar, and a possible solution.

To report bugs, or for other discussion about EmuTOS, please join the EmuTOS [development mailing list](https://sourceforge.net/projects/emutos/lists/emutos-devel). There are other, deprecated, ways to file bugs, but this allows anyone to join the discussion, and will usually get a faster response.

## Glossary

* <a id="aes"></a>AES: *Application Environment Service*, the highest level graphic environment in EmuTOS.

* <a id="eprom"></a>EPROM: Erasable Programmable Read Only Memory, reprogrammable [ROM](#rom). Generally more useful in experimental situations.

* <a id="natfeats" ></a>NatFeats: Native Features support. This is a number of features that some ST emulators provide, and which EmuTOS supports. See your emulator's manual for details.

* <a id="rom" ></a>ROM: Read Only Memory, usually not reprogrammable. See also EPROM.

* <a id="vdi"></a>VDI: *Virtual Device Interface*, provides low level drawing (lines, polygons, etc.), font suport, and handles user events such as mouse clicks.

## Resources

Also see the [EmuTOS links page](https://emutos.sourceforge.io/links.html).

* The [EmuTOS web site](https://emutos.sourceforge.io/).
