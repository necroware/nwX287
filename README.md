# Necroware's NW12887 RTC module

![photo](./photo.jpg)

This is a drop-in replacement for RTC modules with solid body. Such modules were
widely used on 486 and Pentium mainboards back in the days. After so many years
the battery inside of such modules got empty and there is no way to exchange it.
With empty battery BIOS settings can not be saved and so many mainboards can't
even boot properly. This alternative solution has a socket for CR1225 and the
battery can be easily replaced again, when it gets empty.

This part should be compatible with following RTC modules:

* Dallas DS1287 / DS12887 / DS12B887 (using BQ3285)
* Benchmarq BQ3287 (using BQ3285)
* ODIN OEC12C887 (using BQ3285)
* Benchmarq BQ4287 (using BQ4285)


## Bill of Materials

Part | # | Description
-----|---|-----------------------------------------
U1   | 1 | Real-Time Clock BQ4285S (or BQ3285S) SO-24
Y1   | 1 | Crystal oscillator 32kHz 6pF
BT1  | 1 | CR1220 / CR1225 SMD battery holder


## Remarks to the used RTC chips

Pay attention, which RTC IC you need. Most of the mainboards need BQ3285, but
EISA mainboards require BQ4285 with chip enable signaling on pins 21/22 to 
control external RAM IC. Since BQ4285 should be else compatible to BQ3285,
it is probably sufficient just to always use BQ4285 and snap off the related
pins 21/22 if only BQ3285 functionality is needed.




