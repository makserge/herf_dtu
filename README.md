# OpenDTU for HERF-800

https://github.com/tbnobody/OpenDTU

with E01-ML01DP5 module and ESP-32-S3 super mini

Wiring



Device Profile 

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
        "eth": {
            "enabled": false
        }
    }
]
