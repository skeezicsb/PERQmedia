
## PERQ Speech Demo

_PERQemu_ v0.9.5 enables audio output by default in all configurations.  This
set of floppies provides some samples and a program to play them!  Tested on
POS G.6, but should be portable to most POS versions with little effort.

The floppies here are presented in `.prqm` and `.imd` formats.  _PERQemu_ can use
either; `.imd` can be converted using ImageDisk tools for use with a Gotek floppy
emulator or written to 8" floppies for use with your PERQ.


### Installation

You'll need at least 3800 free blocks to install everything, or around 1500 if
you just want to install the first floppy.  To load:

- Start up your PERQ, or _PERQemu_ v0.9.x (or later) and load floppy `talker01`.

- Type: `floppy get setup.cmd` to load the install script.  Modify to taste.

- Type: `@setup` and follow the prompts.

Enjoy!


### History

These audio samples were recorded at Three Rivers to exercise the PERQ's "speech"
output.  The MC3417 CVSD chip provides "telephone quality" audio, and the original
intent (in line with the SPICE Project goals) was to allow research into voice and
speech synthesis -- the low bit rate optimized for storage size over audio fidelity.
No circuit diagram or explanation of how these were captured survives, but someone
managed to do some 32kHz recordings of Christmas music in addition to the short
16kHz samples.  (An early SIGGRAPH booth demo also featured audio and music playback,
and that will be posted here someday too once all the files are found.)

