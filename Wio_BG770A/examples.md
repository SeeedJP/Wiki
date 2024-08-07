# Wio BG770A サンプルスケッチ

## 一覧

* 💪 ... スキルアップ。スケッチの中身を読んでみましょう。
* 🌶️ ... 難易度、中。（中辛）
* 🌶️🌶️ ... 難易度、高。（激辛）

### 基本

||スケッチ|内容|必要なもの|
|:--|:--|:--|:--|
||basic/blink|USER LEDを点滅します。<br>> [追加情報](#basicblink)||
|💪|basic/flash|USERボタンを押すと、FeRAMに書かれているカウント値を加算します。USERボタンを押しながら起動するとカウント値をゼロにリセットします。<br>> [追加情報](#basicflash)||
|💪|basic/watchdog|USERボタンを押さずに10秒経過すると、ウォッチドックがCPUをリセットします。> [追加情報](#basicwatchdog)||

### Grove

||スケッチ|内容|必要なもの|
|:--|:--|:--|:--|
|💪|grove/grove-buzzer|ブザーを鳴らします。|[Grove - Piezo Buzzer/Active Buzzer](https://www.seeedstudio.com/Grove-Buzzer.html)|
|💪|grove/grove-button|ボタンのON/OFFをシリアルモニタに表示します。|[Grove - Button](https://www.seeedstudio.com/Grove-Button.html)|
|💪|grove/grove-rotary-angle-sensor|可変抵抗の回転量をシリアルモニタに表示します。|[Grove - Rotary Angle Sensor](https://www.seeedstudio.com/Grove-Rotary-Angle-Sensor.html)|
|💪|grove/grove-accelerometer|加速度センサーの値をシリアルモニタに表示します。|[Grove - ADXL345 - 3-Axis Digital Accelerometer(±16g)](https://www.seeedstudio.com/Grove-3-Axis-Digital-Accelerometer-16g.html)|
|💪|grove/grove-gps|GPSの位置情報をシリアルモニタに表示します。|[Grove - GPS Module](https://www.seeedstudio.com/Grove-GPS-Module.html)|
|💪|grove/grove-ultrasonic-ranger|Grove - 超音波距離センサーの距離をシリアルモニタに表示します。|[Grove - Ultrasonic Distance Sensor](https://www.seeedstudio.com/Grove-Ultrasonic-Distance-Sensor.html)|

### セルラー通信

||スケッチ|内容|必要なもの|
|:--|:--|:--|:--|
||cellular/transparent|セルラーモジュールをシリアルモニタからATコマンドで操作します。<br>> [追加情報](#cellulartransparent)|nanoSIM|
||cellular/shell🌶️|セルラーモジュールをシリアルモニタから操作するシェルです。<br>> [追加情報](#cellularshell)|nanoSIM|

### セルラー通信（SORACOMプラットフォーム）

||スケッチ|内容|必要なもの|
|:--|:--|:--|:--|
||soracom/soracom-connectivity-diagnostics🌶️|SORACOMプラットフォームへの接続を確認します。<br>> [追加情報](#soracomsoracom-connectivity-diagnostics)|SORACOM Air for セルラー|
|💪|soracom/soracom-uptime|稼働時間をSORACOM Unified Endpointへ送信します。|SORACOM Air for セルラー|
|💪|soracom/soracom-uptime-tcpclient|稼働時間をSORACOM Unified Endpointへ送信します。<br>WioCellularTcpClientクラスを使用して実装しています。|SORACOM Air for セルラー|
|💪|soracom/soracom-uptime-lp🌶️🌶️|稼働時間をSORACOM Unified Endpointへ送信します。PSM機能を使って電力消費を抑止しています。|SORACOM Air for セルラー|
|💪|application/soracom-gps-tracker🌶️🌶️|GPSで取得した位置情報をSORACOM Unified Endpointへ送信します。|[Grove - GPS Module](https://www.seeedstudio.com/Grove-GPS-Module.html)<br>SORACOM Air for セルラー|

## basic/blink

### 概要

プログラムをコンパイル、アップロード、実行できるかを確認するためのスケッチです。

### 動作

USER LEDを点滅します。
点灯時間は0.2秒で、消灯時間は0.8秒です。

### 詳細

USER LED点灯 -> 0.2秒待機 -> USER LED消灯 -> 0.8秒待機、を繰り返します。

```cpp
digitalWrite(LED_BUILTIN, HIGH);    // USER LEDを点灯
delay(200);                         // 200ミリ秒、待機
digitalWrite(LED_BUILTIN, LOW);     // USER LEDを消灯
delay(800);                         // 800ミリ秒、待機
```

## basic/flash

### 概要

不揮発性メモリFeRAMにデータを書き込み、読み込む基本的な操作を示すスケッチです。

### 動作

USERボタンを押す都度、FeRAMに保存しているカウント値を1つ加算します。
カウント値はFeRAMの0番地から4バイトに保存しています。

FeRAMに保存しているカウント値はシリアルモニタに表示します。

USERボタンを押しながら起動もしくはRESETボタンをクリックすると、FeRAMに保存しているカウント値をゼロにします。

### 詳細

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

## basic/watchdog

### 概要

ウォッチドッグタイマでプログラムが暴走したり停止したときにCPUを再起動させる操作を示すスケッチです。

### 動作

USERボタンを定期的にクリックしているとプログラムは動き続けますが、クリックせず10秒経過するとCPUが再起動します。
ウォッチドックタイマがCPUをリセット、再起動させます。

### 詳細

ウォッチドッグタイマの操作にAdafruit SleepyDog Libraryを使用します。

Adafruit_SleepyDog.hをインクルードするとWatchdogインスタンスが使えるようになります。

```cpp
#include <Adafruit_SleepyDog.h>
```

ウォッチドッグタイマのタイムアウト時間を`Watchdog.enable()`で設定します。

```cpp
Watchdog.enable(10000);
```

以降、指定した時間以内に定期的に`Watchdog.reset()`を呼んでください。呼ばないとウォッチドッグタイマがCPUをリセット、再起動させます。

```cpp
Watchdog.reset();
```

## cellular/transparent

### 概要

セルラーモジュールをATコマンドの手入力で操作するスケッチです。

### 動作

セルラーモジュールの電源をオンして、シリアルモニタとセルラーモジュール透過的につなぎます。
シリアルモニタからの入力をセルラーモジュールへ送信し、セルラーモジュールからの受信をシリアルモニタに出力します。

### ATコマンド例

* 初期化

    ```
    AT&F1           // 工場出荷時の設定に戻す
    AT+IFC=2,2      // ハードウェアフロー制御を有効化
    AT+QSCLK=2      // スリープモードを有効化
    ```

* ネットワークオペレーター

    ```
    AT+COPS=?       // 接続できるネットワークオペレーターを取得
    AT+COPS?        // 接続しているネットワークオペレーターを取得
    ```

* PDPコンテキストを設定

    ```
    AT+CGDCONT?                                         // PDPコンテキストを取得
        AT+CFUN=0                                       // 機能レベルを最小化
        AT+CGDCONT=1,"IP","soracom.io","0.0.0.0",0,0,0  // PDPコンテキストを設定
        AT+CFUN=1                                       // 機能レベルを最大化
    ```

* セルラーモジュールやSIMの情報

    ```
    AT+QGMR         // ファームウェアのレビジョンを取得
    AT+GSN          // IMEIを取得
    AT+CPIN?        // PIN状態を取得
    AT+CIMI         // IMSIを取得
    AT+QCCID        // ICCIDを取得
    AT+CNUM         // 電話番号を取得
    ```

* ネットワーク登録状態

    ```
    AT+CEREG?       // EPSネットワーク登録状態を取得
    AT+COPS?        // 接続しているネットワークオペレーターを取得
    AT+CGATT?       // パケットドメインサービスの状態を取得
    ```

* SORACOM HarvestへHTTP POST

    ```
    AT+QHTTPURL=25                  // HTTPのURLを設定(25バイト)
    http://harvest.soracom.io
    AT+QHTTPCFG="contenttype",1     // HTTPのContent-Typeをtext/plainに設定
    AT+QHTTPPOST=5                  // HTTP POST(5バイト)
    hello
    ```

## cellular/shell

### 概要

セルラーモジュールを独自コマンドで操作するスケッチです。

### 動作

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

### コマンド例

* SORACOM Unified Endpointへ送信

    ```
    socketopen TCP uni.soracom.io 23080
    socketsendreceive {"item1":12.34}
    socketclose
    ```

## soracom/soracom-connectivity-diagnostics

### 概要

SORACOMプラットフォームへの接続を確認するスケッチです。

### 動作

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
