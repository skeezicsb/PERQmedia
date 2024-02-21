
## POS F.15 Amendment 2

This supplemental release for POS F.15 includes software to drive the Canon
laser printers.  This standalone package works with PERQemu v0.5.5 or later
to produce LBP-10 (240dpi) or LBP-CX (300dpi) output in the form of PNG or
TIFF images.  It _should_ also work on the actual hardware, if you happen
to own both a PERQ-1 with old Z80 ROMs _and_ a Canon laser printer with the
"video interface" whose insides haven't turned into goo.

The F.15 hard disk images bundled with _PERQemu_ v0.5.5 have been updated to
include the Canon software.  The floppy images here are in the compressed
".prqm" format.  Amendment 3 is expected to be a full (and likely final)
rebuild with some additional features and a new full media set.

## Late breaking news!

Two more floppies are here that have not yet been integrated into the full
distribution:  the STUT utility binary (680132-00) and source (680332-00)
now let POS F.15 access the tape streamer.  This means that a tape install
option will soon be available for POS F.15, dramatically reducing the floppy
swapping madness and greatly simplifying the installation of POS.

Note that some of the POS G and Accent images come with STUT already loaded;
this is a backport to the unique POS F.15 branch.  The _PERQemu_ documentation
and F.15 Release Notes have not yet been updated to reflect this new addition.  The floppies are presented here for early access while development and testing
continue.  Feedback is welcom.  Enjoy!

