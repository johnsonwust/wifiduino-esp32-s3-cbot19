# Getting Started

This guide summarizes the publicly readable setup information for the WiFiduino ESP32-S3 CBot19 board. The board-specific tutorial is in Chinese; this English summary links to the original article rather than reproducing it.

## Before connecting

- Use a stable 5 V supply through USB-C.
- The battery connector is for a 3.7 V lithium battery. Check polarity and connector orientation before connecting it.
- The source article warns that the board power switch must be on while flashing the XiaoZhi firmware.

## Arduino IDE

1. Install the ESP32-S3 Arduino board support and the libraries required by your project.
2. Connect the board over USB and select its serial port.
3. Use the board-specific resources below for pin assignments and examples. The community article identifies the display controller as ST7789 and provides examples for the LCD and XiaoZhi voice assistant.

References:

- [ESP32-S3 core board Arduino environment and driver setup](https://arduino.me/a/3066)
- [ESP32-S3 AIoT learning resources](https://arduino.me/s/52?aid=3094)
- [Board overview, pin assignments, and examples](https://arduino.me/a/3274)

## AilyBlockly

The source tutorial describes choosing **ESP32S3Dev board** in AilyBlockly, then using its examples/project gallery. It mentions a `esp32s3WS2812blink` example and an `AI_Board lcd显示` LCD example. Exact interface names may vary by AilyBlockly version.

- [AilyBlockly environment setup](https://arduino.me/a/3240)

## XiaoZhi firmware

The source article links to a prebuilt firmware archive: [AI_KIT1.rar](http://download.openjumper.cn/AI_KIT1.rar). It recommends Espressif's [Flash Download Tool guide](https://docs.espressif.com/projects/esp-test-tools/zh_CN/latest/esp32/production_stage/tools/flash_download_tool.html), with chip type **ESP32-S3**, work mode **develop**, and load mode **USB**.

Firmware compatibility, licensing, and archive contents have not been independently checked. This repository links to the supplier-hosted archive; it does not redistribute it.

## Interface and pin notes

From the board article:

| Function | Signals / GPIO |
| --- | --- |
| TFT display | DC 11, SDA 10, SCL 12, CS 13, RES 14, BL 3 |
| Digital microphone | SCK 5, SD 6, WS 4 |
| Audio amplifier | DIN 7, BCLK 15, LRCLK 16 |
| Volume buttons | VOL+ GPIO 40, VOL− GPIO 39 |
| Expansion | I²C and UART (MX1.25 4-pin connector); GPIO also available |
| Battery | 3.7 V through MX1.25 2-pin connector |

Verify pin mappings against the actual board revision before wiring external hardware. The article text has some interface/connector wording inconsistencies; use the board silkscreen and original documentation as the final reference.
