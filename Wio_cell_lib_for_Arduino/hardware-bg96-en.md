# Hardware - Wio LTE M1/NB1(BG96)


## Version

|Version|Date|
|:--|:--|
|ES|2018/09/26|
|ES2|2019/04/29|

## Pinout

![15](img/15.png)

## Spec

|Components|Function|Value|
|:--|:--|:--|
|STM32F4 MCU|Processor|STM32F439VI, ARM Cortex-M4 with FPU, 180MHz|
||Flash|2M Byte|
||SRAM|256K Byte|
|LTE|FDD-LTE|B1/B2/B3/B4/B5/B8/B12/B13/B18/B19/B20/B26/B28|
||TDD-LTE|B39|

## Battery
By connnecting Li-Ion battery to the battery connector of Wio LTE M1/NB1(BG96), you can keep continue the operation even if the power weren't supplied from USB connector.  

Since Wio LTE M1/NB1(BG96) has battery charger, you can charge Li-Ion battery if you supply the power from USB connector.

|Status|LED|
|:--|:--|
|Charging|ON|
|Full|OFF|
|Not existing|Blink|

The battery connector of Wio LTE M1/NB1(BG96) is JST PH. Please take care about following things.

* Polarity. ( Please make sure positive of the battery connected to `+` sign side of the connector. )
* You are using Li-Ion battery which have more than 690mAh capacity. (Wio LTE M1/NB1(BG96) will charge battery within 690mA. Connecting the batteries that have less than 690mAh may cause very dangerous situation.)
* When you recharge the battery, please keep watching. Do not left that alone.

**Handling of Li-Ion battery need enough care or attention. THIS FUNCTION IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.**

## Schematics

* [Wio LTE M1/NB1(BG96) v.ES(PDF)](https://github.com/SeeedJP/Wiki/raw/master/Wio_cell_lib_for_Arduino/files/Wio_BG96_vES.pdf)
