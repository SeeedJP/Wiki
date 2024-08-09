# cellular/shell

セルラーモジュールを独自コマンドで操作するスケッチです。

## 概要

セルラーモジュールの電源をオンして、PDPコンテキストを設定します。APNは`soracom.io`です。
シリアルモニタからコマンドを受けて、コマンドに応じた処理を実行します。

|コマンド|内容|
|:--|:--|
|info|セルラーモジュールやSIMの情報(ファームウェアのレビジョン、IMEIなど)を表示します。|
|status|セルラー通信の状態を表示します。|
|pdpctx|PDPコンテキストを表示します。|
|socket|接続しているソケットの状態を表示します。|
|socketopen TCP \<host> \<port>|TCPソケットで指定したホストに接続します。|
|socketsend \<payload>|ソケットへ送信します。|
|socketreceive|ソケットから受信します。|
|socketsendreceive \<payload>|ソケットへ送信して、受信します。|
|socketclose|ソケットを切断します。|
|sleep|**実験段階** セルラーモジュールをスリープモードへ遷移します。|
|wakeup|**実験段階** セルラーモジュールをスリープモードから復帰します。|
|edrx|**実験段階** eDRXを有効にします。|
|psm|**実験段階** PSMを有効にします。|
|resetallsettings|セルラーモジュールを工場出荷時の設定に戻します。|
|transparent|シリアルモニタとセルラーモジュール透過的につなぎます。USERボタンをクリックするとプロンプトに戻ります。|
|help|コマンド一覧を表示します。|

## コマンド例

* SORACOM Unified Endpointへ送信

    ```
    socketopen TCP uni.soracom.io 23080
    socketsendreceive {"item1":12.34}
    socketclose
    ```
