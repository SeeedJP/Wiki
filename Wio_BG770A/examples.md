# Wio BG770A サンプルスケッチ

## 一覧

* 💪 ... スキルアップ。スケッチの中身を読んでみましょう。
* 🌶️ ... 難易度、中。（中辛）
* 🌶️🌶️ ... 難易度、高。（激辛）

### 基本

||スケッチ|内容|必要なもの|
|:--|:--|:--|:--|
||basic/blink|USER LEDを点滅します。<br>> [追加情報](examples/basic/blink.md)||
|💪|basic/flash|USERボタンを押すと、FeRAMに書かれているカウント値を加算します。USERボタンを押しながら起動するとカウント値をゼロにリセットします。<br>> [追加情報](examples/basic/flash.md)||
|💪|basic/watchdog|USERボタンを押さずに10秒経過すると、ウォッチドックがCPUをリセットします。<br>> [追加情報](examples/basic/watchdog.md)||

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
||cellular/transparent|セルラーモジュールをシリアルモニタからATコマンドで操作します。<br>> [追加情報](examples/cellular/transparent.md)|nanoSIM|
||cellular/shell🌶️|セルラーモジュールをシリアルモニタから操作するシェルです。<br>> [追加情報](examples/cellular/shell.md)|nanoSIM|

### セルラー通信（SORACOMプラットフォーム）

||スケッチ|内容|必要なもの|
|:--|:--|:--|:--|
||soracom/soracom-connectivity-diagnostics🌶️|SORACOMプラットフォームへの接続を確認します。<br>> [追加情報](examples/soracom/soracom-connectivity-diagnostics.md)|SORACOM Air for セルラー|
|💪|soracom/soracom-uptime|稼働時間をSORACOM Unified Endpointへ送信します。<br>> [追加情報](examples/soracom/soracom-uptime.md)|SORACOM Air for セルラー|
|💪|soracom/soracom-uptime-tcpclient|稼働時間をSORACOM Unified Endpointへ送信します。<br>WioCellularTcpClientクラスを使用して実装しています。|SORACOM Air for セルラー|
|💪|soracom/soracom-uptime-lp🌶️🌶️|稼働時間をSORACOM Unified Endpointへ送信します。PSM機能を使って電力消費を抑止しています。<br>> [追加情報](examples/soracom/soracom-uptime-lp.md)|SORACOM Air for セルラー|
|💪|application/soracom-gps-tracker🌶️🌶️|GPSで取得した位置情報をSORACOM Unified Endpointへ送信します。|[Grove - GPS Module](https://www.seeedstudio.com/Grove-GPS-Module.html)<br>SORACOM Air for セルラー|

