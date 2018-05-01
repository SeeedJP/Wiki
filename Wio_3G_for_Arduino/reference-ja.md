# リファレンスマニュアル

|種類|識別子|
|:--|:--|
|定数|[WIO_TCP](reference-ja.md#wio_tcp)|
||[WIO_UDP](reference-ja.md#wio_udp)|
||[WIO_D38](reference-ja.md#wio_d38)|
||[WIO_D39](reference-ja.md#wio_d39)|
||[WIO_D20](reference-ja.md#wio_d20)|
||[WIO_D19](reference-ja.md#wio_d19)|
||[WIO_A6](reference-ja.md#wio_a6)|
||[WIO_A7](reference-ja.md#wio_a7)|
||[WIO_A4](reference-ja.md#wio_a4)|
||[WIO_A5](reference-ja.md#wio_a5)|
||[WIO_UART_D23](reference-ja.md#wio_uart_d23)|
||[WIO_UART_D22](reference-ja.md#wio_uart_d22)|
||[WIO_I2C_D24](reference-ja.md#wio_i2c_d24)|
||[WIO_I2C_D25](reference-ja.md#wio_i2c_d25)|
||[Wio3G::SOCKET_TCP](reference-ja.md#wio3gsocket_tcp)|
||[Wio3G::SOCKET_UDP](reference-ja.md#wio3gsocket_udp)|
|関数|[GetLastError](reference-ja.md#getlasterror)|
||[Init](reference-ja.md#init)|
||[PowerSupplyCellular](reference-ja.md#powersupplycellular)|
||[PowerSupplyLed](reference-ja.md#powersupplyled)|
||[PowerSupplyGrove](reference-ja.md#powersupplygrove)|
||[LedSetRGB](reference-ja.md#ledsetrgb)|
||[TurnOnOrReset](reference-ja.md#turnonorreset)|
||[TurnOff](reference-ja.md#turnoff)|
||[GetIMEI](reference-ja.md#getimei)|
||[GetIMSI](reference-ja.md#getimsi)|
||[GetPhoneNumber](reference-ja.md#getphonenumber)|
||[GetReceivedSignalStrength](reference-ja.md#getreceivedsignalstrength)|
||[GetTime](reference-ja.md#gettime)|
||[Activate](reference-ja.md#activate)|
||[Deactivate](reference-ja.md#deactivate)|
||[SocketOpen](reference-ja.md#socketopen)|
||[SocketSend](reference-ja.md#socketsend)|
||[SocketReceive](reference-ja.md#socketreceive)|
||[SocketClose](reference-ja.md#socketclose)|
||[HttpGet](reference-ja.md#httpget)|
||[HttpPost](reference-ja.md#httppost)|

## 定数

### WIO_TCP

TCP通信の指定です。
SocketOpen()の引数に使用します。

### WIO_UDP

UDP通信の指定です。
SocketOpen()の引数に使用します。

### WIO_D38

GroveコネクターピンD38のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WIO_D39

GroveコネクターピンD39のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WIO_D20

GroveコネクターピンD20のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WIO_D19

GroveコネクターピンD19のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WIO_A6

GroveコネクターピンA6のピン番号です。
pinMode(), analogRead(), digitalRead(), digitalWrite()の引数に使用します。

※analogReadを利用する際は `pinMode(WIO_A6, INPUT_ANALOG);` を指定してください。

### WIO_A7

GroveコネクターピンA7のピン番号です。
pinMode(), analogRead(), digitalRead(), digitalWrite()の引数に使用します。

※analogReadを利用する際は `pinMode(WIO_A7, INPUT_ANALOG);` を指定してください。

### WIO_A4

GroveコネクターピンA4のピン番号です。
pinMode(), analogRead(), digitalRead(), digitalWrite()の引数に使用します。

※analogReadを利用する際は `pinMode(WIO_A4, INPUT_ANALOG);` を指定してください。

### WIO_A5

GroveコネクターピンA5のピン番号です。
pinMode(), analogRead(), digitalRead(), digitalWrite()の引数に使用します。

※analogReadを利用する際は `pinMode(WIO_A5, INPUT_ANALOG);` を指定してください。

### WIO_UART_D23

GroveコネクターピンD23のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WIO_UART_D22

GroveコネクターピンD22のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WIO_I2C_D24

GroveコネクターピンD24のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WIO_I2C_D25

GroveコネクターピンD25のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### Wio3G::SOCKET_TCP

TCP通信の指定です。
SocketOpen()の引数に使用します。

### Wio3G::SOCKET_UDP

UDP通信の指定です。
SocketOpen()の引数に使用します。

## 関数

### GetLastError

```cpp
ErrorCodeType GetLastError() const
```

#### 戻り値

|説明|
|:--|
|最後に実行した関数のエラーコードを返します。|

#### 説明

一番最後に実行した関数のエラーコードを返します。エラーが無いときはE_OKを返します。

### Init

```cpp
void Init()
```

#### 説明

Wio 3Gを初期化します。
初期化直後は、全ての電源がオフします。

### PowerSupplyCellular

```cpp
void PowerSupplyCellular(bool on)
```

#### 引数

|引数|説明|
|:--|:--|
|on|電源供給のオン/オフ。オンしたいときはtrue、オフしたいときはfalseを指定します。|

#### 説明

Wio 3G上の3Gモジュールの電源供給をオン/オフします。
3Gモジュールは電源供給オンの後に、起動操作（TurnOnOrReset）しないと利用できません。
本関数を実行した後の、3Gモジュールの操作は0.5秒以上待ってください。（3Gモジュールの動作が安定するまで待つ。）

### PowerSupplyLed

```cpp
void PowerSupplyLed(bool on)
```

#### 引数

|引数|説明|
|:--|:--|
|on|電源供給のオン/オフ。オンしたいときはtrue、オフしたいときはfalseを指定します。|

#### 説明

フルカラーLEDへの電源供給をオン/オフします。

### PowerSupplyGrove

```cpp
void PowerSupplyGrove(bool on)
```

#### 引数

|引数|説明|
|:--|:--|
|on|電源供給のオン/オフ。オンしたいときはtrue、オフしたいときはfalseを指定します。|

#### 説明

Groveコネクター D20/A4/A6/I2C/UARTの電源供給をオン/オフします。
> Groveコネクター D38の電源は常時オンです。

### LedSetRGB

```cpp
void LedSetRGB(byte red, byte green, byte blue)
```

#### 引数

|引数|説明|
|:--|:--|
|red|赤色の度合い。0～255を指定します。|
|green|緑色の度合い。0～255を指定します。|
|blue|青色の度合い。0～255を指定します。|

#### 説明

Wio 3G上のフルカラーLEDを点灯します。
消灯したいときは、red/green/blue全てに0を指定します。

### TurnOnOrReset

```cpp
bool TurnOnOrReset()
```

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

Wio 3G上の3Gモジュールを起動操作します。
3Gモジュールが電源オンしていないときは電源オン、電源オンしているときはリセットします。
本関数を実行する前に、3Gモジュールへ電源供給（PowerSupplyCellular）してください。

### TurnOff

```cpp
bool TurnOff()
```

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

Wio 3G上の3Gモジュールを停止操作します。

### GetIMEI

```cpp
int GetIMEI(char* imei, int imeiSize)
```

#### 引数

|引数|説明|
|:--|:--|
|imei|IMEIを取得する変数。文字列。|
|imeiSize|imeiのバイト数。|

#### 戻り値

|説明|
|:--|
|成功したときはIMEIの文字数、失敗したときはマイナス値を返します。|

#### 説明

Wio 3GのIMEIを取得します。

### GetIMSI

```cpp
int GetIMSI(char* imsi, int imsiSize)
```

#### 引数

|引数|説明|
|:--|:--|
|imsi|IMSIを取得する変数。文字列。|
|imsiSize|imsiのバイト数。|

#### 戻り値

|説明|
|:--|
|成功したときはIMSIの文字数、失敗したときはマイナス値を返します。|

#### 説明

Wio 3Gに取り付けられたSIMのIMSIを取得します。

### GetPhoneNumber

```cpp
int GetPhoneNumber(char* number, int numberSize)
```

#### 引数

|引数|説明|
|:--|:--|
|number|電話番号を取得する変数。文字列。|
|numberSize|numberのバイト数。|

#### 戻り値

|説明|
|:--|
|成功したときは電話番号の文字数、失敗したときはマイナス値を返します。|

#### 説明

Wio 3Gに取り付けられたSIMの電話番号を取得します。

### GetReceivedSignalStrength

```cpp
int GetReceivedSignalStrength()
```

#### 戻り値

|説明|
|:--|
|受信信号強度[dBm]を返します。失敗したときはINT_MIN(limits.h)を返します。|

#### 説明

3Gモジュールが受信している信号強度[dBm]を取得します。

### GetTime

```cpp
bool GetTime(struct tm* tim)
```

#### 引数

|引数|説明|
|:--|:--|
|tim|日時を取得する変数。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

3Gモジュールが保持している日時を取得します。

### Activate

```cpp
bool Activate(const char* accessPointName, const char* userName, const char* password)
```

#### 引数

|引数|説明|
|:--|:--|
|accessPointName|APN。|
|userName|ユーザー名。|
|password|パスワード。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

指定したAPN、ユーザー名、パスワードを使って、データ通信を有効にします。

### Deactivate

```cpp
bool Deactivate()
```

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

データ通信を無効にします。

### SocketOpen

```cpp
int SocketOpen(const char* host, int port, SocketType type)
```

#### 引数

|引数|説明|
|:--|:--|
|host|接続先のホスト名。|
|port|接続先のポート番号。|
|type|ソケット通信の種類。TCP通信はWIO_TCP、UDP通信はWIO_UDPを指定します。|

#### 戻り値

|説明|
|:--|
|成功したときは接続ID、失敗したときはマイナス値を返します。|

#### 説明

指定したホスト名、ポート番号に、ソケット通信を接続します。
同時に12個まで接続することが可能です。

### SocketSend

```cpp
bool SocketSend(int connectId, const byte* data, int dataSize)
bool SocketSend(int connectId, const char* data)
```

#### 引数

|引数|説明|
|:--|:--|
|connectId|接続ID。|
|data|送信するデータ。|
|dataSize|送信するデータのバイト数。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

指定した接続へデータを送信します。
一度に送信できるデータは1460バイト以下です。

### SocketReceive

```cpp
int SocketReceive(int connectId, byte* data, int dataSize)
int SocketReceive(int connectId, char* data, int dataSize)
int SocketReceive(int connectId, byte* data, int dataSize, long timeout)
int SocketReceive(int connectId, char* data, int dataSize, long timeout)
```

#### 引数

|引数|説明|
|:--|:--|
|connectId|接続ID。|
|data|受信したデータを取得する変数。|
|dataSize|dataのバイト数。|
|timeout|タイムアウト時間[ミリ秒]。|

#### 戻り値

|説明|
|:--|
|受信したデータが無いときはゼロ、有るときはデータのバイト数、失敗したときはマイナス値を返します。|

#### 説明

指定した接続に受信したデータを取得します。
受信したデータが無いときはゼロを返します。
タイムアウト時間を指定したときは、その時間、受信を待ちます。

### SocketClose

```cpp
bool SocketClose(int connectId)
```

#### 引数

|引数|説明|
|:--|:--|
|connectId|接続ID。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

指定した接続をクローズします。

### HttpGet

```cpp
int HttpGet(const char* url, char* data, int dataSize)
```

#### 引数

|引数|説明|
|:--|:--|
|url|接続するURL。例："http://test.co.jp", "https://test.co.jp" |
|data|受信したデータを取得する変数。|
|dataSize|dataのバイト数。|

#### 戻り値

|説明|
|:--|
|成功したときはデータの文字数、失敗したときはマイナス値を返します。|

#### 説明

指定したURLから、HTTP通信でGETします。

### HttpPost

```cpp
bool HttpPost(const char* url, const char* data, int* responseCode)
```

#### 引数

|引数|説明|
|:--|:--|
|url|接続するURL。例："http://test.co.jp", "https://test.co.jp" |
|data|送信するデータ。|
|responseCode|受信したHTTPレスポンスステータスコードを取得する変数。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

指定したURLへ、HTTP通信でPOSTします。

