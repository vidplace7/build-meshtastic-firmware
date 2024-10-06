## Device info

<img class = "board-img img-thumbnail img-responsive rounded float-end" src="https://raw.githubusercontent.com/mrekin/MeshtasticCustomBoards/main/firmware/variants/diy/diy-heltec-ct62-tiny-1.02/photo_2024-04-06_13-12-28.jpg" width="20%"> 

**PCB_Board**: DIY

**MCU**: ESP32C3

**MCU_Board**: [Heltec CT-62](https://heltec.org/project/ht-ct62/) 

**LORA_Board**: [Heltec CT-62](https://heltec.org/project/ht-ct62/) 

**LINK**: [Github](firmware/variants/diy/diy-heltec-ct62-tiny-1.02)  



## Notes

**General**: Custom PCB

**Forum**: [Discord](https://discord.com/channels/867578229534359593/871539930852130866)

**Flashing**: [flasher](https://mrekin.duckdns.org/flasher/)

**State**:

**Known issues**: 

- ***ESP32C3*** is power hungry MCU (with BLE/WiFi enabled), at least with Meshtastic FW - so it is not best choise for battery powered devices (regular esp32 mcu is better).
      Initial variant, but not very interesting while ble sleep mode not working (other esp32c3 boards has this problem too). CT-62 has only few free pins, can be interesting only by small/compact size.
  
- ***ESP32C3*** currently has non working USB CDC (it is has problems wirh arduino platform <=2.0.14). Starting arduino platform 2.0.15 problem is solved and we need wait platformio release with this version support.
- - Currect variant has working CDC (with new platform) and based on [T3S3 fix](https://github.com/meshtastic/firmware/pull/3912), but flasher boot mode triggering don't work - this is web esptool problem (need enter to boot mode manually). [Jason2866 flasher](https://github.com/Jason2866/WebSerial_ESPTool/deployments/github-pages) able to trigger ESC32-C3/S3 to boot mode. As temporary solution - Connect/disconnect device on Jason page and then flash as usual here.

Minimum setup: CT62, R1, R2, (R7, R8, type-c connector), C2, C3, LDO, (Tantal capasitor), short wire SB1, SB2, SB3
