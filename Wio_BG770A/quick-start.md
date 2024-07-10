# Wio BG770A クイックスタートガイド

1. Arduino IDEをインストール

    WebサイトからArduino IDEをダウンロードしてPCにインストールしてください。

    * Arduino Software ... `https://www.arduino.cc/en/software`

1. ボードサポートパッケージをインストール

    Arduino IDEの`Board manager URLs`に下記URLを追加して、ボードマネージャ画面で`SeeedJP nRF52 Boards by Seeed K.K.`をインストールしてください。

    * Board manager URL ... `https://www.seeed.co.jp/package_SeeedJP_index.json`

1. Wio Cellularライブラリをインストール

    下記ライブラリをArduino IDEにインストールしてください。

    * Wio Cellular ... `https://github.com/SeeedJP/wio_cellular`

1. LTEアンテナを接続

1. SIMを取付

1. PCに接続

    Wio BG770AをUSBケーブルでPCに接続してください。

1. DFUモードに切替

    RESETボタンをダブルクリックしてDFUモードに切り替えてください。
    正しく切り替わると、USER LEDがフワフワと点滅して、PCにBOOTというボリューム名のドライブが表示されます。

1. basic/blinkスケッチをアップロード

    Arduino IDEで`Board Version`を`1.0`に切り替えてから、Wio Cellularライブラリに含まれているbasic/blinkスケッチをアップロードしてください。
    正しくアップロードできると、USER LEDが点滅します。(0.2秒点灯/0.8秒消灯)
