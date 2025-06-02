# OpenDTU for HERF-800

Based on with EBYTE E01-ML01DP5 module and ESP-32-S3 super mini (4MB Flash)


1. OpenDTU

Download source code from

https://github.com/tbnobody/OpenDTU

put in root folder platformio_override.ini with content

monitor_port = /dev/cu.usbmodem144401
upload_port = /dev/cu.usbmodem144401

[env:generic_esp32s3_usb]
board_upload.flash_size = 4MB

Build project and upload it to board via USB

2. OpenDTU-OnBattery

Download source code from

https://github.com/hoylabs/OpenDTU-OnBattery


put in root folder platformio_override.ini with content

monitor_port = /dev/cu.usbmodem144401
upload_port = /dev/cu.usbmodem144401

[env:generic_esp32s3_usb]
board_upload.flash_size = 4MB
board_build.partitions = partitions_custom_4mb.csv

Build project and upload it to board via USB

3. Wiring 

EBYTE E01-ML01DP5 to ESP32-S3

nRF24L01+	ESP32-S3
VCC		3.3V
GND		GND
CE		GPIO 1
CSN		GPIO 3
SCK		GPIO 12
MOSI		GPIO 11
MISO		GPIO 13
IRQ		GPIO 5

0.96 Inch OLED

OLED

VCC		5V
GND		GND
SDA		GPIO 7
SCL		GPIO 6	


4. Reboot board and connect to AP "OpenDTU-*" with ip 192.168.4.1

5. Import device profile (howto here https://www.opendtu.solar/firmware/device_profiles/)


nrf24.json

[
    {
        "name": "NRF24",
        "nrf24": {
            "miso": 13,
            "mosi": 11,
            "clk": 12,
            "irq": 5,
            "en": 1,
            "cs": 3
        },
	"display": {
            "type": 2,
            "data": 7,
            "clk": 6
        },
        "eth": {
            "enabled": false
        }
    }
]
