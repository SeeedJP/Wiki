# Wio BG770A クイックスタートガイド

## PCにソフトウェアをインストールしよう

1. Arduino IDEをインストール

    ArduinoのWebサイトからArduino IDEをダウンロードしてPCにインストールしてください。

    https://www.arduino.cc/en/software

1. ボードサポートパッケージとWio Cellularライブラリをインストール

    1. 基本設定画面（メニューの、ファイル > 基本設定）にある`追加のボードマネージャのURL`に`https://www.seeed.co.jp/package_SeeedJP_index.json`を追加してください。

    1. ボードマネージャ画面で`wio bg770a`を検索して、`SeeedJP nRF52 Boards by Seeed K.K.`をインストールしてください。

    1. ライブラリマネージャ―画面で`wio cellular`を検索して、`Wio Cellular by Seeed K.K.`をインストールしてください。

    [![](https://img.youtube.com/vi/t8lNZ8HixHk/0.jpg)](https://www.youtube.com/watch?v=t8lNZ8HixHk)

## Wio BG770Aにスケッチを書き込んでみよう

1. PCにWio BG770Aを接続

    PCとWio BG770AをUSBケーブルで接続してください。

    [![](https://img.youtube.com/vi/lbEq_0Bwr9A/0.jpg)](https://www.youtube.com/watch?v=lbEq_0Bwr9A)

1. DFUモードに切替

    RESETボタンをダブルクリックしてDFUモードに切り替えてください。
    正しく切り替わると、USER LEDがフワフワと点滅して、PCに`BOOT`というボリューム名のドライブが表示されます。

    [![](https://img.youtube.com/vi/T-7dgf2oDV0/0.jpg)](https://www.youtube.com/watch?v=T-7dgf2oDV0)

1. blinkスケッチをアップロード

    1. スケッチ例にあるblinkスケッチを開いてください。（メニューの、ファイル > スケッチ例 > Wio Cellular > basic > blink）

    1. ボードを`Seeed Wio BG770A COMx`にしてください。
    一覧にSeeed Wio BG770Aが表示されないときは、DFUモードに切り替えできているかを確認してください。（USER LEDがフワフワと点滅している？）

    1. `Board Version`（メニューの、ツール > Board Version）を`1.0`にしてください。

    1. 書き込みを実行してください。
    正しく書き込みできると、USER LEDが点滅します。(0.2秒点灯/0.8秒消灯)

    [![](https://img.youtube.com/vi/kh8cEM4pA-c/0.jpg)](https://www.youtube.com/watch?v=kh8cEM4pA-c)

## アンテナとSIMを取り付けよう

1. LTEアンテナを取付

    [![](https://img.youtube.com/vi/brZZu70qjm4/0.jpg)](https://www.youtube.com/watch?v=brZZu70qjm4)

1. nanoSIMを取付

    [![](https://img.youtube.com/vi/OvDVqKqDIgI/0.jpg)](https://www.youtube.com/watch?v=OvDVqKqDIgI)
