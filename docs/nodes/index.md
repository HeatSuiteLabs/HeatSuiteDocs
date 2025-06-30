## Start

The HeatSuite platform contains Environmental Nodes which conduct various tasks, including monitoring the local environment, communicating with wearable devices for various tasks, the localization of users, and communication with the HeatSuite Cloud Instance. This documentation will give you an overview of what the nodes do and how to assemble them.

## Types of Nodes

At present, we have two primary nodes in the HeatSuite platform: Primary and and Secondary Nodes. The Primary nodes are the central points of contact for all devices within the HeatSuite ecosystem. The secondary nodes, previously called satellite nodes, are stripped down versions of the Primary nodes, and communicate directly with one paired Primary node for submitting data. 

## Primary Nodes

Within this category, we have 2 primary build options depending on what you want to measure and where. Each has their own advantages, and it is up to you to decide which is best for your application. The best part about the HeatSuite ecosystem is that all the parts are modular, such that you can change housing and include/remove components as needed.

### Housing Options

Outdoor housing:

Indoor housing:

### Environmental Monitoring Endpoints

Each sensor has one or more environmental variables which it monitors and collects. The HeatSuite system does not try to combine, estimate, or interpret the variables for you. All sensor data is stored and collected for the researcher to use as desired. The minimum temporal resolution is saving environmental data locally on an SD card every minute. 

Table 2. The measurement endpoints for each sensor. Onboard means it is available already on the main HeatSuite PCB, while a :material-plus: icon means its supported, but must be added separately.

| Sensor    | Onboard?   | Ta    | RH    | CO2 | NOx | VOC | PM  | Air Speed | dbA | Lux |
| :-        | :-:       | :-:   | :-:   | :-: | :-: | :-: | :-: | :-:       | :-: | :-: |
|[SHT41](https://sensirion.com/products/catalog/SHT41)| :white_check_mark: | :white_check_mark:  | :white_check_mark: | 
|[SCD41](https://sensirion.com/products/catalog/SCD41)| :white_check_mark: |:white_check_mark: |:white_check_mark: |:white_check_mark: | 
|[SGP40](https://sensirion.com/products/catalog/SCD41)| :white_check_mark: ||||:white_check_mark: |:white_check_mark: |
|[SHT85](https://sensirion.com/products/catalog/SHT85)| :material-plus: | :white_check_mark: |:white_check_mark: |
|[SEN55](https://sensirion.com/products/catalog/SEN55)| :material-plus: | :white_check_mark: |:white_check_mark: || :white_check_mark: |:white_check_mark: |:white_check_mark: |
|[HY-WDC2E](https://www.alibaba.com/product-detail/HY-WDC2E-wind-detection-meter-ultrasonic_60776439328.html)| :material-plus: ||||||| :white_check_mark: |
|[PCB Artists Sound](https://pcbartists.com/product/i2c-decibel-sound-level-meter-module/)| :material-plus: |||||||| :white_check_mark: |
|[Adafruit VEML7700](https://learn.adafruit.com/adafruit-veml7700/overview)| :material-plus: ||||||||| :white_check_mark: |

## Secondary Nodes

TBD