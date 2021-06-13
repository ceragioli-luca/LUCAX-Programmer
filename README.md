# LUCAX XMEGA Programmer
An open-source AtXmega programmer using an ATMEGA32U4
Project for the University of Pisa

## Project Tree
* **avrdude-6.3**: contains the patched version of avrdude, which adds a new programmer among the ones available
* **lucax-firmware**: contains the firmware of the programmer

### Avrdude 6.3 patch
* The source files "lucax.c" and "lucax.h" contains the usb driver for the programmer

## Build
To build avrdude-6.3
```
cd avrdude-6.3
./configure.sh
make
```
To build the firmware
```
cd lucax-firmware
make all
```
and then to flash it to the ATMEGA32U4
```
avrdude -C ./avrdude.conf -c usbasp-clone -p m32u4 -U flash:w:Xluca.hex:i
```

## Usage
To use the programmer to flash an XMEGA make sure to actually invoke your newly compiled version of avrdude
```
./avrdude -C ./avrdude.conf -c lucax -p x128a3u -U flash:w:My_firmware.hex:i
```
## Acknowledgements
* __avrdude__		https://www.nongnu.org/avrdude/
* __lufa usb library__ 	http://www.fourwalledcubicle.com/LUFA.php
