# Project: REMOTE WIFI
- [x] Explorer hardware/software requirement.
    - Hardware:
        - USB OTG Full speed.
        - SDIO/SPI support for interfacing with Micro SD.
        - Wifi capability.
    - Software:
        - Firmware/Driver for SDMMC/USB-OTG-FS.
- [x] Evaluate differnce solutions.
    - ~~High-end ARM(STM32H7xx) + ESP32(S3/C6)~~
        - H7xx or F407 was big, expensive, hard to soldering.
        - They were planned to used in case CNC mahcine only accept USB-OTG full speed, but ater checking, it seem USB-OTG HS work just fine.
    - ESP32 S2 👎.
        - Slightly cheaper compare to S3, but hard to find.
    - ESP32 S3 👌.
        - Fully support USB-OTG and SDIO/SDMMC.
- [ ] Software development:
    - [ ] USB MSC firmware.
    - [ ] SDIO/SDMMC firmware.


