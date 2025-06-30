# Tag Reader for Home Assistant
This is based on the nfc tag [Tagreader](https://github.com/adonno/tagreader)project by adonno.

More Documentation can be found there as well.

My version focuses on the usage of this device as a alarm controller for a storefront. It sits behind a large window and does only the following:
- Arm/Disarm alarm in Homeassistant (Using Alarmo) using NFC keychain tags
- show the current alarm state using the LED
- write NDEF data on new NFC tags

## What I changed:
YAML:
- added second LED for showing alarm state
- added a few light effects for showing states
- added a sensor to fetch current alarm state in Homeassistant
- removed all music related stuff
- removed all buzzer signals

Case:
- made it bigger to have more space for labels/logos
- added a second LED
- added heat set inserts
- added transparent LED channels

## Components
To build your own tag reader, you need the following components:

 - ESP8266 D1 Mini v4.0
 - PN532 NFC Reader v4 (v4 has extended reach, otherwise won't work behind thick windows)
 - 2x WS2812 SMD 5050 Leds

### Connecting the components

![Photo of schematics](Schematics/tag_reader_schematics_v4-nobuzzer.png)

Switches on PN532 need to be set to I2C mode:
- Switch 1: On (up)
- Switch 2: Off (down)

To flash the reader firmware to your D1 Mini you point ESPHome at [tagreader.yaml](tagreader.yaml).  
> :warning: The tag reader requires ESPHome `1.16.0`.

## Case
made some changes to the original case design. Mainly did that to house the second LED and have some more space at the front for labels and logos.
![Open Case](docs/inside-case.jpg)

Step File from Fusion are [here](CAD Files)