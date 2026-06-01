
## Upgrading POS F.15 to Amendment 3

This floppy contains several command files to update your existing POS F.15
system from Amendment 1 to Amendment 3.  For PERQemu users, the bundled hard
disk images have already been updated in the v0.9.5 release.  The complete
Amendment 3 media set, with hard disk, floppy and a new cartridge tape image
is here if you want to selectively add or upgrade individual file sets, or
do your own upgrade or "bare metal" installations.  Hey, I don't judge.


### Changes

Amendment 1 fixed a number of bugs and replaced the original "FCS" installation
in the PERQemu distribution set.  If you are still running the initial release,
it is recommended that you upgrade-in-place to Amendment 3 using the new media.

Amendment 2 was a supplemental release of the Canon laser printing software and
the streaming tape utility on separate floppies.  The Amendment 3 upgrade allows
you to skip those if they are already installed.

Amendment 3 contains two small bug fixes to FTP and Kermit, as well as a few
incidental source code cleanups that correct improper line endings but otherwise
do not impact functionality.  It also provides a new set of command files to
create boot and installation floppies with support for tape as the source media,
eliminating a lot of manual floppy loading and unloading!  All of these new
features are being rolled into POS F.16, the next release (coming Real Soon Now).


### Installation Instructions

To install the binary upgrade (all systems), download the following images from
the Floppies directory:

    680020-00-1     F.15 Amendment 3 floppy
    685040-02-1     CONTRIB.COMMS.KERMIT.BINARY
    680132-00-1     OS.UTILS.STUT.BINARY
    680135-00-1     OS.UTILS.CANON.BINARY

For PERQemu, you can use either format; for updating your PERQ's hard disk
using a Gotek or other floppy emulator, the .IMD format can be readily
converted for use with the hardware.

For full source/developer systems, also download:

    685045-02-1     CONTRIB.COMMS.KERMIT.SOURCE
    680600-02-1     OS.SYSTEM.MISC
    680332-00-1     OS.UTILS.STUT.SOURCE 
    680335-00-1     OS.UTILS.CANON.SOURCE


Boot your POS F.15 system and log in.  Load the POS F.15 Amendment 3 floppy
(680020-00-1), then type:

```
    > **floppy get am3bin.cmd**
    > **@am3bin**
```

    This will copy the modified binaries for Amendment 3, then prompt you to
    load the other binary floppies.  The Canon and Stut packages may be
    skipped if they are already installed.  The updated executables will then
    be linked.


To install the source packages (for dev systems), load the Amendment 3 floppy
again and type:

```
    > **floppy get am3src.cmd**
    > **@am3src**
```

    This will then prompt you to insert the additional floppies needed to
    bring your :dev>src> and :extra>contrib> trees up-to-date.  The script
    will not recompile anything; the binaries installed above are current.

When your upgrade is complete, there is no need to reboot; you may delete
the upgrade scripts `am3bin.cmd` and `am3src.cmd`.  For PERQemu users, be
sure to save the hard disk to preserve your changes.

