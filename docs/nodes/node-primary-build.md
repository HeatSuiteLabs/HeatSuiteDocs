## Bill of Materials

Before we begin, here is a parts list of items for you to construct your own HeatSuite Primary Node. Optional parts are not needed. 

Table 1. Parts list for a Primary HeatSuite Node

| Part  | Description | Required | Note |
| :- | :-| :-: | :-: |
| HeatSuite PCB | Daughter board for interfacing environmental sensors | Yes|
| [LilyGo 7000G - 16MB](https://lilygo.cc/products/t-sim7000g)| Microcontroller with network connectivity, GPS, battery, and SD Card | Yes|  |
| 3010 5V Fan | Forced aspiration of sensors | No | [^1] |
| CR2032 Battery | For PCB onboard RTC | No | [^2] |
| [Sensirion SEN5X](https://sensirion.com/search/products?q=SEN5x) | Particulate Matter, [SEN54](https://sensirion.com/products/catalog/SEN54): adds VOC, [SEN55](https://sensirion.com/products/catalog/SEN55): adds NOx | No | [^3] |
| [Adafruit VEML7700](https://learn.adafruit.com/adafruit-veml7700/overview) | Ambient Light Sensor | No | [^4] |
| [PCB Artists Sound Meter ](https://pcbartists.com/product/i2c-decibel-sound-level-meter-module/) |Decibel A meter (Range 30 dB to 120 dB) | No | [^4] |
| [HY-WDC2E](https://www.alibaba.com/product-detail/HY-WDC2E-wind-detection-meter-ultrasonic_60776439328.html) | Ultrasonic anemometer | No | [^5] |
| [Winsen MH-Z1911A](https://www.winsen-sensor.com/product/mh-z1911a.html) | Carbon Dioxide Sensor (NDIR) | No | |

Table 2. The minimum additional hardware needed, and their quantities based on the housing selected.

| Part  | Quantity (Outdoor Housing) | Quantity (Indoor Housing) |
| :- | :-: | :-: |
|M3 threaded insert (OD: 4.2mm, Length: 5mm) | 3| 7|
|M3 screw (5mm) | 5| 5|
|M3 screw (16mm) | 2| 2|
|M3 nut | 4 | 4 |
|M4 threaded rod (150mm) | 4 | 0|
|M4 nut | 8 | 0|
|M4 knurled nut | 4 | 0 |


## Assembling The PCB tray

Both housings use the same PCB tray, which makes it easy to move from one design to the other. The tray is meant to be servicable, extending the life of the Primary Node. 

1. 

## Mounting the PCB

[^1]: Recommended for forced aspiration on the sensors, especially when used with the outdoor housing.
[^2]: Recommended for maintaining time on the onboard realtime clock during power down.
[^3]: Requires a double head [JST-GH 6-Pin connector](https://www.aliexpress.com/item/1005004962152962.html), HeatSuite allows you to use any of the environmental sensors in the SEN5X series.
[^4]: Requires a double head [JST-XH 5-Pin connector](https://www.aliexpress.com/item/1005005985026015.html), and a [male connector soldered](https://www.aliexpress.com/item/1005007703022445.html) to sensor pcb for easy connection.
[^5]: Must be programmed by manufacturer with the following settings: RS232, NMEA0183, 9600 Baud no parity
