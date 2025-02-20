## ![Music](/pics/facemusic.gif) Welcome to Sonic Buster 8 home page!

### Stock status:
![Hot](/pics/hot.gif) <b>(19-02-2025) IN STOCK !</b> \
![Mailme](/pics/mailme.gif) <b>Please PM me on VOGONS.ORG (link below) or drop an e-mail to eugenetongue@gmail.com to make an order.</b>

---

![Update](/pics/update.gif) [Latest firmware update](#firmware-updates) (v4.01)

![New](/pics/new.gif) [Sonic Buster 8 thread on VOGONS.ORG](https://www.vogons.org/viewtopic.php?t=94701&hilit=sonic+buster+bust)

---

<!-- [Configuration](#configuration) \
[PC-Speaker input](#pc-speaker-input) \
[CD/Aux audio input](#cdaux-input) \
[Volume controls](#manual-volume-controls) \
[Audio output](#audio-output) \
[Programming the Sonic Buster 8](#programming-the-sonic-buster-8) -->

![Sonic Buster 8](/pics/sb8b.jpg)

![Arrow](/pics/arrow.gif) [Click to see more photos](#photo-gallery)

---

Sonic Buster 8 is a modern ISA sound card for PC XT (8086) / AT (286, 386, 486, Pentium) or compatible computers intended for retro-gaming in DOS and early Windows. The card is very easy to setup and is fully compatible with the most supported card in DOS - a Sound Blaster 2.0.

Sonic Buster 8 is fully compatible with SB2.0 in terms of 8-bit mono PCM/ADPCM audio and FM music playback. But it goes beyond that by adding a PC-Speaker input, a stereo CD/Aux audio input and a super-quiet onbord analog mixer with individual volume controls.

The firmware is based on a reverse-engineered SB2.0 firmware and is written entirely from scratch for the AVR MCU, implementing all internal workings of the original. So, basically, Sonic Buster 8’s sample playback capabilities are the same as Sound Blaster 2.0’s, but it also extends Sound Blaster 2.0 in many ways:

- **Using OPL3 FM chip instead of OPL2 for FM music playback.** OPL3 is fully compatible with OPL2 and sounds the same, but can play more advanced music in games that support OPL3. It also has way less timing issues with games running on 486 or faster machines.

- **CD/Aux stereo input** for connecting CD-ROM audio or any other sound source like a MIDI sound module for example.

- **PC-Speaker input** for routing beeper sounds to the audio output of the card instead of an internal computer speaker. For the most ancient games.

- **Super quiet (around -98dB RMS) analog audio path**, so no more Sound Blaster background noise from the speakers.

- **Firmware is updateable from DOS.**

- **Works on systems which does not have a 14.32MHz clock on ISA bus**, which is a problem for the original Sound Blaster that requires it.

- **Doesn’t need a -5V power rail to operate**, as some PSUs does not provide it.

- **Works with 6/8/12MHz ISA bus speeds.**

- **An ability to disable Adlib functionality for port 388H** by removing JP4.

## Configuration
**System requirements:** \
IBM PC XT / AT 286, 386, 486 or Pentium with one free 8/16-bit ISA slot ![Computer](/pics/computer.gif) 

![Sonic Buster 8 scheme](/pics/sb8sch.jpg)

Hardware configuration is made by selecting I/O port, IRQ and DMA with JP1, JP2 and JP3 jumpers respectively. Make sure the computer is switched off before adjusting the settings.

The most common configuration is 220H for I/O port, 5 for IRQ and 1 for DMA:

![Jumpers](/pics/sb8jumpers.jpg)

To tell DOS software which settings are selected, it is necessary to set a `BLASTER` environment variable with corresponding parameters. This is done by adding a string to `C:\AUTOEXEC.BAT`. For the hardware settings on the picture above the string is:
```
SET BLASTER = A220 I5 D1 T3
```
Where: \
`Axxx` – I/O address (210/220/230/240)\
`Dx` – 8-bit DMA setting (1/3)\
`Ix` – IRQ number (3/5/7)\
`Tx` – Sound Blaster model, where 3 is for SB 2.0, so is for the Sonic Buster 8

> ![Warning](/pics/warn.gif) *The parameters will take effect only after system reboot.*

---

To use Sonic Buster 8 in games just setup it as a Sound Blaster 2.0 or let the game to autodetect it:

![Detect](/pics/crt1.jpg)

Although `Music Card:` is automatically set to `Sound Blaster FM (OPL2)`, for advanced music playback it can be manually changed to OPL3 if the game supports it:

![OPL3](/pics/crt2.jpg)

![Set](/pics/crt3.jpg)

---

Windows 9x/ME detects Sonic Buster 8 as a `Sound Blaster or compatible` during OS installation or by running Control Panel -> Add New Hardware wizard:

![Win98](/pics/win98.jpg)

## ![Speaker](/pics/speaker1.gif) PC-Speaker input 
![PC-Speaker input](/pics/pcspk.jpg)

This is made for very old games that lack any sound support except the PC-Speaker.

To make PC-Speaker audible on the output of Sonic Buster 8 connect...

A 2-pin connector is used for connecting PC-Speaker header of a motherboard to the Sonic Buster 8. It is usually marked as SPK or SPEAKER and have 4 pins, but only the two on the ends matter. One of them is usually named VCC or SPEAK+ or just +, while the other one can be something like SPEAK- or not marked at all. Use the included 2-pin cable to connect the first one to + pin on the card and the other one to S pin.

If there is no speaker signal present, please check its gain setting on the back panel of the card or try swapping the connected pins.

> ![Warning](/pics/warn.gif) *This input accepts only PC-Speaker signal and is not intended for other audio sources.*

## ![CD](/pics/cdspin.gif) CD/Aux input 
![CD/AUX](/pics/cdaux.jpg)

Audio input accepts any stereo line-level signal. Left, ground and right pins are marked as L G R. Use the included 3-pin cable to connect analog audio output of a CD-ROM to the card. CD/Aux input can also be used for any other audio source, for example a MIDI sound module or an output of another sound card in the system. Its gain can be adjusted with a corresponding volume pot on the back panel of the card.

## Manual volume controls
There are four volume pots on the back panel of the card for adjusting volume levels of PCM/ADPCM audio, FM music, PC-Speaker and CD/Aux:

![Volume controls](/pics/controls.jpg)

When the card's output is connected to an amplifier or active speakers it is recommended to set OPL3 level to maximum (clockwise) and adjust other levels accordingly to your liking, as OPL3 has the most dynamic range and can seem to be the quietest of them all.

## Audio output
Audio output accepts standard stereo mini-jack connection and can be fed to an amplified sound system or directly to headphones.

> ![Caution](/pics/warn.gif) *CAUTION: Using headphones with excessive volume levels can damage your ears!*

## Firmware updates
**Latest firmware version is 4.01**

Download ![Download](/pics/download.gif) [SB8VER.ZIP](/downloads/SB8VER.ZIP) utility to check if your Sonic Buster 8 firmware is up to date.

> ![Warning](/pics/warn.gif) *The update utility should NOT be run from Windows multi-tasking environment! Also make sure that no other programs are using Sonic Buster 8 hardware during the update when running it from DOS!*

![New](/pics/new.gif) ![Download](/pics/download.gif) [SB8FW401.ZIP](/downloads/SB8FW401.ZIP) - **Sonic Buster 8 firmware v4.01**.\
This update fixes DMA timing issues on some machines and is recommended for all Sonic Buster 8 users.\
Download the archive, extract to a separate directory and run `SB8FLASH.EXE`. Follow on-screen instructions to make an update.

## Photo gallery
![1](/pics/gall/1.jpg)
![2](/pics/gall/2.jpg)
![3](/pics/gall/3.jpg)
![4](/pics/gall/4.jpg)
![5](/pics/gall/5.jpg)
![6](/pics/gall/6.jpg)
![7](/pics/gall/7.jpg)
![8](/pics/gall/8.jpg)

Prototypes:


<!-- ![Up](/pics/finger_up.gif) [Back to top](#music-welcome-to-sonic-buster-8-home-page) -->


