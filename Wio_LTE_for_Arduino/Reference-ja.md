# リファレンスマニュアル

|種類|識別子|
|:--|:--|
|定数|[WioLTE::D38](Reference-ja.md#wiolted38)|
||[WioLTE::D39](Reference-ja.md#wiolted39)|
||[WioLTE::D20](Reference-ja.md#wiolted20)|
||[WioLTE::D19](Reference-ja.md#wiolted19)|
||[WioLTE::A6](Reference-ja.md#wioltea6)|
||[WioLTE::A7](Reference-ja.md#wioltea7)|
||[WioLTE::A4](Reference-ja.md#wioltea4)|
||[WioLTE::A5](Reference-ja.md#wioltea5)|
||[WioLTE::SOCKET_TCP](Reference-ja.md#wioltesocket_tcp)|
||[WioLTE::SOCKET_UDP](Reference-ja.md#wioltesocket_udp)|
||[WIOLTE_D38](Reference-ja.md#wiolte_d38)|
||[WIOLTE_D39](Reference-ja.md#wiolte_d39)|
||[WIOLTE_D20](Reference-ja.md#wiolte_d20)|
||[WIOLTE_D19](Reference-ja.md#wiolte_d19)|
||[WioLTE_A6](Reference-ja.md#wiolte_a6)|
||[WioLTE_A7](Reference-ja.md#wiolte_a7)|
||[WioLTE_A4](Reference-ja.md#wiolte_a4)|
||[WioLTE_A5](Reference-ja.md#wiolte_a5)|
||[WIOLTE_TCP](Reference-ja.md#wiolte_tcp)|
||[WIOLTE_UDP](Reference-ja.md#wiolte_udp)|
|関数|[GetLastError](Reference-ja.md#getlasterror)|
||[Init](Reference-ja.md#init)|
||[PowerSupplyLTE](Reference-ja.md#powersupplylte)|
||[PowerSupplyCellular](Reference-ja.md#powersupplycellular)|
||[PowerSupplyGNSS](Reference-ja.md#powersupplygnss)|
||[PowerSupplyLed](Reference-ja.md#powersupplyled)|
||[PowerSupplyGrove](Reference-ja.md#powersupplygrove)|
||[PowerSupplySD](Reference-ja.md#powersupplysd)|
||[LedSetRGB](Reference-ja.md#ledsetrgb)|
||[TurnOnOrReset](Reference-ja.md#turnonorreset)|
||[TurnOff](Reference-ja.md#turnoff)|
||[Sleep](Reference-ja.md#sleep)|
||[Wakeup](Reference-ja.md#wakeup)|
||[GetIMEI](Reference-ja.md#getimei)|
||[GetIMSI](Reference-ja.md#getimsi)|
||[GetICCID](Reference-ja.md#geticcid)|
||[GetPhoneNumber](Reference-ja.md#getphonenumber)|
||[GetReceivedSignalStrength](Reference-ja.md#getreceivedsignalstrength)|
||[GetTime](Reference-ja.md#gettime)|
||[SendSMS](Reference-ja.md#sendsms)|
||[ReceiveSMS](Reference-ja.md#receivesms)|
||[DeleteReceivedSMS](Reference-ja.md#deletereceivedsms)|
||[WaitForCSRegistration](Reference-ja.md#waitforcsregistration)|
||[WaitForPSRegistration](Reference-ja.md#waitforpsregistration)|
||[Activate](Reference-ja.md#activate)|
||[Deactivate](Reference-ja.md#deactivate)|
||[SyncTime](Reference-ja.md#synctime)|
||[GetLocation](Reference-ja.md#getlocation)|
||[SocketOpen](Reference-ja.md#socketopen)|
||[SocketSend](Reference-ja.md#socketsend)|
||[SocketReceive](Reference-ja.md#socketreceive)|
||[SocketClose](Reference-ja.md#socketclose)|
||[HttpGet](Reference-ja.md#httpget)|
||[HttpPost](Reference-ja.md#httppost)|
||[EnableGNSS](Reference-ja.md#enablegnss)|
||[DisableGNSS](Reference-ja.md#disablegnss)|
||[GetGNSSLocation](Reference-ja.md#getgnsslocation)|
||[SystemReset](Reference-ja.md#systemreset)|

## 定数

### WioLTE::D38

GroveコネクターピンD38のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WioLTE::D39

GroveコネクターピンD39(D38と同一コネクター)のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WioLTE::D20

GroveコネクターピンD20のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WioLTE::D19

GroveコネクターピンD19(D20と同一コネクター)のピン番号です。
pinMode(), digitalRead(), digitalWrite()の引数に使用します。

### WioLTE::A6

GroveコネクターピンA6のピン番号です。
pinMode(), analogRead(), digitalRead(), digitalWrite()の引数に使用します。

※analogReadを利用する際は `pinMode(WioLTE::A6, INPUT_ANALOG);` を指定してください。

### WioLTE::A7

GroveコネクターピンA7(A6と同一コネクター)のピン番号です。
pinMode(), analogRead(), digitalRead(), digitalWrite()の引数に使用します。

※analogReadを利用する際は `pinMode(WioLTE::A7, INPUT_ANALOG);` を指定してください。

### WioLTE::A4

GroveコネクターピンA4のピン番号です。
pinMode(), analogRead(), digitalRead(), digitalWrite()の引数に使用します。

※analogReadを利用する際は `pinMode(WioLTE::A4, INPUT_ANALOG);` を指定してください。

### WioLTE::A5

GroveコネクターピンA5(A4と同一コネクター)のピン番号です。
pinMode(), analogRead(), digitalRead(), digitalWrite()の引数に使用します。

※analogReadを利用する際は `pinMode(WioLTE::A5, INPUT_ANALOG);` を指定してください。

### WioLTE::SOCKET_TCP

TCP通信の指定です。
SocketOpen()の引数に使用します。

### WioLTE::SOCKET_UDP

UDP通信の指定です。
SocketOpen()の引数に使用します。

### WIOLTE_D38

WioLTE::D38の別名です。

### WIOLTE_D39

WioLTE::D39の別名です。

### WIOLTE_D20

WioLTE::D20の別名です。

### WIOLTE_D19

WioLTE::D19の別名です。

### WIOLTE_A6

WioLTE::A6の別名です。

### WIOLTE_A7

WioLTE::A7の別名です。

### WIOLTE_A4

WioLTE::A4の別名です。

### WIOLTE_A5

WioLTE::A5の別名です。

### WIOLTE_TCP

WioLTE::SOCKET_TCPの別名です。

### WIOLTE_UDP

WioLTE::SOCKET_UDPの別名です。

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

Wio LTEを初期化します。
初期化直後は、LTEモジュール電源・Groveコネクター電源がオフします。

### PowerSupplyLTE

```cpp
void PowerSupplyLTE(bool on)
```

#### 引数

|引数|説明|
|:--|:--|
|on|電源供給のオン/オフ。オンしたいときはtrue、オフしたいときはfalseを指定します。|

#### 説明

Wio LTE上のLTEモジュールの電源供給をオン/オフします。
LTEモジュールは電源供給オンの後に、起動操作（TurnOnOrReset）しないと利用できません。
本関数を実行した後の、LTEモジュールの操作は0.5秒以上待ってください。（LTEモジュールの動作が安定するまで待つ。）

### PowerSupplyCellular

```cpp
void PowerSupplyCellular(bool on)
```

#### 引数

|引数|説明|
|:--|:--|
|on|電源供給のオン/オフ。オンしたいときはtrue、オフしたいときはfalseを指定します。|

#### 説明

Wio LTE上のLTEモジュールの電源供給をオン/オフします。
LTEモジュールは電源供給オンの後に、起動操作（TurnOnOrReset）しないと利用できません。
本関数を実行した後の、LTEモジュールの操作は0.5秒以上待ってください。（LTEモジュールの動作が安定するまで待つ。）

### PowerSupplyGNSS

```cpp
void PowerSupplyGNSS(bool on)
```

#### 引数

|引数|説明|
|:--|:--|
|on|電源供給のオン/オフ。オンしたいときはtrue、オフしたいときはfalseを指定します。|

#### 説明

GNSS/GPSアンテナへの電源供給をオン/オフします。
日本版Wio LTEにはGNSS/GPS機能が無いので、本関数を使うことはありません。

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

### PowerSupplySD

```cpp
void PowerSupplySD(bool on)
```

#### 引数

|引数|説明|
|:--|:--|
|on|電源供給のオン/オフ。オンしたいときはtrue、オフしたいときはfalseを指定します。|

#### 説明

マイクロSDの電源供給をオン/オフします。

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

Wio LTE上のフルカラーLEDを点灯します。
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

Wio LTE上のLTEモジュールを起動操作します。
LTEモジュールが電源オンしていないときは電源オン、電源オンしているときはリセットします。
本関数を実行する前に、LTEモジュールへ電源供給（PowerSupplyLTE）してください。

### TurnOff

```cpp
bool TurnOff(long timeout = 60000)
```

#### 引数

|引数|説明|
|:--|:--|
|timeout|タイムアウト時間[ミリ秒]。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

Wio LTE上のLTEモジュールを停止操作します。

### Sleep

```cpp
void Sleep()
```

#### 説明

LTEモジュールを省電力モードにします。
本関数を実行した後に、LTEモジュールを使うときは、省電力モードから復帰（Wakeup）する必要があります。

### Wakeup

```cpp
bool Wakeup()
```

#### 説明

LTEモジュールを省電力モードから通常モードに復帰します。

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

Wio LTEのIMEIを取得します。

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

Wio LTEに取り付けられたSIMのIMSIを取得します。

### GetICCID

```cpp
int GetICCID(char* iccid, int iccidSize)
```

#### 引数

|引数|説明|
|:--|:--|
|iccid|ICCIDを取得する変数。文字列。|
|iccidSize|iccidのバイト数。|

#### 戻り値

|説明|
|:--|
|成功したときはICCIDの文字数、失敗したときはマイナス値を返します。|

#### 説明

Wio LTEに取り付けられたSIMのICCIDを取得します。

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

Wio LTEに取り付けられたSIMの電話番号を取得します。

### GetReceivedSignalStrength

```cpp
int GetReceivedSignalStrength()
```

#### 戻り値

|説明|
|:--|
|受信信号強度[dBm]を返します。失敗したときはINT_MIN(limits.h)を返します。|

#### 説明

LTEモジュールが受信している信号強度[dBm]を取得します。

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

LTEモジュールが保持している日時を取得します。

### SendSMS

```cpp
bool SendSMS(const char* dialNumber, const char* message)
```

#### 引数

|引数|説明|
|:--|:--|
|dialNumber|発信先の電話番号。|
|message|ショートメッセージ。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

指定した電話番号に、ショートメッセージ（SMS）を送ります。
日本語は対応していません。

### ReceiveSMS

```cpp
int ReceiveSMS(char* message, int messageSize, char* dialNumber = NULL, int dialNumberSize = 0)
```

#### 引数

|引数|説明|
|:--|:--|
|message|ショートメッセージを取得する変数。文字列。|
|messageSize|messageのバイト数。|
|dialNumber|発信元の電話番号を取得する変数。文字列。|
|dialNumberSize|dialNumberのバイト数。|

#### 戻り値

|説明|
|:--|
|受信したショートメッセージが無いときはゼロ、有るときはショートメッセージの文字数、失敗したときはマイナス値を返します。|

#### 説明

受信したショートメッセージ（SMS）のうちの、一番古いショートメッセージを取得します。
本関数を実行しても、受信したショートメッセージは消えません。
次のショートメッセージを取得したいときは、DeleteReceivedSMS関数を実行して、古いメッセージを削除してください。
日本語は対応していません。

### DeleteReceivedSMS

```cpp
bool DeleteReceivedSMS()
```

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

受信したショートメッセージ（SMS）のうちの、一番古いショートメッセージを削除します。
受信したショートメッセージが無いときは、falseを返します。

### WaitForCSRegistration

```cpp
bool WaitForCSRegistration(long timeout = 120000)
```

#### 引数

|引数|説明|
|:--|:--|
|timeout|タイムアウト時間[ミリ秒]。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

CSネットワークに登録完了するまで待ちます。

### WaitForPSRegistration

```cpp
bool WaitForPSRegistration(long timeout = 120000)
```

#### 引数

|引数|説明|
|:--|:--|
|timeout|タイムアウト時間[ミリ秒]。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

PSネットワークに登録完了するまで待ちます。

### Activate

```cpp
bool Activate(const char* accessPointName, const char* userName, const char* password, long waitForRegistTimeout = 120000)
```

#### 引数

|引数|説明|
|:--|:--|
|accessPointName|APN。|
|userName|ユーザー名。|
|password|パスワード。|
|waitForRegistTimeout|タイムアウト時間[ミリ秒]。|

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

### SyncTime

```cpp
bool SyncTime(const char* host)
```

#### 引数

|引数|説明|
|:--|:--|
|host|NTPサーバーのホスト名。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

LTEモジュールの日時を、指定したNTPサーバーの日時に合わせます。

### GetLocation

```cpp
bool GetLocation(double* longitude, double* latitude)
```

#### 引数

|引数|説明|
|:--|:--|
|longitude|経度。|
|latitude|緯度。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

接続している基地局の位置（緯度、経度）を取得します。

### SocketOpen

```cpp
int SocketOpen(const char* host, int port, SocketType type)
```

#### 引数

|引数|説明|
|:--|:--|
|host|接続先のホスト名。|
|port|接続先のポート番号。|
|type|ソケット通信の種類。TCP通信はWIOLTE_TCP、UDP通信はSOCKET_UDPを指定します。|

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
int HttpGet(const char* url, char* data, int dataSize, long timeout = 60000)
int HttpGet(const char* url, char* data, int dataSize, const WioLTEHttpHeader& header, long timeout = 60000)
```

#### 引数

|引数|説明|
|:--|:--|
|url|接続するURL。例："http://test.co.jp", "https://test.co.jp" |
|data|受信したデータを取得する変数。|
|dataSize|dataのバイト数。|
|header|カスタムHTTPヘッダ。|
|timeout|タイムアウト時間[ミリ秒]。|

#### 戻り値

|説明|
|:--|
|成功したときはデータの文字数、失敗したときはマイナス値を返します。|

#### 説明

指定したURLから、HTTP通信でGETします。

### HttpPost

```cpp
bool HttpPost(const char* url, const char* data, int* responseCode, long timeout = 60000)
bool HttpPost(const char* url, const char* data, int* responseCode, const WioLTEHttpHeader& header, long timeout = 60000)
```

#### 引数

|引数|説明|
|:--|:--|
|url|接続するURL。例："http://test.co.jp", "https://test.co.jp" |
|data|送信するデータ。|
|responseCode|受信したHTTPレスポンスステータスコードを取得する変数。|
|header|カスタムHTTPヘッダ。|
|timeout|タイムアウト時間[ミリ秒]。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

指定したURLへ、HTTP通信でPOSTします。

### EnableGNSS

```cpp
bool EnableGNSS(long timeout = 60000)
```

#### 引数

|引数|説明|
|:--|:--|
|timeout|タイムアウト時間[ミリ秒]。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

GNSS/GPS機能を有効にします。
日本版Wio LTEにはGNSS/GPS機能が無いので、本関数を使うことはありません。

### DisableGNSS

```cpp
bool DisableGNSS()
```

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

GNSS/GPS機能を無効にします。
日本版Wio LTEにはGNSS/GPS機能が無いので、本関数を使うことはありません。

### GetGNSSLocation

```cpp
bool GetGNSSLocation(double* longitude, double* latitude, double* altitude = NULL, struct tm* tim = NULL)
```

#### 引数

|引数|説明|
|:--|:--|
|longitude|経度。|
|latitude|緯度。|
|altitude|高度。[m]|
|tim|日時。|

#### 戻り値

|説明|
|:--|
|成功したときはtrue、失敗したときはfalseを返します。|

#### 説明

GNSS/GPS機能を使って、現在地を取得します。

### SystemReset

```cpp
static void SystemReset()
```

#### 説明

CPUをリセットします。
