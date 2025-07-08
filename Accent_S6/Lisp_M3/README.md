## Lisp M3

This collection includes PERQ Lisp release M3 for Accent S6.  This early implementation of Common Lisp is now available for [PERQemu](https://github.com/skeezicsb/PERQemu) v0.7.5 or newer.  (For 24-bit mode, v0.7.8 is required.)

### What's here

| Media files |    |
| :---------- | -- |
| `s6mfm.prqm` | _PERQemu_ hard disk image for the PERQ-2/T2 or T4 |
| `s6.img.gz`, `s6.img.metadata.gz` | Raw data for import into the MFM emulator
| **Configuration files** | |
| `t2s6lisp.cfg` | Configures a PERQ-2/T2 for use with Accent (`a` boot) or POS G.6 (`b` boot) |
| `t4s6lisp.cfg` | Pre-configured PERQ-2/T4 (aka PERQ4) 24-bit configuration; use with `z` boot to boot into 24-bit mode |

Consult the file `/sys/lisp/core/Util/release.notes` for more information about the Lisp M3 release.

### What's not

This image was pulled together from a number of different sources and is _not_ the full distribution set provided by Expert Technologies, Inc.  (ETI was a spin-off of CMU and/or PERQ Systems Corp.?)  This installation includes their CORE: and MORE: pacakges, but KCORE:, SFASL: and SOURCE: are not included.  It is hoped that these additional files will be recovered to allow building the complete distribution from source, if only to preserve the software (or port it to Accent S7!).

Note that while this disk image has received a fair bit of testing, there may be some programs that fail or misbehave; improvements to the emulator and/or this disk image will be posted as time and resources allow.

### Notes

- The hard disk is a Maxtor XT-1105, with a much larger paging partition and plenty of extra space for doing Lisp development or loading additional demos and sample code.  The original PERQ-1 Shugart drive (`s6lisp.cfg` bundled with _PERQemu_) was severely limited.

- The `.img` files can be imported using `mfm_util` and used with David Gesswein's [MFM emulator](https://www.pdp8online.com/mfm/) attached to a real PERQ-2/T2 or T4.  _For import:_ `Cyl 918, Heads 11, Sect 16, no write precomp.`

- At this time, floppy or QIC tape images to recreate the hard disk from scratch are not available.  In time, the complete distribution sets for building new Accent S6, POS G.6 and Lisp M3 installations will hopefully be added to this archive.  As always, the _excellent_ [Bitsavers archive](https://bitsavers.org/bits/PERQ) is a good place to unearth treasures.

- Both configurations specify the landscape monitor; some applications (FontEd) may require you reconfigure and reboot with the portrait instead.  You can add the OIO board for Canon laser printing and QIC streaming tape if desired.  See the _PERQemu_ User Guide for details about customizing configurations.
