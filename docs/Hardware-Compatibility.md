# Hardware Compatibility

### General Remark
Although a board looks similar, it can have major differences, e.g.:

- Processor
- Ram (Size! & Type) -> this Project needs at least 4MB RAM!
- Flashrom
- Camera Modules
- Onboard/External Antenna
- Quality of Components
- Manufacture Quality of the PCB and soldering
- Different Components
- "Clone" Components -> ESPxx
- etc.

This can cause different Power Consumption, Power Requirements, compatibility issues, etc.

Most manufacturers and sellers buy what's cheap today on the Asian markets. In the end, it looks like it is sometimes a trial and error approach which ESP32-CAM Module works reliably.

Below you find some remarks and experiences from the community:

# ESP32 core itself

| Chip Version              | Image | Status   |
| ------------------------- | ----- | -------- |
| ESP32-D0WDQ6 (revision 1) |       | :heavy_check_mark: |

# PSRAM

There seems to be a lot of "fake" chips, or maybe wrongly configured ESP32 Boards.


For AP MEMORY, all "real" APS**64**04\*3SQR chips should work.

For ESP PSRAM, all "real" PSRAM**64**\* should work.

64Mbit density = 8Mbyte PSRAM

This Table is just a snapshot of chips which worked

| Labeling on PSRAM module                       | Image | Status                    |
| ---------------------------------------------- | ----- | ------------------------- |
| IPUS / IPS640LS0 / 1815XBGN                |       |:heavy_check_mark:              |
| AP MEMORY / **64**04L-3SOR / 1040H / 110089G |       | :heavy_check_mark:                  |
| AP MEMORY / **64**04L-3SQR / 12205 / 150047G |       | :heavy_check_mark: 8MB              |
| AP MEMORY / **64**04L-3SQR / 12208 / 150047G |       | :heavy_check_mark: 8MB              |
| AP MEMORY / **64**04L-350R / 1120A / 130027G |       | :x: PSRAM not accessible|
| AP MEMORY / **64**04L-35QR / 11208 / 130025G |       | :x: PSRAM not accessible|
| AP MEMORY / **64**04L-3SQR / 13100 / 180026G|       | :x: PSRAM not accessible|
| AP MEMORY / **64**04L-3SQR / 11207 / 130024G|       | :x: PSRAM not accessible|
| AP MEMORY / 1604M-3SQR / 0280A / 070036G|       | :x: 2MB only!  |
| ESP PSRAM**64**H 462021 / 1B00286                |       | :heavy_check_mark:                  |
| ESP PSRAM**64**H 412021 /1A0039G                |       | :heavy_check_mark:   (8MB)                |
| ESP PSRAM16M 302020                        |       | :x: 2MB only! |
| ESP PSRAM16H 202020 / 050022G                |       | :x: 2MB only! |

# OV2640 - Camera

The experience with the camera only is based on single modules. It is well possible, that this module had a damage overall and other modules of the same type will work. Give it a try and report to me!

| Labeling on Flex-Connector | Image | Status                            |
| -------------------------- | ----- | --------------------------------- |
| TY-OV2 / 640-V2.0        |       | :heavy_check_mark:                          |
| DCX-OV2 / 640-V2         |       | :heavy_check_mark:                          |
| DC-26 / 40-V3            |       | :heavy_check_mark: 3x<br> :x: 1x |



# ESP32 Modules

| Module                                                       | Image | Status                         |
| ------------------------------------------------------------ | ----- | ------------------------------ |
| ESP32CAM / Different versions on the market!<br>Especially the PSRAM is sometimes labeled wrong<br>(Label: 4MB, Real: only 2 MB --> will not work!) |       | :heavy_check_mark:<br />with >=4 MB PSRAM! |
| ESP32-S3-EYE<br />No Flash LED, pins different used (e.g. LCD display) |       | **NOT OKAY**                   |



# SD Cards

Due to the limited free available GPIOs (due to all the extensions needed like: camera, SD card, LED-flash, ...) the SD card is connected in 1-wire mode. There are some cards, that are compatible with the esp32cam module for unknown reasons.
It is observed, that smaller cards (up to 4 GB) tend to be more stable and larger cards have more problems. But quite some exceptions in the forums (4 GB cards not working, 16 GB cards working like a charm).


# Devices known to work


### Modules (Old list, not up-to-date anymore):

See [https://github.com/jomjol/AI-on-the-edge-device/discussions/1732](https://github.com/jomjol/AI-on-the-edge-device/discussions/1732) for a more recent list.

 - [https://arduino-projekte.info/produkt/esp32-cam-v2-integriertem-ch340-mit-ov2640-kamera-modul/](https://arduino-projekte.info/produkt/esp32-cam-v2-integriertem-ch340-mit-ov2640-kamera-modul/) (see [https://github.com/jomjol/AI-on-the-edge-device/discussions/1041](https://github.com/jomjol/AI-on-the-edge-device/discussions/1041))

- [https://www.amazon.de/-/en/gp/product/B0B51CQ13R](https://www.amazon.de/-/en/gp/product/B0B51CQ13R)

- [https://www.reichelt.de/entwicklerboards-esp32-kamera-2mp-25--debo-cam-esp32-p266036.html?PROVID=2788&gclid=CjwKCAiAqaWdBhAvEiwAGAQlttJnV4azXWDYeaFUuNioMICh-jvxKp6Cifmcep9vvtoT2JRCDqBczRoC7Q0QAvD_BwE](https://www.reichelt.de/entwicklerboards-esp32-kamera-2mp-25--debo-cam-esp32-p266036.html?PROVID=2788&gclid=CjwKCAiAqaWdBhAvEiwAGAQlttJnV4azXWDYeaFUuNioMICh-jvxKp6Cifmcep9vvtoT2JRCDqBczRoC7Q0QAvD_BwE) (27.12.2022)

### SD Card
 
- Sandisk 2GB Micro SD Class 2 [Sandisk 2GB](https://www.amazon.co.uk/gp/product/B000N3LL02/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1)
AITRIP ESP32 and CAM [ESP-32/CAM](https://www.amazon.co.uk/gp/product/B08X49P8P3/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1)
- [Amazon US - Aideepen ESP32-CAM W BT Board ESP32-CAM-MB Micro USB to Serial Port CH-340G with OV2640 2MP Camera Module Dual Mode](https://www.amazon.com/gp/product/B0948ZFTQZ) with [Amazon US - Cloudisk 5Pack 4GB Micro SD Card 4 GB MicroSD Memory Card Class6](https://www.amazon.com/gp/product/B07QYTP4VN)

# Weak Wifi
The ESP32-CAM supports an external antenna. It requires some soldering skills but can improve the connection quality. See [https://randomnerdtutorials.com/esp32-cam-connect-external-antenna/](https://randomnerdtutorials.com/esp32-cam-connect-external-antenna/)
