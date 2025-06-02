# basic/flash

不揮発性メモリFeRAMへのデータを書き込み、読み込みの基本的な操作を示すスケッチです。

## 概要

Wio BG770Aには、一時的にデータを保存するためのFeRAMを搭載しています。FeRAMは電源がオフしてもデータがされる不揮発性メモリで、FlashやEEPROMと比べて書き換え回数や書き換え速度に優れています。([FRAMと他メモリの特性比較](https://pr.fujitsu.com/prir/jp/news/2004/10/25b.pdf))

このスケッチはFeRAMにデータを書き込み、読み込みの基本的な操作を示しています。
USERボタンを押す都度、カウント値を1つ加算します。
カウント値はFeRAMに保存するので、Wio BG770Aの電源を切っても、それまでのカウント値を覚えています。
カウント値はシリアルモニタで確認できます。Wio BG770Aの起動したときと、USERボタンを押したときに表示します。
カウント値をゼロにリセットしたいときは、USERボタンを押しながらWio BG770Aを起動してください。

## 詳細

FeRAMの操作にAdafruit SPIFlashライブラリとWioCellularに含まれているWioNonVolatileMemoryをインクルードします。
必ず、WioNonVolatileMemory.hの前にAdafruit_SPIFlash.hをインクルードしてください。

```cpp
#include <Adafruit_SPIFlash.h>
#include <WioNonVolatileMemory.h>
```

そして、いくつかのグローバル変数を定義すると、Flashインスタンスが使えるようになります。同時にAdafruit_SPIFlashMemoryクラスとNonVolatileMemoryクラスも使うと少し便利です。代入文でFeRAMへ読み書きすることができるようになります。

```cpp
static const SPIFlash_Device_t SPIFLASH_DEVICE = FERAM_DEVICE_CONFIG;

static SPIClass FlashSpi(FERAM_SPI, PIN_FERAM_SO, PIN_FERAM_SCK, PIN_FERAM_SI);
static Adafruit_FlashTransport_SPI FlashTransport(PIN_FERAM_CS, FlashSpi);
static Adafruit_SPIFlash Flash(&FlashTransport);
static Adafruit_SPIFlashMemory FlashMemory(Flash);

static NonVolatileMemory NvmValue(FlashMemory, 0x0000, 4);
```

次に、初期化です。
Flashインスタンスを`Flash.begin()`で初期化します。
また、WPピンとHOLDピンを`pinMode()`と`digitalWrite()`で初期化します。
FlashインスタンスはFeRAMのWPピンとHOLDピンを一切操作しないからです。

```cpp
digitalWrite(PIN_FERAM_WP, HIGH);
digitalWrite(PIN_FERAM_HOLD, HIGH);
pinMode(PIN_FERAM_WP, OUTPUT);
pinMode(PIN_FERAM_HOLD, OUTPUT);
if (!Flash.begin(&SPIFLASH_DEVICE, 1)) abort();
```

以上で準備が整いました。
FeRAMの読み書きは`NvmValue`の`value()`関数を使用します。

```cpp
uint32_t value = NvmValue.value<uint32_t>();
```
```cpp
NvmValue.value<uint32_t>() = value;
```

## 参考リンク

* [FRAMと他メモリの特性比較](https://pr.fujitsu.com/prir/jp/news/2004/10/25b.pdf)
* [【FRAMプレゼント付！】メモリデバイス研究会 "愛のメモリー2022"](https://www.youtube.com/watch?v=biCdC61ESi8)
