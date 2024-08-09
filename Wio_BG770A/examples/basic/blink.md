# basic/blink

プログラムをコンパイル、アップロード、実行できるかを確認するためのスケッチです。

## 概要

このスケッチはUSER LEDを点滅します。
USER LEDが点滅することで、アップロードしたプログラムがWio BG770AのCPUで動いていることがわかります。
USER LEDの点滅は、点灯時間が0.2秒で消灯時間が0.8秒です。

## 詳細

`digitalWrite(LED_BUILTIN, HIGH)`を呼ぶとLEDが点灯します。
`HIGH`を`LOW`にすると消灯します。

点灯、消灯時間は`delay()`で調整します。
引数の単位はミリ秒です。

```cpp
digitalWrite(LED_BUILTIN, HIGH);
delay(200);
digitalWrite(LED_BUILTIN, LOW);
delay(800);
```
