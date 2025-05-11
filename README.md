# Project: REMOTE WIFI
- [x] Explorer hardware/software requirement.
    - Hardware requirement:
        - USB OTG Full speed.
        - SDIO/SPI support for interfacing with Micro SD.
        - Wifi capability.
    - Software requirement:
        - Firmware/Driver for SDMMC/USB-OTG-FS.
- [x] Evaluate differnce solutions.
    - ~~High-end ARM(STM32H7xx) + ESP32(S3/C6)~~
        - H7xx or F407 very powerfull, but expensive and hard to soldering.
        - They were planned to used in case CNC mahcine only accept USB-OTG high speed, but ater checking, it seem USB-OTG FS work just fine.
    - ESP32 S2 👎.
        - Slightly cheaper compare to S3, but hard to find.
    - ESP32 S3 👌.
        - Fully support USB-OTG FS and SDIO/SDMMC.

## Decide hardware and techstack.
- Hardware:
    - ESP32-S3.
    - SDIO.
    - USB-OTG FS.
- Software:
    - SDMMC (interfacing with SD card).
    - HTTP (file transfering), mDNS.
    - tinyUSB (USB library).

# Development process.
- [ ] firmware development:
    - [ ] SDMMC + USB MSC.
    - [ ] SDMMC + HTTP.
    - [ ] SDMMC + USB MSC + HTTP.
- [ ] Software developemnt.
    - [ ] Basic utility functions (backend).
    - [ ] UI development (frontend).
    - [ ] Testing.

# Ideas.
- [ ] Alternative communication method for IOT device over internet with certain level of security.
