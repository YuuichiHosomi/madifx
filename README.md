Linux ALSA driver for RME MADI FX (WIP)
=======================================
This repository contains a Linux kernel driver for RME MADI FX cards. It
is still work in progress. Once finished, it'll be submitted to the
mainline kernel.


Disclaimer
----------
This driver has been developed via ssh on a remote machine with a single
static MADI crossover connection to a PCI RME MADI card, so not all
ports have been tested. Most importantly, the channel mappings might be
wrong.

Like always, no guarantees at all, use at your own risk. Feel free to
report problems and patches to improve the driver.


Installation
------------
Clone this repository, then run

    make install

as root. Use `alsamixer` or `amixer` to adjust settings.


Status
------
 * PCM playback/capture working (SS and DS tested, QS untested)
 * MIDI probably working (untested)
 * All card settings working (e.g. TX64, SMUX, AESpro, WC-Term,
   WC-singlespeed...)
 * Mirror-MADI1-to-Out2+3 maybe working (untested)
 * Redundancy mode maybe working (untested)
 * ioctls implemented (see ioctl.c)
 * Static mixer working (fixed 1:1 mapping)
 * DSP **NOT** working. RME doesn't intend to release any information
   regarding the DSP.
 * Adjustable mixer **NOT** working (needs new userspace tools)
 * Levelmetering **NOT** working (maybe wrong, needs new userspace
   tools)


TODO
----
 * Cleanup code (still contains plenty of the HDSPM driver)
 * Implement new userspace tools (see above)
 * Submit to mainline

Acknowledgement
---------------
Thanks to [IOSONO](http://www.iosono-sound.com/) for hosting the card
and providing the remote login. Kudos to Andre Schramm for taking care
of the setup.

Thanks to [RME](http://www.rme-audio.com) for temporarily providing the
card. Special thanks to Martin Björnsen for the OSX driver source.

Contact
-------
In case of trouble or questions, send me an email:

   [Adrian Knoth](mailto:adi@drcomp.erfurt.thur.de)