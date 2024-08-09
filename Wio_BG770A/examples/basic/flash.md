# basic/flash

不揮発性メモリFeRAMにデータを書き込み、読み込む基本的な操作を示すスケッチです。

## 概要

USERボタンを押す都度、FeRAMに保存しているカウント値を1つ加算します。
カウント値はFeRAMの0番地から4バイトに保存しています。

FeRAMに保存しているカウント値はシリアルモニタに表示します。

USERボタンを押しながら起動もしくはRESETボタンをクリックすると、FeRAMに保存しているカウント値をゼロにします。

## 詳細

FeRAMの操作にAdafruit SPIFlashライブラリを使用します。

下記コードで、Flashインスタンスを使えるようにします。

```cpp
#include <Adafruit_SPIFlash.h>

static const SPIFlash_Device_t SPIFLASH_DEVICE = FERAM_DEVICE_CONFIG;

static SPIClass FlashSpi(FERAM_SPI, PIN_FERAM_SO, PIN_FERAM_SCK, PIN_FERAM_SI);
static Adafruit_FlashTransport_SPI FlashTransport(PIN_FERAM_CS, FlashSpi);
static Adafruit_SPIFlash Flash(&FlashTransport);
```

`Flash.begin()`でFlashインスタンスを初期化します。くわえて、
WPピンとHOLDピンを`pinMode()`と`digitalWrite()`で初期化します。FlashインスタンスはFeRAMのWPピンとHOLDピンを操作しないからです。

```cpp
digitalWrite(PIN_FERAM_WP, HIGH);
digitalWrite(PIN_FERAM_HOLD, HIGH);
pinMode(PIN_FERAM_WP, OUTPUT);
pinMode(PIN_FERAM_HOLD, OUTPUT);
Flash.begin(&SPIFLASH_DEVICE, 1);
```

FeRAMからの読み込みは`Flash.readBuffer()`、書き込みは`Flash.writeBuffer()`を呼びます。

```cpp
  if (Flash.readBuffer(0, reinterpret_cast<uint8_t*>(&value), sizeof(value)) != sizeof(value)) abort();
```
```cpp
  if (Flash.writeBuffer(0, reinterpret_cast<uint8_t*>(&value), sizeof(value)) != sizeof(value)) abort();
```
