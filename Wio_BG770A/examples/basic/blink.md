# basic/blink

プログラムをコンパイル、アップロード、実行できるかを確認するためのスケッチです。

## 概要

USER LEDを点滅します。
点灯時間は0.2秒で、消灯時間は0.8秒です。

## 詳細

USER LED点灯 -> 0.2秒待機 -> USER LED消灯 -> 0.8秒待機、を繰り返します。

```cpp
digitalWrite(LED_BUILTIN, HIGH);    // USER LEDを点灯
delay(200);                         // 200ミリ秒、待機
digitalWrite(LED_BUILTIN, LOW);     // USER LEDを消灯
delay(800);                         // 800ミリ秒、待機
```
