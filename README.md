## ![Music](/pics/facemusic.gif) Welcome to Sonic Buster 8 home page!

![New](/pics/update.gif) [Latest firmware update](#firmware-updates) (v4.01)

![Sonic Buster 8](/pics/sb8b.jpg)

Sonic Buster 8 is an 8-bit ISA sound card 

Main features

![Sonic Buster 8 scheme](/pics/sb8sch.jpg)

## Hardware configuration
To select I/O port, IRQ and DMA for Sonic Buster 8 use jumpers JP1, JP2 and JP3 respectively:

![Jumpers](/pics/sb8jumpers.jpg)\

After that you need to configure a `BLASTER` variable for your DOS environment to reflect the selected hardware settings. This is done by adding a corresponding line to `C:\AUTOEXEC.BAT`. For hardware settings on the picture above the line should look like this:
```
SET BLASTER = A220 D1 I5 T3
```
`Axxx` – I/O address (210/220/230/240)\
`Dx` – 8-bit DMA setting (1/3)\
`Ix` – IRQ number (3/5/7)\
`Tx` – Sound Blaster model, where 3 is for SB 2.0, so is for the Sonic Buster 8

![Warning](/pics/warn.gif) You need to restart your computer after setting the BLASTER variable.

## PC-Speaker input

## CD/Aux input

## Dedicated volume controls

## Line output

## Firmware updates
Sonic Buter 8 firmware is based on a reverse-engineered original SB2.0 firmware... it constantly envolves ?

![Download](/pics/download.gif) [SB8VER.ZIP](/downloads/SB8VER.ZIP) - check firmware version of your Sonic Buster 8 sound card.

![New](/pics/new.gif) ![Download](/pics/download.gif) [SB8FW401.ZIP](/downloads/SB8FW401.ZIP) - **Sonic Buster 8 firmware v4.01**.\
This update fixes DMA timing issues on some machines and is recommended for every Sonic Buster 8 user.\ Download the archive, extract files to a separate directory and run `SB8FLASH.EXE`. Follow on-screen instructions to make an update.\
![Warning](/pics/warn.gif) ***The update utility should NOT be run from Windows environment! Also make sure that no other programs are using Sonic Buster 8 hardware during the update!***

## Sonic Buster 8 in DOS

## Sonic Buster 8 in Windows 3.x

## Sonic Buster 8 in Windows 9x/ME


## Programming the Sonic Buster 8

## Additional photos

