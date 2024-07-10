# Wio BG770A サンプルプログラム

|スケッチ|内容|依存ライブラリ|必要なもの|Groveコネクタ|
|:--|:--|:--|:--|:--|
|application/soracom-gps-tracker|GPSで取得した位置情報をSORACOM Unified Endpointへ送信します。|[ArduinoJson 7.0.4](https://github.com/bblanchon/ArduinoJson)|[Grove - GPS Module](https://www.seeedstudio.com/Grove-GPS-Module.html)<br>SORACOM Air for セルラー|Grove-UART|
|basic/blink|USER LEDを点滅します。||||
|basic/flash|USERボタンを押すと、FeRAMに書かれているカウント値を加算します。USERボタンを押しながら起動するとカウント値をゼロにリセットします。<br>[追加情報](#basicflash)|[Adafruit SPIFlash 4.3.4](https://github.com/adafruit/Adafruit_SPIFlash)<br>[SdFat - Adafruit Fork 2.2.3](https://github.com/adafruit/SdFat)|||
|basic/watchdog|USERボタンを押さずに10秒経過すると、ウォッチドックがCPUをリセットします。||||
|cellular/shell|セルラーモジュールをシリアルモニタから操作するシェルです。<br>> [追加情報](#cellularshell)|[Natural Tiny Shell 0.3.1](https://github.com/matsujirushi/ntshell)|nanoSIM||
|cellular/transparent|セルラーモジュールをシリアルモニタからATコマンドで操作します。<br>> [追加情報](#cellulartransparent)||nanoSIM||
|grove/grove-accelerometer|加速度センサーの値をシリアルモニタに表示します。||[Grove - ADXL345 - 3-Axis Digital Accelerometer(±16g)](https://www.seeedstudio.com/Grove-3-Axis-Digital-Accelerometer-16g.html)|Grove-I2C|
|grove/grove-button|ボタンのON/OFFをシリアルモニタに表示します。||[Grove - Button](https://www.seeedstudio.com/Grove-Button.html)|Grove-Digital|
|grove/grove-buzzer|ブザーを鳴らします。||[Grove - Piezo Buzzer/Active Buzzer](https://www.seeedstudio.com/Grove-Buzzer.html)|Grove-Digital|
|grove/grove-gps|GPSの位置情報をシリアルモニタに表示します。||[Grove - GPS Module](https://www.seeedstudio.com/Grove-GPS-Module.html)|Grove-UART|
|grove/grove-rotary-angle-sensor|可変抵抗の回転量をシリアルモニタに表示します。||[Grove - Rotary Angle Sensor](https://www.seeedstudio.com/Grove-Rotary-Angle-Sensor.html)|Grove-Analog|
|grove/grove-ultrasonic-ranger|Grove - 超音波距離センサーの距離をシリアルモニタに表示します。|[Grove Ultrasonic Ranger 1.0.1](https://github.com/Seeed-Studio/Seeed_Arduino_UltrasonicRanger)|[Grove - Ultrasonic Distance Sensor](https://www.seeedstudio.com/Grove-Ultrasonic-Distance-Sensor.html)|Grove-Digital|
|soracom/soracom-uptime|稼働時間をSORACOM Unified Endpointへ送信します。|[ArduinoJson 7.0.4](https://github.com/bblanchon/ArduinoJson)|SORACOM Air for セルラー||
|soracom/soracom-uptime-lp|稼働時間をSORACOM Unified Endpointへ送信します。PSM機能を使って電力消費を抑止しています。|[ArduinoJson 7.0.4](https://github.com/bblanchon/ArduinoJson)|SORACOM Air for セルラー||
|soracom/soracom-uptime-tcpclient|稼働時間をSORACOM Unified Endpointへ送信します。<br>WioCellularTcpClientクラスを使用して実装しています。|[ArduinoJson 7.0.4](https://github.com/bblanchon/ArduinoJson)|SORACOM Air for セルラー||

## basic/flash

```mermaid
flowchart TD
    Start((Start))
    J1{USERボタンが押されている？}
    T1[FeRAMへゼロを書き込み]
    T2[FeRAMからカウント値を読み出して表示]
    T3[0.5秒待機]
    T4[USERボタンが押されるまで待機]
    T5[カウント値を加算してFeRAMへ書き込み]

    Start --> J1
    J1 -->|Yes| T1
    T1 --> T2
    J1 -->|No| T2
    T2 --> T3
    T3 --> T4
    T4 --> T5
    T5 --> T2
```

## cellular/shell

### コマンド例

* ヘルプ表示

    ```
    help
    ```

* SORACOM Unified Endpointへ送信

    ```
    socketopen TCP uni.soracom.io 23080
    socketsendreceive {"item1":12.34}
    socketclose
    ```

## cellular/transparent

### ATコマンド例

* 初期化

    ```
    AT&F1
    AT+IFC=2,2
    AT+QSCLK=2
    ```

* ネットワークオペレーターを取得

    ```
    AT+COPS=?
    AT+COPS?
    ```

* PDPコンテキストを設定

    ```
    AT+CGDCONT?
        AT+CFUN=0
        AT+CGDCONT=1,"IP","soracom.io","0.0.0.0",0,0,0
        AT+CFUN=1
    ```

* セルラーモジュールやSIMの情報

    ```
    AT+QGMR         // Revision
    AT+GSN          // IMEI
    AT+CPIN?        // SIM State
    AT+CIMI         // IMSI
    AT+QCCID        // ICCID
    AT+CNUM         // Phone Number
    ```

* ネットワーク登録状態

    ```
    AT+CEREG?       // Registration State
    AT+COPS?        // Operator
    AT+CGATT?       // Packet Domain State
    ```

* SORACOM HarvestへHTTPポスト

    ```
    AT+QHTTPURL=25
    http://harvest.soracom.io
    AT+QHTTPCFG="contenttype",1
    AT+QHTTPPOST=5
    hello
    ```
