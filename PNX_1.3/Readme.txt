PNX 1.3 Readme
Supplemental notes and instructions for PNX 1 release for PERQemu

12-Aug-2018 - skeezicsb - v1.0


1.0 Introduction
================

This package contains a complete PERQemu hard disk image containing PNX Rel 1,
suitable for use with PERQemu v0.4.4 or later.  Also included are images of
the original floppy media used to create it, dated 5/5/1983.

This first release of PNX is an implementation of Unix System III, implemented
on the PERQ by ICL in the UK.  It comprises the majority of the Unix Version 7
commands and utilities, along with in-kernel support for a proprietary window
manager that takes advantage of the PERQ's RasterOp facility.  The kernel is
around 80KB in size and the system runs in approximatley 120KB of core.  (Let
that sink in for a minute.)

It is unclear if this really is the 1.0 release described in the installation
instructions (file "unix.rel" from the POS/RT-11 formatted install.pfd floppy)
or a slightly later version 1.3 in a comment emitted from the installation
script as the manual pages were loaded from floppy:

    February 1983 PNX release 1.3; Additions and changes made to Unix by
    ICL have not been incorporated in the on-line manual.

The Kernel Version message that appears at bootup is 1.3, so I'm going to call
this release 1.3.


2.0 Contents
============

There are two directories here:

    Disks/      Contains "pnx1.phd", a 24MB Shugart disk image;

    Floppies/   Contains the set of ".pfd" floppy disk images used
                to create pnx1.phd.

At this time there is no additional software to bundle with the basic OS as
provided by ICL.  It is still a usable Unix environment, albeit extremely
minimal by today's standards!  Although the marketing literature suggests
that PNX supported C and FORTRAN, only the C compiler is bundled with this
release.


3.0 Booting with PERQemu
========================

This version of PNX specifically requires a PERQ-1 with the v8.71 Z80 PROMs.
Fortunately that's exactly what PERQemu currently emulates!  However, it only
supported 512KB or 1MB memory configurations, and by default we configure the
emulator with 2MB (for Accent and POS).

If you are running the PERQemu v0.4.4 binary release, launch the PERQemu-1MB
executable in the manner appropriate to your platform.  If running the
source release, take out the TWO_MEG conditional and rebuild the emulator
with the default 1MB memory board.  If you try to boot PNX with 2MB it will
fail to initialize and drop you into the kernel debugger, prompting with an
'@' in the lower left corner of the screen.

After launching PERQemu, use the "load harddisk" command to load the pnx1.phd
disk image, then start the machine with "go".  The only valid boot letter is
the default "a" boot.  Upon successful boot, the DDS will read 255 and you'll
see the software version banner and a login: prompt.


3.1 Emulator Notes
------------------

Linux users:  If the emulator croaks when PNX starts up, try "set rs232 rsx:"
before starting the PERQ.  (That should be fixed in the next release.)

Debugging notes:  PNX runs a different byte code interpreter, and not the
POS/Accent "Q-code" interpreter.  We do not have any documentation or
information about the PNX "C-machine" instruction set; while single-stepping
or tracing in the PERQemu command-lne debugger, the symbolic names of the
opcodes will be wrong.  (The numeric op and microcode disassembly are correct,
however.)  If anyone _does_ happen to have any documentation, we'd be
thrilled to get ahold of a copy...


4.0 Hints and Quirks
====================

There is quite a bit of useful information to get you started in the release
notes.  Here are a few supplemental things if you want to jump in right away:

    * PNX boots into single user mode by default.  To switch to
      multi-user, type a ^Z at the login: prompt.  You'll be
      prompted to enter the date and time.  Note that in this
      version of PNX, it's always 1983!

    * The only included login is "root", password "root".  If you
      want to create your own login, it seems you have to do it all
      manually -- editing the password file, creating a directory,
      etc.

    * To start the window manager, run "winit" at the shell.  If you
      run "winman" directly, good luck figuring out how to recover
      from that.

    * The window manager is a little weird and wonderful.  It takes
      a little bit of getting used to, and there's very little help
      available.  You just have to kinda poke around and play with
      it to get the hang of it.

    * The on-line man pages are present, but for some reason they're
      painfully slow to render.  If the display stops, hit space to
      have it continue; I think there's some kind of silent "more
      mode" that doesn't prompt you to continue.  Weird.

    * There's no "bye" command like in POS. To shut down "cleanly,"
      as root type "kill -1 1" (unix.rel incorrectly shows this as
      lowercase L, not the digit 1!) to exit the window manager and
      get back to single-user mode login prompt.  Log back in as root,
      type "sync" to flush the disk buffers, then wait a few seconds.
      It's then safe to switch to PERQemu's debugger window and halt
      the machine.  REMEMBER: if you want to save any changes you
      made, use the "save harddisk" command!


5.0 A Plea For Help
===================

There were a lot of PERQs in universities all around the UK back in the
1980s, and there _must_ be more software available beyond the base OS
release.  If there are any PERQ users in the UK who might have hardcopy or
electronic copies of any documentation, or even software for PNX, *please*
contact me.  Any assistance in rescuing those bits and docs from oblivion
would be greatly appreciated!

In particular, it would be especially helpful if a copy of the "Guide to
PNX" document referenced in the "unix.rel" file could be found and scanned
for inclusion here or in the Bitsavers archive.

Thanks for your interest in PNX and PERQemu, and please feel free to drop
me a line with feedback:  skeezics b at g mail dot com

