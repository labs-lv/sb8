<a name="top"></a>
## ![Music](/pics/facemusic.gif) Welcome to Sonic Buster 8 home page!

### Stock status:
![Hot](/pics/hot.gif) <b>(19-02-2025) IN STOCK !</b> \
![Mailme](/pics/mailme.gif) <b>Please PM me on VOGONS.ORG (link below) or drop an e-mail to eugenetongue@gmail.com to make an order.</b>

---

![Update](/pics/update.gif) [Latest firmware version](#firmware-updates) *is 4.01*

![New](/pics/new.gif) [Sonic Buster 8 thread on VOGONS.ORG](https://www.vogons.org/viewtopic.php?t=94701&hilit=sonic+buster+bust)

---

![Arrow](/pics/arrow_sm5.gif) [Overview](#overview) \
![Arrow](/pics/arrow_sm5.gif) [Features](#features) \
![Arrow](/pics/arrow_sm5.gif) [Configuration](#configuration) \
![Arrow](/pics/arrow_sm5.gif) [PC-Speaker input](#-pc-speaker-input) \
![Arrow](/pics/arrow_sm5.gif) [CD/Aux audio input](#-cdaux-input) \
![Arrow](/pics/arrow_sm5.gif) [Volume controls](#manual-volume-controls) \
![Arrow](/pics/arrow_sm5.gif) [Audio output](#audio-output) \
![Arrow](/pics/arrow_sm5.gif) [Firmware updates](#firmware-updates) \
![Arrow](/pics/arrow_sm5.gif) [New DSP functions](#new-dsp-functions) \
![Arrow](/pics/arrow_sm5.gif) [Photo gallery](#photo-gallery)

![Sonic Buster 8](/pics/sb8b.jpg)

![Arrow](/pics/arrow_r.gif)[Click to see more photos](#photo-gallery) ![Arrow](/pics/arrow1leftgreen.gif)

---
<a name="overview"></a>
Sonic Buster 8 is a modern ISA sound card for PC XT (8086) / AT (286, 386, 486, Pentium) or compatible computers intended for retro-gaming in DOS and early Windows environments. The card is simple to use and is fully compatible with the most supported card in DOS - Sound Blaster 2.0. Its firmware is based on a reverse-engineered SB2.0 firmware and is written entirely from scratch for the AVR MCU, implementing all internal workings of the original card. But being fully playback-compatible with Sound Blaster 2.0, Sonic Buster 8 also surpasses it in many ways.

Sonic Buster 8 intergrates a high quality ultra-quiet analog path, which drastically reduces background noise (which Sound Blaster is famous for) to a level of non-existing. It also uses 2-stage active filtering for minimizing aliasing effects of a 8-bit sound while trying to keep the high frequences in place. All this results in a much cleaner and pronounced sound.

For games with CD music Sonic Blaster 8 has an internal stereo CD/Aux input with a dedicated volume control on the back panel. It can also be used for connecting any line-level sound source to the Sonic Buster 8's mixer, like a MIDI sound module or an output from another sound card for example.

For very old games which do not support digital audio or FM music, Sonic Buster 8 has a PC-Speaker input with a dedicated volume pot and an active filter in the audio path, which tries very hard in making the beeper to sound a bit more pleasant. 

Unlike any Sound Blaster, Sonic Buster 8 has an analog audio mixer with four dedicated volume control pots for all its sound sources - PCM/ADPCM audio, FM music, CD/Aux and PC-Speaker.  

And finally it uses a better version of OPL2 chip - an OPL3 for FM music playback.

<a name="features"></a>
Here is a list of features:

- **Fully compatible with Sound Blaster 2.0 8-bit mono PCM and ADPCM digital audio playback.** PCM playback rate up to 62500Hz. Has new SB8-specific DSP functions for future retro software.

- **Using OPL3 FM chip instead of OPL2 for FM music playback.** OPL3 is fully compatible with OPL2 and sounds the same, but can play more advanced music in games that support OPL3 and also has way less timing issues with games running on 486 or faster machines.

- **CD/Aux stereo input** for connecting CD-ROM audio or any other sound source like a MIDI sound module for example.

- **PC-Speaker input** for routing beeper sounds to the audio output of the card instead of an internal computer speaker. For the most ancient games.

- **Super quiet (around -100dB RMS) analog audio path**, so no more Sound Blaster background noise from the speakers.

- **Firmware is upgradable from DOS.**

- **Works on systems which does not have a 14.32MHz clock on ISA bus**, which was a problem for the original Sound Blaster that required it.

- **Doesn’t need a -5V power rail to operate**, as some PSUs do not provide it. -5V rail was a requirement for the original Sound Blaster.

- **Works with 6/8/12MHz ISA bus speeds.**

- **An ability to disable Adlib functionality for port 388H** by removing JP4.

## Configuration
### System requirements ![Computer](/pics/computer.gif)
IBM PC XT / AT 286, 386, 486 or Pentium with one free 8/16-bit ISA slot 

![Sonic Buster 8 scheme](/pics/sb8sch.jpg)

### Hardware settings

Hardware configuration is made by selecting I/O port, IRQ and DMA with JP1, JP2 and JP3 jumpers respectively. Make sure the computer is switched off before adjusting the settings.

The most common configuration is 220H for I/O port, 5 for IRQ and 1 for DMA:

![Jumpers](/pics/sb8jumpers.jpg)

### Sonic Buster 8 and DOS

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

### "Adlib enable" jumper (JP4)
When JP4 is opened (removed), Sonic Buster 8's OPL3 chip will not react to Adlib port (388h) commands at all, but will keep listening to 2x0h/2x1h and 2x8h/2x9h ports. This feature was requested by several users who have an Adlib card installed on the same system and want it to play FM music when "Adlib" is selected in game setup as a music device. \

Normally this jumper should remain closed.

---

### Games setup

To use Sonic Buster 8 in games just setup it as a Sound Blaster (version 2.0 or lower).\
Or let the game to autodetect it:

![Detect](/pics/crt1.jpg)

Although `Music Card:` is automatically set to `Sound Blaster FM (OPL2)`, for advanced music it can be manually changed to OPL3 if the game supports it:

![OPL3](/pics/crt2.jpg)

![Set](/pics/crt3.jpg)

---

### Sonic Buster 8 and Windows 9x/ME

Windows 9x/ME detects Sonic Buster 8 as a `Sound Blaster or compatible` during OS installation or by running Control Panel -> Add New Hardware wizard:

![Win98](/pics/win98.jpg)

## ![Speaker](/pics/speaker1.gif) PC-Speaker input 
![PC-Speaker input](/pics/pcspk.jpg)

This one is made for very old games that does not support any sound device except the PC-Speaker. It has an active filter in its audio path to round up the beeper waveform a bit and make it a little more pleasant to the ears.

A signal from a motherboard header should be connected to this input. A 4-pin header is usually marked as SPK or SPEAKER, but only the two on the ends matter. One of them is usually named VCC or SPEAK+ or just +, while the other one can be something like SPEAK- or not marked at all. Use the included 2-pin cable to connect the first one to + pin on the card and the other one to S pin.

If there is no speaker signal present at the output when it should, please check its gain setting on the back panel of the card or try swapping the connected pins.

> ![Warning](/pics/warn.gif) *This input accepts only PC-Speaker signal and is not intended for other audio sources.*

## ![CD](/pics/cdspin.gif) CD/Aux input 
![CD/AUX](/pics/cdaux.jpg)

This input accepts a line-level stereo signal. Left, ground and right pins are marked as L G R. Use the included 3-pin cable to connect analog audio output of a CD-ROM to this input. It can also be used for any other audio source, for example a MIDI sound module or an output of another sound card in the system. The gain can be adjusted with a corresponding volume pot on the back panel of the card.

## Manual volume controls
There are four volume pots on the back panel of the card for adjusting volume levels of PCM/ADPCM audio, FM music, PC-Speaker and CD/Aux:

![Volume controls](/pics/controls.jpg)

When the card's output is connected to an amplifier or active speakers it is recommended to set OPL3 level to maximum (clockwise) and adjust other levels accordingly to your liking, as OPL3 has the widest dynamic range and can seem to be the quietest of them all.

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

## New DSP functions
For those who is developing new software for DOS and want to support Sonic Buster 8 features (like OPL3 FM chip for example) here is a description of new DSP functions that Sonic Buster 8 adds to the Sound Blaster command set.

### Detecting Sonic Buster 8
Command **E5h** is used to read Sonic Buster 8 firmware version. 

**Output:** E5h

**Remarks:** After sending this command, read back two bytes from the DSP. The first byte is the major version number and the second byte is the minor version number. For Sonic Buster 8 the major version number is always 4, while minor version is variable. 

If reading bytes from the DSP was successfull it means that Sonic Buster 8 is present in the system and its features like an OPL3 FM chip and other specific DSP functions can be utilized by the program.

If reading bytes from the DSP has failed (timed out) it means that Sonic Buster 8 card is not present in the system.

### Setting accurate time constant
Sonic Buster 8 DSP adds two new commands for setting Time Constant more precisely that doing it a regular way using command 40h.

The process is simple:
1) Read a value from the DSP with command 50h
2) Make calculations
3) Write the result to the DSP with command 51h

---

#### 50h - Read DSP clock constant
**Output:** 50h

**Remarks:** After sending this command, read four bytes back from the DSP. These four bytes form a 32-bit value representing the DSP clock speed. The first byte read contains bits 31-24 of the value, the second - bits 23-16, the third - bits 15-8 and finally the last byte contains 7-0 bits of the value. 

This 32-bit value is always constant for the exact Sonic Buster 8 card and thus should be read only once during the init. However, it can differ between card models and revisions.

After reading the clock speed, a time constant should be now calculated as follows:

```
time_constant = dsp_clock_speed / playback_rate
```

The result should be rounded to the closest 2-byte integer value and sent back to the DSP using command 51h.

Example:
```
If we need to set playback rate to 44100 Hz
and command 50h returned 14318181

time_constant = 14318181 / 44100

The result is 324.675, which rounds up to 325

A real playback rate of the DSP will be 14318181 / 325 = 44055 Hz
```
As a result, 44055 Hz is way more accurate than 45454 Hz, which is a reality when setting Time Constant the Sound Blaster way using command 40h.

---

#### 51h - Write time constant
**Output:** 51h, time_constant.HighByte, time_constant.LowByte

**Remarks:** After calculating the Time Constant using the clock value returned by command 50h, send the two-byte result back to the DSP.

The proper sequence is:

1) Send command 51h
2) Send time_constant.HighByte
3) Send time_constant.LowByte

After this command a DSP playback operation can be started.

---

## Photo gallery
![1](/pics/gall/1.jpg)

![2](/pics/gall/2.jpg)

![3](/pics/gall/3.jpg)

![4](/pics/gall/4.jpg)

![5](/pics/gall/5.jpg)

![6](/pics/gall/6.jpg)

![7](/pics/gall/7.jpg)

![8](/pics/gall/8.jpg)

---

**Prototype #2:**

![Proto](/pics/proto/p2-1.jpg)

---

**Prototype #1:**

![Proto](/pics/proto/p3.jpg)

![Proto](/pics/proto/p2.jpg)

![Proto](/pics/proto/p1.jpg)

![Up](/pics/finger_up.gif) [Back to top](#top)


