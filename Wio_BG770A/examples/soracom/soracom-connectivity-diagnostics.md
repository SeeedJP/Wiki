# soracom/soracom-connectivity-diagnostics

SORACOMプラットフォームへの接続を確認するスケッチです。

## 概要

SORACOMプラットフォームの`pong.soracom.io`にpingパケットが通信できるかを、状況を表示しながら確認します。

1. タイトル

    ```
    ****************************
    * Connectivity diagnostics *
    ****************************
    ```

1. 通信モジュールの初期化

    ```
    --- Initializing modem, please wait for a while...[OK]
    Target modem: BG770AGLAAR02A05_JP_01.200.01.200
    ```

1. 通信モジュールおよびIoT SIMの状態表示

    ```
    --- Getting modem info...
    > AT+GSN
    865502060000279
    > AT+CIMI
    440103167698583
    > AT+QSIMSTAT?
    +QSIMSTAT: 0,1
    ```

1. ネットワーク設定の書き込み

    ```
    --- Executing AT commands to connect SORACOM network...
    > AT+CGDCONT=1,"IP","soracom.io","0.0.0.0",0,0,0
    Ok
    > AT+QCFG="iotopmode",0,1
    Ok
    > AT+QCFG="nwscanseq",00,1
    Ok
    ```

1. セルラー網への接続

    ```
    --- Connecting to cellular network, please wait for a while...[OK]
    ```

1. ネットワーク接続の状態表示

    ```
    --- Getting network info...
    > AT+QIACT?
    +QIACT: 1,1,1,"10.225.154.84"
    > AT+QCSQ
    +QCSQ: "eMTC",-84,-91,165,-6
    > AT+COPS?
    +COPS: 0,0,"NTT DOCOMO",7
    > AT+CGPADDR=1
    +CGPADDR: 1,"10.225.154.84"
    ```

1. SORACOMプラットフォームへの接続確認

    ```
    --- Conntectivity test: Ping to pong.soracom.io...
    > AT+QPING=1,"pong.soracom.io",3,3
    Ok
    Dest="100.127.100.127", Bytes=32, Time=56, TTL=64
    Dest="100.127.100.127", Bytes=32, Time=67, TTL=64
    Dest="100.127.100.127", Bytes=32, Time=93, TTL=64
    Sent=3, Received=3, Lost=0, Min=56, Max=93, Avg=72

    --- Execution completed, please write your own sketch and enjoy it.
    ```
