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
    - HTTP (file transfering).
    - tinyUSB (USB library).
    - VFS.

# Development process.
- [ ] firmware development:
    - [x] SDMMC + TinyUSB => Normal USB MSC.
    - [ ] SDMMC + VFS + HTTP => HTTP file server.
        - [x] Read/download.
        - [x] Upload.
        - [ ] Delete.
    - [ ] Locking and access switching mechanism for USB and HTTP.
    - [ ] Problem: TinyUSB can work it direct memory access but VFS still unknown.
        - Mentioned in [this](https://github.com/espressif/esp-idf/issues/12990) but still no concrete solution yet.
- [ ] Software developemnt.
    - [ ] Basic utility functions (backend).
    - [ ] UI development (frontend).
    - [ ] Testing.

# Issues.
- [x] HTTP server started but not response to ping or request.
    - Soldering 'in-out' connector cause power supply to be unstable. Unsoldering it.
- [x] Wifi authentication fail sometime.
    - Company's wifi has some issue so ESP32 cannot connect to.
    - Add retry when fail as insurrance.
- [x] SDMMC return error 0x107.
    - Look like it was power supply issue, pretent it fixed for now.
- [ ] ESP32 HTTPD send imcomplete response or hang on to it.
- [ ] Upload and download content is really slow. Increase buffer size of VFS may fix (haven't tested yet)?

# Ideas.
- [ ] Alternative communication method for IOT device over internet with certain level of security.
- [ ] External RAM to beef up VFS performance.
