# grove/grove-rotary-angle-sensor

可変抵抗の回転量をシリアルモニタに表示するスケッチです。

## 概要

このスケッチはGrove - Analogの使用例です。
Grove - Analogコネクタに接続した[Grove - Rotary Angle Sensor](https://www.seeedstudio.com/Grove-Rotary-Angle-Sensor.html)のノブ回転位置をシリアルモニタに表示します。
表示の周期は0.5秒です。

<a href="../../media/45.jpg"><img src="../../media/45.jpg" width="300"></a>

<a href="../../media/46.gif"><img src="../../media/46.gif" width="500"></a>

## 詳細

WioCellular.hをインクルードして、WioCellularインスタンスを使えるようにします。

```cpp
#include <WioCellular.h>
```

セルラーモジュールとのインターフェースを初期化して、Groveの電源を投入します。

```cpp
WioCellular.begin();
WioCellular.enableGrovePower();
```

アナログ入力の分解能（ビット数）を14ビットに変更します。
(デフォルトは10ビットです。)

```cpp
analogReadResolution(14);
```

`analogRead()`で回転位置に対応した値を取得します。

```cpp
const auto rotaryAngleRaw = analogRead(ROTARY_ANGLE_PIN);
```

`analogRead()`の値を`/ 16383 * 0.6f * 6`するとアナログ入力の電圧(0~3.3[V])になります。
さらに3.3で割ると、正規化した値(0~1)になります。

```cpp
const auto rotaryAngle = (float)rotaryAngleRaw / 16383 * 0.6f * 6 / 3.3f;
```
