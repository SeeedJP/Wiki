# KB2 Groveモジュールが動かない、通信できない

## 事象

Groveモジュールの初期化でプログラムがフリーズしてしまう。

> https://zenn.dev/showm001/articles/2024-12-01-01
>
> M5Stackで動作検証をしたときと同じくSeeed社さんのBME68xライブラリと、リポジトリに含まれるテストプログラムをそのまま動かしてみたのですが・・・これが動かない。
センサーのinitの段階でだんまりになってしまうので～


## 原因

Wio BG770AからGroveモジュールの電源を供給していない可能性が高いです。
電源を供給していないときは、GROVE LEDが消灯しています。

## 回避策

VGROVE_ENABLE信号をオンします。

WioCellularライブラリを使用しているときは、下記コードでVGROVE_ENABLE信号をオンできます。

```cpp
WioCellular.begin();
digitalWrite(PIN_VGROVE_ENABLE, LOW);
```

## 参考リンク

* [groveコネクタを利用する際に電源供給開始のコードが必要なことをドキュメントに追加してほしい](https://github.com/SeeedJP/wio_cellular/issues/18)
