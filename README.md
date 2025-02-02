# CAS Tools 1.3

## Copyright 2001-2007 Vincent van Dam
### vincentd@erg.verweg.com


This is an OS/2 fork of cas_tools, a set of utilities for MSX emulators.
I ported this on OS/2 as part of my personal project to have as many retro
computer and game consoles emulator as possible available on this old but
still good platform.

The original GitHub repository is [here](https://github.com/joyrex2001/castools).

I just modified the original makefile in order to compile it, since I was 
dealing with command line programs and these are fairly easy to compile.


### The original README.txt follows

This is a set of tools which can read sampled MSX tapes and convert them to
the standard .cas format and back to .wav samples. This package consist of
three tools: wav2cas, cas2wav and casdir.

The most important tool is wav2cas, this tool does the actual conversion of
audio samples to the .cas format. The cas2wav is the reverse process and
converts .cas files back to audio samples, which can be read on a real MSX.
The casdir tool gives a detailed list of the contents of the .cas file. The
last two tools are pretty straight forward and will not be described any
further in this document.

The wav2cas tool requires a .wav file as input. It will analyse the signal and
create a .cas file. It will work on 'copy-protected' tapes which use their own
custom loader using the bios routines for the actual retrieval of data.
Unfortunately tapes exist which don't use the bios routines (e.g. a lot of 
Gremlin games used a entirely different format). These will not work. 
Fortunately, a lot of publishers did use the bios calls, and they should work
fine. 

However, keep in mind that the tape medium was not the most reliable medium to
store data on; remember cleaning your heads, tuning your heads and playing with
the phase and volume settings on your datarecorder? This tool can have good
results, but if the signal is too much deteriorated it will probably fail.

You get the best results by sampling the tapes at the highest sample frequency
as possible. It does not matter if the sample is 16 or 8 bits; if it is 16 bits
it will be converted to 8 bits. Sample the signal as loud as possible, but make
sure the signal does not clip!. 

The wav2cas tool has 4 arguments to play with, but the default settings should
work fine if it is a clean clear signal.  The -t argument requires an integer
which defines a threshold; if the signal is noisy you could try a higher value
to get better results. The -e argument also requires an integer and defines the
amount of 'envelope' correction, you could try increasing and decreasing this
to get better results. The -n argument will maximize the signal and the final
-p argument will phase shift the signal.

This should be enough info to get you started in converting your old cassette
tapes to .cas files. Good luck!


## Version History

### 2007/12/08 1.3

* cas2wav: allow custom gaptime between blocks.

### 2007/05/04 1.2

* cas2wav: added multi cpu support
* wav2cas: added multi cpu support
* casdir: compile warnings fixed
Credits go to Ramones for the applied changes, thanks!

### 2002/06/09 1.1

* cas2wav: increased gap between data and headers
* wav2cas: fixed bug in wav reading
* wav2cas: changed default phase 

### 2001/12/03 1.0

* first public release
