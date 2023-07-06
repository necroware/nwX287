# Necroware's nwX287 RTC module

![photo](./images/top.jpg)

This is a drop-in replacement for RTC modules with solid body. Such modules were
widely used on 486 and Pentium mainboards back in the days. After so many years
the battery inside of such modules got empty and there is no way to exchange it.
With empty battery BIOS settings can not be saved and so many mainboards can't
even boot properly. This alternative solution has a socket for CR1225 and the
battery can be easily replaced again, when it gets empty. This module can be
used with BQ3285, BQ4285 or pin compatible RTC chips, dependent on the
requirements. This module was tested only with the named ICs, but it should be
also compatible with DS1385, which has additional 2KB of NVRAM and was used on
many microchannel and EISA mainboards.

This part should be compatible with following RTC modules:

* Dallas DS1287 / DS12887 / DS12B887 (using BQ3285)
* Dallas DS1387 (using DS1385, untested so far)
* Dallas DS14287 (using BQ4285)
* Benchmarq BQ3287 (using BQ3285)
* Benchmarq BQ4287 (using BQ4285)
* ODIN OEC12C887 (using BQ3285)

Video: https://www.youtube.com/watch?v=svPNxILeQEw

## Remarks to the used RTC chips

Pay attention, which RTC IC you need. Most of the mainboards with an RTC module
need BQ3285, but some EISA mainboards require BQ4285 with chip enable signaling
on pins 21/22 to control external memory. The Benchmarq ICs are easier to find
today, that's why they are proposed, but there are some compatible ICs existing
which can be used instead as well:

* Benchmarq BQ3285 = Dallas DS12885
* Benchmarq BQ4285 = Dallas DS14285

### Motorola and Intel Bus Modes

This module can also be used as a replacement for the Motorola MC146818 RTC chip
and compatibles. The MC146818 was used as the RTC and CMOS storage element in
the IBM PC AT and has been extensively cloned, or many compatible chips made as
alternatives (e.g. the ubiquitous Dallas 128x RTC modules found on many PC
mainboards).

Depending on your exact system requirements, the function of pin 1 may be
configured through the use of two solder bridges per the following table:

| JP1 | JP2 | RTC pin 1 is ... |
|-|-|-|
| 1-2 | Don't care | connected directly to socket pin 1 (default) |
| 2-3 | 2-3 | pulled DOWN to ground for Intel bus mode |
| 2-3 | 1-2 | pulled UP to VCC for Motorola bus mode |

Note: JP1 pins 1-2 are bridged from the factory to maintain compatability with
any external functionality or signalling, so a small cut must be made between
these two pads to unbridge them if you intend to pull up or down via JP2.
*__!!! Test for continuity between adjacent pads to ensure all cuts are clean
and that solder bridges do not make unintentional connections before installing
the module in your computer or device !!!__*

Adrian Black of Adrians Digital Basement tested the Motorola bus mode (using a
bodge wire) as a replacement for a Hitachi HD146818 for use in a BBC Master in a
video on his channel: https://youtu.be/2Sgleturods?t=2970

## Cutting the module pins

*Important:* some mainboards seem to use /RCL pin 21, so cut it first if you are
sure, that your mainboard doesn't use it.

Dependent on which RTC chip you are using you have to cut off some pins on the
module. If you are using BQ3285, you need to remove pins 2,3,16,20,21,22. When
using BQ4285 you need to remove pins 2,3,16,20.

![photo](./images/pinout.jpg)
![photo](./images/bottom.jpg)

## Bill of Materials

Part | # | Description
-----|---|-----------------------------------------
U1   | 1 | Real-Time Clock BQ3285S or BQ4285S SO-24
Y1   | 1 | Crystal oscillator 32.768kHz 6pF
BT1  | 1 | CR1220 / CR1225 SMD battery holder








