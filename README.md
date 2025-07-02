# yamb

YAMB (Yet Another Meshtasic Board) is a meshtastic board centered around outdoor solar powered use. The goals of this project are:

* Learn more about PCB design and manufacturing.
* Build a Meshtastic board that has features I am always looking for in an outdoor solar node.
* Is open source and open hardware so anyone can make it, modify it, and use it.
* Get the board into hands of people near me that want to use it to help expand our local mesh network.

![YAMB PCB](https://raw.githubusercontent.com/andyshinn/yamb/master/exports/yamb-pcb.png)

## Features

* Based around the proven RAK4630 module which provides the nrf52840 and SX1262 LoRa radio.
* Solar power and battery charging using the excellent Voltaic SVR and MCSBC combination.
* Reset supervisor to ensure the board can recover from power issues like brownouts.
* Vertical USB-C connector for easy access to the USB port while inside an enclosure.
* Ports for external power switch and reset button to aide maintenance while enclosed.
* Plenty of GPIO pins and ports for extending and hacking.
* Onboard QWIIC / STEMMA QT connector for easy I2C expansion.
* BME280 temperature, humidity, and pressure sensor.

## Schematic

![YAMB Board](https://raw.githubusercontent.com/andyshinn/yamb/master/exports/yamb.svg)

## Notes

### Exporting Images

To export images from KiCad, you can use the following command in the terminal:

```bash
export KICAD9_3DMODEL_DIR=/Applications/KiCad/KiCad.app/Contents/SharedSupport/3dmodels
kicad-cli pcb export stl yamb.kicad_pcb --output exports/yamb-pcb.stl
kicad-cli pcb render --output=exports/yamb-pcb.png --rotate="310,0,45" --perspective --pan "0,2.2,0" --quality high --zoom 1.3 yamb.kicad_pcb
kicad-cli sch export svg yamb.kicad_sch -n --output exports
```
